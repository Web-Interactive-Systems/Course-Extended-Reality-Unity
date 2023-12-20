---
type: NoteCard
---

# What is C#?
C# (pronounced C-sharp) is an Object-Programming Language (OOP) developed by Microsoft, as part of the .NET framework. **Unity** uses [Mono](https://www.mono-project.com/), an open-source runtime of C#. Mono is based on the [ECMA](https://ecma-international.org/) standard of C#.

ECMA is an international industry association dedicated to the standardization of information and communication systems. ECMA maintains specifications for different systems and languages, including, for example, ECMAScript, the standard for JavaScript.

## Features of C\#

*   OOP
*   Static typing (see Static Typing in C\\# )

## Example of C# program

Here is an example of a C# program. Don’t worry if you don’t understand all the features of the language. Just follow along, we will get into most aspects in the following units.

```js
// Import System collections
using System.Collections;

// Define a class named MoveCare
public class MoveCare
{
    // Public variable to represent care health, with an initial value of 5
    public float careHealth = 5;

    // Private variable to track whether the care is destroyed
    private bool isDestroyed = false;

    // Method to apply damage to the care's health
    void ApplyDamage(float damage)
    {
        // Decrease careHealth by the specified damage amount
        careHealth -= damage;

        // Check if careHealth is less than or equal to 0 and the care is not already destroyed
        if (careHealth <= 0 && !isDestroyed)
        {
            // Set the isDestroyed flag to true
            isDestroyed = true;

            // Call the Destroying method to handle destruction-related logic
            Destroying();
        }
        else
        {
            // If the care is not destroyed, call the Damaging method to handle damage-related logic
            Damaging();
        }
    }

    // Virtual method to handle damage-related logic (to be overridden by derived classes)
    public virtual void Damaging()
    {
        // This method can be overridden in derived classes to implement custom damage logic for the care
    }

    // Virtual method to handle destruction-related logic (to be overridden by derived classes)
    public virtual void Destroying()
    {
        // This method can be overridden in derived classes to implement custom destruction logic for the care
    }
}
```

## Learn more

*   link 1
*   link 2
*   link 3