# Be.IO

Be.IO is a fast big-endian implementation of .NET's BinaryReader and BinaryWriter.

## Installation

    Install-Package Be.IO

## Supported Platforms

Just about every platform is supported, including:

- .NET Framework 4.5+
- Windows 10 Universal apps
- Portable Class Libraries
- ASP.NET Core
- Xamarin.iOS
- Xamarin.Android
- Mono (Mac/Linux)
- Windows 8.1 and 8.0
- Windows Phone 8.1
- Silverlight

## Getting Started

First, add this using statement at the top of your file:

```csharp
using Be.IO;
```

After that, you can use `BeBinaryWriter` and `BeBinaryReader` the same way you would use a regular binary reader/writer. Example:

```csharp
using (var file = File.Open(@"C:\foo.txt", FileMode.Create))
{
    var writer = new BeBinaryWriter(file);
    writer.WriteInt16(0x1357);
    writer.WriteInt32(0xDEADBEEF);
    writer.WriteInt64(long.MinValue);
    
    var reader = new BeBinaryReader(file);
    short s = reader.ReadInt16();
    int i = reader.ReadInt32();
    long l = reader.ReadInt64();
}
```
