---
type: NoteCard
---

# What is OOP in C#?

C# is an object-oriented programming (OOP) language that supports various OOP features. OOP features are **_design patterns_** (meaning, good practices). We find them in almost all OOP languages. Here are some of the most important ones, with examples using C# syntax:

## Classes and objects

Classes are templates that define the properties and methods of objects. Objects are instances of classes.

```js
class Car
{
    // Properties
    public string Model;
    public int Year;

    // Method or behavior
    public void StartEngine()
    {
        Console.WriteLine("Engine started!");
    }
}
```

To create objects from a class (template)

```js
// Creating Car objects or instances
Car myCar = new Car();

Car myCar2 = new Car();
```

## **Encapsulation**

Encapsulation is the technique of enabling access to properties using well-defined methods, rather than direct access. Often, the access methods are the getters and setters. Encapsulation protects and isolates the code.

- A **getter** is a public method that enables read access to private property
- A **setter** is a public method that enables write access to private property

In the below example, the balance property is `private` and has a getter (`GetBalance`) and a setter (\`SetBalance\`).

```js
class BankAccount
{
    private decimal balance;

    // getter
    public decimal GetBalance()
    {
        return balance;
    }

   // setter
    public decimal SetBalance(decimal amount)
    {
        this.balance = amount;
    }

    public void Deposit(decimal amount)
    {
        balance += amount;
    }

    public void Withdraw(decimal amount)
    {
        if (amount <= balance)
            balance -= amount;
        else
            Console.WriteLine("Insufficient funds!");
    }
}
```

## Inheritance

Inheritance allows a class to inherit properties and methods of another class.

- The class that we inherit from is called a **superclass** or **base class**
- The class that inherits another class is called a **subclass** or **derived class**

::::cal
In most programming languages a class can inherit only one class. A pseudo-form of multiple inheritance can be achieved using interfaces.

::::

In C# we use “:” to implement inheritance

```js
class DerivedClass : BaseClass { /* ... */ }
```

```js
class Animal
{
    public void Eat()
    {
        Console.WriteLine("Animal is eating.");
    }
}

// Dog class will inherit methods that are not private.
// Here Eat method is inherited
class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog is barking.");
    }
}

Dog myDog = new Dog();

// inherited method
myDog.Eat()

myDog.Bark()
```

## **Polymorphism**

Polymorphism is a technique to use different types through a single interface. One approach to polymorphism is providing the same name of a function, with either different:

1.  Implementations,
2.  Return types, or
3.  Arguments (number or types)

The name of the function is the same, which provides a single interface for calling the function. During the execution, an implementation is selected depending on the actual context, return types, and arguments being referred to.

We can distinguish between two types of polymorphism.

- **Overloading**: When multiple methods in the same class have the _same name_ but different arguments (either a different number arguments of or different types of arguments)
- **Overriding**: When a subclass provides an implementation for a method that is already defined in its superclass (or interface)

```js
// *** Overloading ***
// -------------------

class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }

    public double Add(double a, double b)
    {
        return a + b;
    }
}

// Create an instance of the Calculator class
Calculator myCal = new Calculator();

// Use method overloading
int result1 = myCal.Add(5, 10);
double result2 = myCal.Add(3.5, 7.2);
```

```js
// *** Overriding ***
// -------------------

class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Animal makes a sound.");
    }
}

class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Dog barks.");
    }
}

// Create instances of Animal and Dog classes
Animal myAnimal = new Animal();
Dog myDog = new Dog();

// Use method overriding
myAnimal.MakeSound(); // Output: Animal makes a sound.
myDog.MakeSound();    // Output: Dog barks.
```

```js
// *** Similar to overriding, with interface ***
// ---------------------------------------------

interface IDrawable
{
    void Draw();
}

class Circle : IDrawable
{
    public void Draw()
    {
        Console.WriteLine("Drawing a circle.");
    }
}

class Square : IDrawable
{
    public void Draw()
    {
        Console.WriteLine("Drawing a square.");
    }
}

// Create instances of Circle and Square classes
IDrawable myCircle = new Circle();
IDrawable mySquare = new Square();

// Use polymorphic behavior
myCircle.Draw(); // Output: Drawing a circle.
mySquare.Draw(); // Output: Drawing a square.
```

## **Abstraction**

Abstraction involves representing complex entities or ideas using simpler interfaces. The goal is to hide the implementation details of an object and show only the relevant features (an API or what the object can do).

Abstraction can:

- Make system design (code) less complex, and
- Provide developers with a clear view of objects, interfaces, and their interactions

In the below example, we create an abstract class. An abstract class can declare an abstract method. An abstract method declares only the return type and arguments —not the implementation.

```js
// abstract class can have an abstract method
abstract class Shape
{
   // abstract method, there is no implementation
    public abstract void Draw();
}

