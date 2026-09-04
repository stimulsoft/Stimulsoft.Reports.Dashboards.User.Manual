# Safe Mode

By default, scripts are executed in Safe Mode with certain restrictions. Safe Mode is recommended when running user-defined scripts or scripts from untrusted sources. This helps restrict access to the file system, network, system processes, and other potentially dangerous platform capabilities.


To disable these restrictions, set the **Script Security** option in the report designer **Options** menu to **Full Access**. If the **Script Security** option is set to **Safe Mode**, the following restrictions are applied during script execution.

### Type Validation

Before types are used in a script, they are validated against lists of allowed and prohibited types.

Validation specifics:

- Both fully qualified type names and short type names are checked;
- Namespaces are validated by prefix. If a namespace starts with a prohibited value, the type is considered unavailable;
- For arrays and generic types, validation is performed recursively. If at least one nested type is prohibited, the entire type is blocked from use.

### Resource Usage Restrictions

To protect against excessive memory and CPU consumption, the following limitations are applied:

- Maximum array size - 10 000 elements;
- Maximum recursion depth - 50 calls;
- Maximum number of execution steps or loop iterations - 100 000;
- Maximum nesting depth of generic types - 10 levels.


If any of these limits are exceeded, script execution is terminated.

### Prohibited Types

In Safe Mode, types that allow system operations, work with processes, networking, threading, serialization, or dynamic code loading are unavailable.

The following types are prohibited:

- System.Activator
- System.AppDomain
- System.Environment
- System.Diagnostics.Process
- System.Diagnostics.ProcessStartInfo
- System.Threading.Thread
- System.Threading.Tasks.Task
- System.Runtime.InteropServices.Marshal
- System.Runtime.Serialization.Formatters.Binary.BinaryFormatter
- System.Xml.Serialization.XmlSerializer
- System.Data.SqlClient.SqlConnection
- System.Data.OleDb.OleDbConnection
- System.Net.Http.HttpClient
- System.Net.WebClient
- System.Net.Sockets.Socket
- System.Net.Sockets.TcpClient
- Stimulsoft.Base.StiCSharpScriptParser


### Prohibited Namespaces

By default, the following namespaces are prohibited:

- System.IO
- System.Diagnostics
- System.Net
- System.Net.Sockets
- System.Reflection
- System.Runtime.InteropServices
- System.Security.Cryptography
- System.CodeDom
- System.Web
- Microsoft.CSharp
- Microsoft.VisualBasic
- Microsoft.Win32


All types belonging to these namespaces are considered unavailable for use in scripts.
