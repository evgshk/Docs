# Platform Invoke Examples

The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument. In the examples, the [DllImportAttribute.CharSet](https://docs.microsoft.com/en-us/dotnet/api/system.runtime.interopservices.dllimportattribute.charset) field is set to **Auto** to let the target platform determine the character width and string marshaling.

```csharp
using System;
using System.Runtime.InteropServices;

public class Win32 {
     [DllImport("user32.dll", CharSet=CharSet.Auto)]
     public static extern IntPtr MessageBox(int hWnd, String text, 
                     String caption, uint type);
}

public class HelloWorld {
    public static void Main() {
       Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0);
    }
}
```

For additional examples, see [Marshaling Data with Platform Invoke](https://docs.microsoft.com/en-us/dotnet/framework/interop/marshaling-data-with-platform-invoke).

