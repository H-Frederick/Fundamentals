# Class

A class defines an object's structure. It contains fields, properties, methods, events etc.

They are declared inside namespaces, like this:
```cs
namespace HelloWorldEnterprise
{
    class Program
    {
        // members here
    }
}
```

In practice, it is best to only have 1 class per class file.

## Members of a class

For what members a class could contain, [here is a complete list.](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/members)

## Types of classes
- 'regular' classes

With a regular class, you can create as many instances as you want. And if you want to use the members within it, you have to instantiate an object of the class first.

E.g.:
```cs
class Person
{
    public void Shout()
    {
        Console.WriteLine("*shouts in this instance*");
    }
}

public void Main()
{
    Person p = new Person(); // Creating an instance of Person class
    Person.Shout(); // And then using the methods within it
}
```

- static class

Unlike a regular class, there could only be ONE instance of the static class. Thus, there is no need to instantiate them and the members of a static class must be static as well. When calling it's members, you must type the class name first followed by a dot.

```cs
static class Person
{
    public static void Shout()
    {
        Console.WriteLine("*shouts in a static instance*");
    }
}

public void Main()
{
    Person.Shout(); // calls the shout method
}
```

- abstract class

An abstract class is a class that cannot be instantiated. It can contain the same members as a class would, but methods have to be overriden when inheriting from an abstract class.

```cs
abstract class Example
{
    public abstract void Say();
}

class SomeClass : Example
{
    public override void Say()
    {
        Console.WriteLine("Hidden Message");
    }
}
```

- sealed class

In C#, a sealed class is a class that cannot be inherited. Usually, it is used to mark classes as if saying "There should be nothing else inheriting this class".
```cs
sealed class Test
{
    // members go here
}
```