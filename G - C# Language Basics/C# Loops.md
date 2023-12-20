---
type: NoteCard
---

# C# Loops
Loops execute a block of code as long as a specified condition is true.

## While

```js
while (condition) 
{
  // code block to be executed
}
```

```js
int i = 0;
while (i < 5) 
{
  Console.WriteLine(i);
  i++;
}
```

## Do while

A do-while loop executes the code block once, before checking if the condition is true, then it will iterate as long as the condition is true.

```js
do 
{
  // code block to be executed
  // code block is executed first...
}
while (condition);
```

```js
int i = 0;
do 
{
  Console.WriteLine(i);
  i++;
}
while (i < 5);
```

## For

A for loop can be suitable when we know the number of iterations in advance.

```js
for (statement 1; statement 2; statement 3) 
{
  // code block to be executed
}
```

*   **Statement 1** is executed one time before the execution of the code block
*   **Statement 2** is executed every time and defines the condition for executing the code block (when it is true, otherwise we exit the loop)
*   **Statement 3** is executed every time after the code block has been executed

```js
for (int i = 0; i < 5; i++) 
{
  Console.WriteLine(i);
}
```

## Foreach

A foreach loop is used to loop through elements in an **array**:

```js
foreach (type variableName in arrayName) 
{
  // code block to be executed
}
```

```js
string[] fruits = { "Apple", "Banana", "Cherry" };

foreach (string fruit in fruits) 
{
  Console.WriteLine(fruit);
}
```

## Break

Similar, to switch, the `break` statement can be used to jump out of a **loop**. It is always used with a condition.

```csharp
for (int i = 0; i < 10; i++) 
{
  if (i == 4) 
  {
    break;
  }
  Console.WriteLine(i);
}
```

## Continue

Similar to skips the current iteration in the loop, if the specified condition is true, and continues with the next iteration in the loop.

```js
for (int i = 0; i < 10; i++) 
{
  if (i == 4) 
  {
    continue;
  }
  Console.WriteLine(i);
}
```