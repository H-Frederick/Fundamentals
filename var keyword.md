# var keyword

`var` is a keyword added to the C# language to allow implicit type local variables. They can only be declared inside body methods and makes your programs shorter and easier to read. The resulting type is determined by the compiler.

## Usage

```cs
public static void Main()
{
    var apples = 10;
    Console.WriteLine(apples); // 10
}
```

## Why var?

`var` saves you the hassle of typing long variable types in their declaration.

Instead of:
```cs
public static void Main()
{
    Dictionary<int, string> numbers = new List<int, string>();
}
```
It's a lot nicer to read this instead:
```cs
public static void Main()
{
    var numbers = new Dictionary<int, string>();
}
```

## Restrictions

- `var` cannot be assigned on `null`.
- `var` cannot be used on a field/property type, method return types/parameter types.
```cs
public class Person
{
    var Age { get; set; } // Although this obviously returns an int, this is not valid

    public var SayAge() // Replacing a method return type with var is not allowed
    {
        return Age;
    }
}
```