---
type: NoteCard
---

# lab3 - Unity GameObject
## Manipulating gameObjects at runtime

**GameObject** class represents any object that can exist in a **Scene.**

It provides methods to work with the scene’s object in code.

In a previous lab, we created a script that we attached using drag and drop or the “Add Component” button (in the Inspector) to a grameObject. Unity allows us to do the same using scripting.

Follow these steps to create a gameObject and attach a script to it at runtime:

1.  Create an empty gameObject in the scene
2.  Create a script MyGameObjectScrip
3.  Add the below code to the script
4.  Run the project

```js
public class MyGameObjectScript : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        // A new GameObject
        GameObject myObject = new GameObject("MyGameObject");

        // Add script to the GameObject
        myObject.AddComponent<MyGameObjectScript>();

        // Get Transform component of the GameObject
        Transform myTransform = myObject.transform;

        // Log info about the GameObject
        Debug.Log("Name: " + myObject.name);
        Debug.Log("Position: " + myTransform.position);
    }

    // Update is called once per frame
    void Update()
    {
        // Perform actions in each frame
    }
}
```