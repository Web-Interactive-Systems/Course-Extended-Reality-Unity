---
type: NoteCard
---

# lab7-Unity Random
In Unity, we often needs to generate random data. For example, games rely on randomness to have more dynamic and/or realistic scenarios and effects.

`Random` is an important class for random data in unity. It is part of UnityEngine.Random.

```js
public class RandomScript : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        // Generating a random number between 0.0 and 1.0
        float randomValue = Random.value;

        // Generating a random integer between 1 and 10
        int randomInt = Random.Range(1, 11);

        // random floating point
        float extraHeight = Random.Range(0.5f, 1.5f);
    }

    // Update is called once per frame
    void Update()
    {
        // Perform actions in each frame
    }
}
```

Unity’s Random class is kind of “global” random values generator per game.

Sometime, we might need independant random values generator. For this we can use C# native Random class, which is part of System.Random. Here is an example that generate random indices:

```js
List<int> RandomizeIndices(int indicesCount, int intCount)
    {
        // Create a random number generator
        System.Random random = new System.Random();


        List<int> indices = new List<int>();

        // Loop until three items are selected
        while (indices.Count < indicesCount && indices.Count < intCount)
        {
            // Generate a random index
            int index = random.Next(intCount);

            // If the index has not been selected before, add it to the HashSet
            if (!indices.Contains(index))
            {
                indices.Add(index);
            }
        }

        return indices;
    }
```