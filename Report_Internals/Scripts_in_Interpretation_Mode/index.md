# Scripts in Interpretation Mode

When developing reports, various scripts can be executed in **Interpretation** mode. To enable this functionality, the following conditions must be met:

- The report template property **Script Language** must be set to C#;
- The script description must contain a `return` statement.


> **Information**
>
> If an expression contains a `return` operator, the report engine processes this expression as a script. Without a `return` operator, any constructs are treated as a regular expression.

When developing various scripts, you can use:

- report variables;
- data columns;
- functions, including custom functions;
- basic C# constructs such as if, else, the ternary operator, and loops.


Scripts can be used in:

- report events;
- custom functions;
- report expressions;
- expressions of components, variables, and calculated columns.

### Script Language

Script processing in a report depends on the selected value of the **Script Language** property. To ensure that C# scripts work on all supported platforms, the Script Language property must be set to C#. This value is used by default for all newly created reports. However, for backward compatibility, reports created earlier may have the **Script Language** property set to **Platform**. In this case, the scripting language depends on the platform used to generate the report:

- on the .NET platform - C# scripts are used;
- on the JS platform - JavaScript is used.

### Script Execution Management

To completely disable script execution, set the report property **Allow Scripts To Run** to **False**. If you only need to disable scripts in expressions, set the report property **Allow Scripts In Expressions** to **False**.


> **Information**
>
> Please note that script execution in expressions also depends on the **Allow Scripts To Run** property. If script execution is disabled in the report properties, the value of the **Allow Scripts In Expressions** property will be ignored, because scripts will not be executed. In addition, you can configure a script timeout in seconds using the **Script Timeout** property.

By default, report designers use Safe Script Execution Mode. For more details, see the [Safe Mode](Safety_Mode.md) section.
