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
    private age;
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

In properties, there are two new keywords you'll encounter, `get` and `set`. In this example, when you assign something to `Age`, the code within `set` is called. And when you call `Age`, the code within `get` is called.

Both of the above do the same thing, to provide the age of a person.

## Usage of fields and properties

Let's say that I have a class called `Circle` and it has attributes named `Radius`, `Diameter` and `Circumference`.

Since diameter and circumference can be computed directly from radius itself, the most efficient way of  would be to implement 3 public properties that would expose a private `radius` field.
```cs
class Circle
{
    private double radius;
    
    public double Radius
    {
        get => return radius;
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

Do note that in properties, when you don't type out a `get`, you won't be able to call that property, since it'll become write-only. By omitting the `set`, it'll become read-only.

By using a private field, you can use properties as a way to expose those private fields. This way, the information that should contain within that class, will remain within that class through the proper use of fields and properties.