# Field & Property

Fields and Properties are a member of a class/interface/struct. They are used to define attributes of a class/interface/struct they belong into.


Although both field and properties can be used to do the same job, properties are the 99.99% go-to for attributes.

## Field & Property syntax

Field
```cs
class Person
{
    public int Age;
}
```

Property
```cs
class Person
{
    private int age;
    public int Age
    {
        get
        {
            return age;
        }
        set
        {
            age = value;
        }
    }
}
```

In properties, there are two new keywords you'll encounter, `get` and `set`. In this example, when you assign something to `Age`, the code within `set` is executed. And when you call `Age`, the code within `get` is executed.

Both of the above do the same thing, to provide the age of a person object.

## Usage of fields and properties

Let's say that I have a class called `Circle` and it has attributes named `Radius`, `Diameter` and `Circumference`.

Since diameter and circumference can be computed directly from radius itself, the best way to go along with this would be to implement 3 public properties that would expose a private `radius` field.
```cs
class Circle
{
    private double radius;
    
    public double Radius
    {
        get => radius;
        set => radius = value;
    }
    public double Diameter
    {
        get
        {
            return radius * 2;
        }
    }
    public double Circumference
    {
        get
        {
            return radius * 2 * Math.PI;
        }
    }
}
```

With this, you only need to write at `Radius` and then the change would immediately reflect at Diameter and Circumference.

Do note that in properties, when you don't define a `get`, you won't be able to call the value of that property, making it a write-only property. Respectively, by omitting the `set`, it'll become a read-only property.

By using a private field, you can use properties as a way to expose the values of those private fields and gives you the ability to perform validations through the property itself. This way, the information that should contain within that class, will remain within that class through the use of fields and properties.
