---
type: NoteCard
---

# lab9 - Unity Debug
Debugging is an essential skill for any programmer, and it's especially important for game developers in Unity. When you're working on a game, you're constantly adding new features and fixing bugs. Debugging helps you find and fix those bugs quickly and efficiently.

Unity provides several debugging tools

**Using Unity Debug Mode**

In Unity, you can debug C# code using Unity debug mode. You can learn more about it here: <https://docs.unity3d.com/Manual/ManagedCodeDebugging.html>.

**Using the Console Window**

1.  Open the Console window by clicking on the Window menu and selecting General | Console.
2.  Use the Debug.Log() method to print debug messages to the Console window.
3.  Observe how the debug messages are printed to the Console window as the code executes.

```js
public class DebugScript : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        // Generating a random number between 0.0 and 1.0
        float randomValue = Random.value;

        // Generating a random integer between 1 and 10
        int randomInt = Random.Range(1, 11);

        // Output random values
        Debug.Log("Random Value: " + randomValue);
        Debug.Log("Random Integer: " + randomInt);

        // Debugging information
        Debug.Log("This is a debug message.");

        // Printing a formatted message
        Debug.LogFormat("Random Value: {0}, Random Integer: {1}", randomValue, randomInt);
    }

    // Update is called once per frame
    void Update()
    {
        // Perform actions in each frame
    }
}
```