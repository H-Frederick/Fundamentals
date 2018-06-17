# Method

A method is a member of a class/interface/struct. It contains a series of statements that a program executes when the method is called.

## Method syntax

- By default, a method *must* have a return type and a method name followed by a parenthesis and brackets.
```
ReturnType MethodName()
{
    // statements for the method to do
}
```
For example:
```cs
void SayHello()
{
    Console.WriteLine("Hello");
}
```

- Optionally, a method declaration may contain access modifiers(`public`, `private` etc.) and method parameters.
```
AccModifier ReturnType MethodName(Param1, Param2)
{
    // statements
}
```
For example:
```cs
class Car
{
    public void Start()
    {
        Console.WriteLine("Vroom");
    }

    public int PressHorn(int timePressed) // returns how loud your honk was
    {
        Honk(timePressed);
        int volume = timePressed * 2;
        return volume;
    }

    private void Honk(int strength)
    {
        Console.WriteLine("Honk!");
    }
}
```

## Method Overloading

Method overloading is used if you want a method to take different sets of parameters, while having the same return type.

```cs
class ComputerMouse
{
    public void ScrollUp()
    {
        // Scrolls up
    }

    public void ScrollUp(int amountOfTicks)
    {
        // scrolls up by amountOfTicks
    }

    public void ScrollDown() { }
    public void ScrollDown(int amountOfTicks) { }

    public string Click(string button)
    {
        return "You have clicked using the " + button + " button";
    }

    public string Click(string button, int timesClicked)
    {
        return "You have clicked " + timesClicked + " times using the " + button + " button";
    }
}
```

## When using methods...

- If a method has a return type that is not `void`, there must be at least one `return` statement within that method
- If your method returns multiple values of the same type, try returning it as an array or a list.
- If your method returns multiple values of different types, look at using the `out` keyword, which is explained [here.](https://github.com/CSharpBooks/Fundamentals/blob/master/Understanding%20the%20difference%20between%20value%20and%20reference%20types.md#ref-in-and-out-keywords)