class Circle : Shape
{
    public override void Draw()
    {
        Console.WriteLine("Drawing a circle.");
    }
}
```

## **Interfaces**

An interface declares a set of methods (their types and arguments) that classes should implement. An interface is like a contract for a complex type or an API. Similar to inheritance, we use “:” to implement interfaces.

::::cal
Unlike inheritance, a class can implement multiple interfaces.

::::

In the below example, `IDrawable` is an interface that declares the method `Draw`. The `Circle` class implements the interface and the Draw function.

```js
interface IDrawable
{
    void Draw();
}

class Circle : IDrawable
{
    public void Draw()
    {
        Console.WriteLine("Drawing a circle.");
    }
}
```

## Genericity

A technique for creating generic classes and methods that can work with multiple data types.

```js
// generic class

public class GenericClass<T>
{
    public T Value { get; set; }
}


// using it
GenericClass<int> integerClass = new GenericClass<int>();
integerClass.Value = 10;

GenericClass<string> stringClass = new GenericClass<string>();
stringClass.Value = "Hello";
```

```js
// generic method

public static T Add<T>(T x, T y)
{
    return x + y;
}

// using it
int sum = Add(5, 10);
double product = Add(3.5, 2.5);
```

```js
// generic interface

public interface IGenericInterface<T>
{
    void DoSomething(T parameter);
}

// implementing the interface ...
public class MyClass : IGenericInterface<int>
{
    public void DoSomething(int parameter)
    {
        Console.WriteLine("Parameter: " + parameter);
    }
}

// using ...

IGenericInterface<int> myObj = new MyClass();
myObj.DoSomething(5);
```

## Delegation

A technique by which an object delegates specific tasks to other objects. It enables modular collaboration between objects without having a direct dependency on each other.

```js
using System;

// Interface representing the task to delegate
public interface ISender
{
    void SendMessage(string message);
}


// Email implementation of the task
public class EmailSender : ISender
{
    public void SendMessage(string message)
    {
        // Send email logic goes here
    }
}

// SMS implementation of the task
public class SmsSender : ISender
{
    public void SendMessage(string message)
    {
        // Send SMS logic goes here
    }
}


// Class responsible for delegating tasks
public class MessageHandler
{
    private readonly ISender _sender;

    public MessageHandler(ISender sender)
    {
        _sender = sender;
    }

    public void HandleMessage(string message)
    {
        _sender.SendMessage(message);
    }
}

public class Program
{
    public static void Main()
    {
        var emailSender = new EmailSender();
        var smsSender = new SmsSender();

        var messageHandler = new MessageHandler(emailSender);
        messageHandler.HandleMessage("Email message");

        messageHandler = new MessageHandler(smsSender);
        messageHandler.HandleMessage("SMS message");
    }
}
```

## Reflection

Reflection is a technique that allows developers to inspect and interact with runtime metadata, such as:

- Types (classes, interfaces, enums, etc.), and
- Members (properties, methods, etc.)

For example, using reflection, developers can

- Inspecting types, and members: Retrieve runtime metadata, such as the types and members it contains, and even modify certain aspects of the assembly itself
- Creating and manipulating objects dynamically: Create instances of types at runtime and invoke their methods
- Extending existing libraries: Reflection can be used to extend existing libraries by adding new functionality to existing types

```js
using System;
// import Reflection package
using System.Reflection;

class Program
{
    static void Main()
    {
        Type type = typeof(string);

        // Display type information
        Console.WriteLine($"Type Name: {type.Name}"); // output: Type Name: String
        Console.WriteLine("Methods:");

       // output: all methods in String class
        foreach (MethodInfo method in type.GetMethods())
        {
            Console.WriteLine($"  {method.Name}");
        }
    }
}
```

```js
using System;
using System.Reflection;

class MyClass
{
    public void DisplayMessage()
    {
        Console.WriteLine("Hello, Reflection!");
    }
}

class Program
{
    static void Main()
    {
        Type type = typeof(MyClass);

        // Create an instance dynamically
        object instance = Activator.CreateInstance(type);

        // Invoke a method on the dynamically created instance
        MethodInfo method = type.GetMethod("DisplayMessage");
        method.Invoke(instance, null);
    }
}
```
