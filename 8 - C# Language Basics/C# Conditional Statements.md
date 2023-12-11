---
type: NoteCard
---

# C# Conditional Statements
C# provides many conditional statements to control the flow of a program based on certain logical conditions.

*   if condition
*   else-if condition
*   else condition
*   switch

## Logical statements

The condition should be a logical statement that resolves into a boolean, either true or false. Here are some examples:

*   Less than: x < y
*   Less than or equal to: 2 <= 5
*   Greater than: a > b
*   Greater than or equal to: p >= q
*   Equal to d == d
*   Not Equal to: a != z

## Conditions

*   Use `if` to specify a block of code to be executed, if a specified condition is true
*   Use `else` to specify a block of code to be executed, if the parent condition is false
*   Use `else if` to specify a new condition to test, if the parent condition is false
*   Use `switch` to specify many alternative blocks of code to be executed depending on the `case` statement

## Examples

```js
// if

int i = 10, j = 20;

if (i < j)
{
    Console.WriteLine("i is less than j");
}        

if (i > j)
{
    Console.WriteLine("i is greater than j");
}

// if else

int time = 3;
if (time <= 2) 
{
  Console.WriteLine("Good morning.");
} 
else 
{
  Console.WriteLine("Good afternoon.");
}
// Outputs "Good evening."

// if else if
int time2 = 22;
if (time2 < 10) 
{
  Console.WriteLine("Good morning.");
} 
else if (time2 < 18) 
{
  Console.WriteLine("Good afternoon.");
} 
else 
{
  Console.WriteLine("Good evening.");
}

int day = 5;
switch (day) 
{
  case 1:
    Console.WriteLine("Monday");
    break;
  case 2:
    Console.WriteLine("Tuesday");
    break;
  case 3:
    Console.WriteLine("Wednesday");
    break;
  case 4:
    Console.WriteLine("Thursday");
    break;
  case 5:
    Console.WriteLine("Friday");
    break;
  case 6:
    Console.WriteLine("Saturday");
    break;
  case 7:
    Console.WriteLine("Sunday");
    break;
}
// Outputs "Friday"
```