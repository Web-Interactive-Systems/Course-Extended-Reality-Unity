---
type: NoteCard
---

# C# Visibility
Visibility in C# refers to the accessibility or scope of members of a class (or struct), such as fields, methods, and properties. C# provides several access modifiers to determine which parts of the code can access a particular member. The primary access modifiers are:

1.  **public:** The member is accessible from any other code
2.  **private:** The member is accessible only within the body of the class or the struct in which it is declared
3.  **protected:** The member is accessible within its declaring class or struct and by derived classes (inheritance)

Here, PublicField and PublicMethod are accessible from anywhere, including outside the class:

```js

public class MyClass
{
    // Public field
    public int PublicField = 10;

    // Public method
    public void PublicMethod()
    {
        Console.WriteLine("This is a public method.");
    }
}
```

Here, PrivateField and PrivateMethod are only accessible within the MyClass class:

```js

public class MyClass
{
    // Private field
    private int PrivateField = 20;

    // Private method
    private void PrivateMethod()
    {
        Console.WriteLine("This is a private method.");
    }

    // Public method calling the private method
    public void AccessPrivateMethod()
    {
        PrivateMethod(); // Accessible within the same class
    }
}
protectedField and ProtectedMethod are accessible in the MyDerivedClass because it derives from MyBaseClass.
```

Here ProtectedField and ProtectedMethod are accessible in the MyDerivedClass because they derive from MyBaseClass.

```js
public class MyBaseClass
{
    // Protected field
    protected int ProtectedField = 30;

    // Protected method
    protected void ProtectedMethod()
    {
        Console.WriteLine("This is a protected method.");
    }
}

public class MyDerivedClass : MyBaseClass
{
    // Public method calling the protected method
    public void AccessProtectedMethod()
    {
        ProtectedMethod(); // Accessible in derived class
    }
}
```