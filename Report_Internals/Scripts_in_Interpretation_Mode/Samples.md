# Samples

This chapter provides several samples of using C# constructs in scripts.


### Variables and Types

In Stimulsoft scripts, variables can be declared using the var keyword or by explicitly specifying the type. All basic C# types are supported, including numbers, strings, dates, boolean values, colors, collections, and objects.


**C#**

```csharp
...
var number = 10;
var text = "Hello, World!";
var isActive = true;
var price = 19.99m;
var date = DateTime.Today;
var color = Color.Red;
...
```

### Arrays and Collections

.NET arrays and collections are available.


**C#**

```csharp
...
var numbers = new int[3];
var list = new List<string>();
var dict = new Dictionary<string, int>();
...
```

### Special Types

Types such as GUID, Color, and custom business objects can also be used if they are registered in the report.


**C#**

```csharp
...
var id = Guid.NewGuid();
var color = Color.FromArgb(255, 128, 64);
...
```

In Stimulsoft scripts, you can directly use variables defined in the report, as well as access and modify their values in code. To access a variable, simply specify its name without additional prefixes, for example: `var value = MyVariable`; If a variable is declared in the report, it automatically becomes available in all report scripts, including component events, expressions, custom functions, and global scripts. You can also assign new values to variables: `MyVariable = 42`; This allows variables to be used for storing intermediate results, transferring data between different parts of the report, and dynamically controlling report generation logic.

### Type Conversion

Both implicit and explicit type conversions are supported.


**C#**

```csharp
...
var d = 5.5;
var i = (int)d; // 5
var s = (string)123; // "123"
...
```

### Operators in Stimulsoft Scripts

Stimulsoft scripts support all standard C# operators, including:

- arithmetic operators  (+, -, *, /, %);
- comparison operators  (==, !=, &lt;, &gt;, &lt;=, &gt;=), logical operators  (&&, ||, !);
- bitwise operators  (&, |, ^, ~, &lt;&lt;, &gt;&gt;);
- assignment operators  (=, +=, -=, *=, /=, %=, etc.);
- the ternary operator  (? :);
- increment and decrement operators  (++, --);
- type checking and casting operators  (is, as, typeof, GetType).


This makes it possible to use familiar C# expressions and constructs for calculations, conditions, working with variables and types, just as in standard C#. All operators follow the same precedence and associativity rules as in C#, including support for complex expressions, operator combinations, and all standard usage scenarios in conditions, loops, functions, and collections.

### Loops in Stimulsoft Scripts

All main types of C# loops can be used in Stimulsoft scripts.


The loop `for`. A loop with an explicit counter. It is usually used when you know in advance how many times an action needs to be repeated.


**C#**

```csharp
...
var sum = 0;
for (var i = 0; i < 5; i++) {
    sum += i;
}
// sum = 0 + 1 + 2 + 3 + 4 = 10
...
```

The loop `while`. A loop with a precondition that runs as long as the condition is true.

**C#**

```csharp
...
var count = 0;
while (count < 3) {
    count++;
}
// count = 3
...
```

The loop `do...while`. A loop with a postcondition that executes the loop body at least once.


**C#**

```csharp
...
var value = 0;
do {
    value += 2;
} while (value < 6);
// value = 6
...
```

The loop `foreach`. A loop for iterating over each element of a collection (e.g., a list, array, etc.).


**C#**

```csharp
...
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
var total = 0;

foreach (var item in list) {
    total += item;
}
// total = 6
...
```

Inside loops, you can use `break` to exit the loop and `continue` to move to the next iteration. Here are some examples with `break` and `continue`:


**C#**

```csharp
...
for (var i = 0; i < 10; i++) {
    if (i == 5) break;
    if (i % 2 == 0) continue;
    // This code will only execute for odd i values less than 5.
}
...
```

### Functions in Stimulsoft Scripts

