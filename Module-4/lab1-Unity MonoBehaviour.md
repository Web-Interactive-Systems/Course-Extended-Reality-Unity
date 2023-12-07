---
type: NoteCard
---

# lab1-Unity MonoBehaviour
Scripting is the programming approach in Unity. It allows us to have more controls on GameObjects in a scene. This includes creating behaviors, interactions, and instanciating GameObjects at runtime. Unity support different languages for scripting. But the native scripting language is C#.

::::cal
You want to add different behaviors to GameObjects, like a car that runs, a plane that flys, etc. The way to do so is using scripting.

::::

## Script component or **MonoBehaviour**

In Unity, a gameObject is a container of components. Components are the building blocks that apply differnent logics to objects. There are different types of components that we can apply to grameObjects.

**MonoBehaviour** is *the script component* type. A script component will be then attached to a the gameObject, and participate in the gameObject’s update loop (code that runs every fame).

## Creating a script

1.  Create a new scene called CubeMoverScene
2.  Create a new 3D Cube GameObject
3.  Position the the cube in front of the camera
4.  Go to script folder and create a C# Script called CubeMover
5.  Double click the script. Unity will open it in your editor.

```js
using System.Collections; System.Collections.Generic;
using UnityEngine;

public class CubeMover : MonoBehaviour
{
    // Start callback will be called once at the start up of the script
    void Start()
    {

    }

    // Update callback will be called every frame
    void Update()
    {

    }
}
```

::::cal
Unity requires that the name of the script file matches the name of the class of the script.

::::

## Add logic to a script

Let’s modify the script:

```js
public class CubeMover : MonoBehaviour
{
    public Vector3 direction = Vector3.up;

    public float speed = 0.001f;

    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        var movement = direction * speed;
        this.transform.Translate(movement);
    }
}
```

*   `Vector3` represents points and vectors in 3 dimensional space (x, y, z) (more info: <https://docs.unity3d.com/ScriptReference/Vector3.html>)
*   `float speed = 0.001f` creates a floating number (notice `f`)
*   `Transform (see: this.transform(...))`represents position, rotation, and scale of an object (more info: <https://docs.unity3d.com/ScriptReference/Transform.html>)

## Attach a script to an object

To attach a script to an object you can drag and drop the script on the object or drag and drop the script on the inspector editor of the object

::::cal
All public variables declared in a script are visible in the inspector.

::::

## Run the scene

Run the scene to see the effect of the script on the cube.