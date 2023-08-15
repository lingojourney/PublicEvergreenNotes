## Regex replace and capture groups in PowerShell 🌿

Regular Expressions (Regex) are a powerful way to parse, analyze and manipulate text. In PowerShell, Regex is often used in conjunction with the `-replace` operator to find and replace text in strings. When using `-replace`, you can also use capture groups to manipulate or reformat parts of the string. Here's how you do it.

Let's say we have a string that contains dates in the format `MM/DD/YYYY`, but we want to change them to `YYYY-MM-DD`. We can use Regex replace with capture groups to accomplish this.

```powershell
# Original string
$string = "Today's date is 06/15/2022"

# Use regex replace with capture groups
$newString = $string -replace '(\d{2})/(\d{2})/(\d{4})', '$3-$1-$2'

# Print new string
Write-Output $newString"
```

In the regular expression `(\d{2})/(\d{2})/(\d{4})`, we're defining three capture groups:

1. `(\d{2})` matches any two digits (the month)
2. `(\d{2})` matches any two digits (the day)
3. `(\d{4})` matches any four digits (the year)

In the replacement pattern `$3-$1-$2`, we're referencing these capture groups:

1. `$3` refers to the third capture group (the year)
2. `$1` refers to the first capture group (the month)
3. `$2` refers to the second capture group (the day)

So, this script changes "Today's date is 06/15/2022" into "Today's date is 2022-06-15".

This technique can be very useful when you need to find and replace text in strings, especially when dealing with patterns or formats. 

## Calculating the Sum of an Array

In PowerShell, you can calculate the sum of an array using the `Measure-Object` cmdlet along with the `-Sum` parameter. Here is an example:

```powershell
PS> $numbers = 1, 2, 3, 4, 5
PS> $numbers | Measure-Object -Sum

Count    : 5
Average  :
Sum      : 15
Maximum  :
Minimum  :
Property :
```

As you can see in the above output, the sum of the numbers in the `$numbers` array is calculated and displayed.

It's important to note that `Measure-Object` will provide other statistical information such as count (number of elements), average, maximum and minimum values. If you only want to retrieve the sum, you can do so by adding `.Sum` to your command like so:

```powershell
PS> ($numbers | Measure-Object -Sum).Sum
15
```

## Using `-join` Operator

The `-join` operator in PowerShell provides a simple way to concatenate or join array elements into a single string. You simply specify the separator you want to use between each element. 

For example:

```powershell
PS> $names = "John", "Jane", "Doe"
PS> $names -join ", "
John, Jane, Doe
```

In this example, we have an array `$names`, and we use `-join ", "` to concatenate all the elements in this array into a single string with each element separated by a comma followed by a space.

This operator is very helpful when you need to convert an array into a string for presentation or further processing.

## Conclusion

PowerShell is a powerful scripting language that offers several features that make it easier for users to manipulate data and automate tasks. By understanding how these features work such as regex replace and capture groups, ExpandProperty of Select , calculating sum of arrays and using `-join` operator , users can create more efficient scripts and save time on manual tasks.

## ExpandProperty of Select


The ExpandProperty parameter of the Select-Object cmdlet in PowerShell allows you to expand and display the properties of an object within the object itself.

For example, if you have an object with a property that itself contains multiple properties (like a nested object), the ExpandProperty parameter allows you to access and display those nested properties. Without using ExpandProperty, PowerShell would just display the top level property value.

Here's an example:

```powershell
# Without ExpandProperty
PS> Get-Process | Select-Object -First 1

Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    892      57    14712      21164       0.73   3996   1 ApplicationFrameHost

# With ExpandProperty
PS> Get-Process | Select-Object -ExpandProperty Modules -First 1

ModuleName: clr.dll
FileName:   C:\Windows\Microsoft.NET\Framework64\v4.0.30319\clr.dll
BaseAddress:0x7ff98b2d0000
ModuleMemorySize:24117248
FileVersionInfo: File:             C:\Windows\Microsoft.NET\Framework64\v4.0.30319\clr.dll
                 InternalName:     clr.dll
                 OriginalFilename: clr.dll
                 FileVersion:      4.8.4300.0 built by: NET48REL1LAST_C 
                 FileDescription: Microsoft .NET Runtime Common Language Runtime - WorkStation 
                 Product:          Microsoft® .NET Framework 
```

As you can see, without `ExpandProperty`, we only see the basic information for each process. But with `ExpandProperty`, we can dive into the `Modules` property of each process and see more detailed information about each module being used by that process.

So in short, `ExpandProperty` lets you "dig into" nested properties in PowerShell objects, making it easier to work with complex data structures.