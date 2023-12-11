---
type: NoteCard
---

# C# Non-Primitive Data Types
## Class

Also explained in C# OOP unit, classes are template types that encapsulate fields (data) and methods.

```js
class Game

{

// Fields

public string Name;

public int Score;

// Constructor

public Game(string name, int score)

{

Name = name;

Score = score;

}

// Method

public void DisplayInfo()

{

Console.WriteLine($"Name: {Name}, Score: {Score}");

}

}

// Creating an instance of the class

Person game = new Game("Sara", 30);

// Accessing fields and invoking methods

string gameName = game.Name;

game.DisplayInfo();
```

## Structure

A structure type (or struct type) is a value type that can encapsulate data and related functionality.

```js
public struct Coords

{

public Coords(double x, double y)

{

X = x;

Y = y;

}

public double X { get; }

public double Y { get; }

public override string ToString() => $"({X}, {Y})";

}
```

## Enumeration

An enumeration type (or enum type) is a value type defined by a set of named integral constants, representing a group of related values.

```js
enum Days

{

Sunday, // 0

Monday, // 1

Tuesday, // 2

Wednesday, // 3

Thursday, // 4

Friday, // 5

Saturday // 6

}
```

## Collections

C# allows many types of collections to handle groups of related objects, such as List, SortedList, ArrayList, Stack, Queue, Dictionary, and Hashtable.

You can learn more about them here:

<https://www.tutorialsteacher.com/csharp/csharp-collection>