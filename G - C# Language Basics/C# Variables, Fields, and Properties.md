---
type: NoteCard
---

# C# Variables, Fields, and Properties
## Variables

A variable is a container of a value. We declare variables to store values that we accessed and modify in a program.

In C#, variables are typically defined inside functions or blocks of code, and they only exist during the execution of that function or block. Once the function or block finishes executing, variables are cleaned out.

We can use keywords, such as `var` to declare variables. “Var” is a shorthand for “let” with the type; the compiler will infer the type of the variable.

```js
var speed = 3.3f;
var index = 3;
var amount = 2.2;
```

We can also create typed variables such as:

```js
float speed = 3.3f;
int index = 3;
double amount = 123.4567890123456789;
bool isCheck = true;
char firstChar = 'a';
string name = "hello C#";
```

## Fields

In C#, fields are variables that are declared within a class. Like variables, they are used to store data. However, they have visibility:

```js
public class MyClass
{
    // public field
    public int myField;

    
}
```

## Properties

Properties are methods to access the state of an object by encapsulating fields. They consist of a getter or a setter.

```js
public class MyClass
{
    // Private field
    private int myField;

    // Property with getter and setter
    public int MyProperty
    {
        get { return myField; }
        set { myField = value; }
    }

    // Auto-implemented property (shortened syntax)
    public string AnotherProperty { get; set; }
}
```