---
type: NoteCard
---

# lab4 - Unity Transform
## Accessing and manipulating Transform component

In Unity Transform is the component that represents: the position, rotation, and scale of an object. In scripts, Transfrom is exposed as an API to work with transform components.

All gameObjects have a transform component attached to them.

```js
public class TransformExample : MonoBehaviour
{
    // Reference to another GameObject
    public GameObject targetObject;

    // Start is called before the first frame update
    void Start()
    {
        // Accessing the Transform component of the current GameObject
        Transform myTransform = transform;

        // Check if the targetObject is not null
        if (targetObject != null)
        {
            // Accessing the Transform component of the targetObject
            Transform targetTransform = targetObject.transform;

            // Perform operations with transforms
            myTransform.position = targetTransform.position;
            myTransform.Rotate(Vector3.up, 45f);
        }
    }

    // Update is called once per frame
    void Update()
    {
        // Perform actions in each frame
    }
}
```