You can use different types of functions in scripts: built-in functions, static functions, type functions, and custom (user) functions, which can be defined directly in the code or accessed from the report.

### Built-in Stimulsoft Functions

Scripts support a large number of built-in Stimulsoft functions for working with data, strings, numbers, dates, colors, and more. These functions can be called directly by name.


**C#**

```csharp
...
var empty = IsNullOrEmpty("");
var max = Maximum(3, 5);
var color = RGB(255, 0, 0);
...
```

[Full list of built-in functions.](../Functions/index.md)

### Static .NET Methods

You can use static methods from standard .NET classes, for example, to convert types or to work with numbers, strings, and dates.


**C#**

```csharp
...
var absValue = Math.Abs(-10);
var rounded = Math.Round(2.6);
var parsed = int.Parse("123");
var now = DateTime.Now;
var formatted = string.Format("Value: {0}", 42);
...
```

### Type Methods (Object Methods)

Methods of standard .NET types are available, including methods for strings, numbers, dates, and collections.


**C#**

```csharp
...
var text = "hello";
var upper = text.ToUpper();
var length = text.Length;
var tomorrow = now.AddDays(1);
var exists = list.Contains(2);
...
```

### Custom Functions

You can declare your own functions directly in the script and call them as usual.


**C#**

```csharp
...
double square(double n) {
    return n * n;
}
var result = square(5);
...
```

### Report Functions

If custom functions are defined in the report, they can be called by name if they are available in the script context.


**C#**

```csharp
...
var value = MyReportFunction(10);
...
```

### Type Casting and Type Checking

Stimulsoft scripts support standard C# operators for working with types: `as`, `is`, `typeof`, as well as explicit and implicit type conversions. You can also use the `GetType()` method to retrieve type information about an object.


Operator `is`. The operator allows you to check whether an object belongs to a certain type. Returns `true` or `false`.


**C#**

```csharp
...
var result = "hello" is string; // true
var isInt = 123 is int; // true
var isBool = 123 is bool; // false
...
```

Operator `as`. The operator attempts a type conversion. If the conversion is not possible, it returns `null` (rather than throwing an exception).


**C#**

```csharp
...
var obj = "hello";
var str = obj as string; // "hello"
var num = obj as int;    // null
...
```

Operator `typeof`. The operator allows you to obtain a type object for further checking or reflection.


**C#**

```csharp
...
typeof(string); // Type { Name = "String", FullName = "System.String" }
typeof(int);    // Type { Name = "Int32",  FullName = "System.Int32" }
...
```

Operator `GetType()`. The method returns the actual type of the object at runtime. This is useful for dynamic testing and debugging.


**C#**

```csharp
...
var value = 123;
var typeName = value.GetType().Name; // "Int32"
var typeFullName = value.GetType().FullName; // "System.Int32"
var text = "abc";
var isString = text.GetType() == typeof(string); // true
...
```

The parser supports standard C# casting syntax, including conversions between numbers, strings, boolean values, and other types. If a conversion is not possible, an exception is thrown, as in regular C#.

### Using Data Sources and Business Objects in Stimulsoft Scripts

In Stimulsoft scripts, you can directly access data sources registered in the report, as well as their related data and business objects. To access data, simply use the data source name, for example:


**C#**

```csharp
...
Products.First();
var name = Products.ProductName;
...
```

Here we move to the first row of the Products data source and read the value of its ProductName column. If relationships are set up between data sources, we can access related data using a dot:


**C#**

```csharp
...
var categoryName = Products.Categories.CategoryName;
...
```

This is how you can get the category name for the current product. Navigation methods such as `First()`, `Next()`, `Previous()`.


If business objects are added to a report via the `RegBusinessObject` method, they can be accessed by name like regular objects:


**C#**

```csharp
...
var id = Business.Id;
var name = Business.Name;
Business.Name = "NewName";
...
```

For nested objects, use dot.


**C#**

```csharp
...
var subPrice = Business.Child.SubChild.Price;
...
```
