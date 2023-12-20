---
type: NoteCard
---

# C# Arrays Data Types
Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value. Arrays are typed:

```js
int[] numbers = { 1, 2, 3, 4, 5 }; 
string[] fruits = { "Apple", "Banana", "Cherry" };
```

We access an array element by index number

```js
string firstElement = fruits[0];

Console.WriteLine(firstElement); // outputs Apple
```

We can change the value of a specific element by index number

```js
fruits[0] = "Papaya"
```

We can use `Length` to find the number of elements in an array

```js
Console.WriteLine(fruits.Length);
```

##