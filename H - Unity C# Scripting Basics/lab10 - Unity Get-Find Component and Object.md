---
type: NoteCard
---

# lab10 - Unity Get-Find Component and Object
Script allows us to find and interact with the components of a gameObject.

## Using GetComponent

As its name suggests, GetComponent finds a component that is attached to a gameObject.

Following on our CubeMover script, let’s get the MeshRenderer attached to the Cube:

```js
void Update()
    {
// get MeshRenderer component. Notice GetComponent is a generic function that taks a type. It will get the first component
        var meshRenderer = GetComponent<MeshRenderer>();

        // Check to make sure that it's valid before we use it
        if (meshRenderer == null)
        {
            return;
        }

        var sineTime = Mathf.Sin(Time.time) + 1 / 2f;
        var color = new Color(sineTime, 0.5f, 0.5f);
        meshRenderer.material.color = color;

        var movement = direction * speed;

        movement *= Time.deltaTime;

        this.transform.Translate(movement);
    }
```

## Variants of GetComponent

There are different variants of GetComponent.

For information about them check Unity documentation: <https://docs.unity3d.com/ScriptReference/30_search.html?q=GetComponent>

## Using FindObjectOfType

Script allows us to find and interact with the objects of other gameObjects.

`FindObjectOfType`: find a random object by type in a scene

`FindObjectsOfType`: find all objects by type in a scene

::::cal
These functions will,

*   Return null if no object is found
*   Return only active objects

::::

```js
var mover = FindObjectOfType<Cube>();
```

## Optimization

It is often recommended to initialize variables only once in the Awake() or Start() callbacks. In our example, instead of calling `var meshRenderer = GetComponent<MeshRenderer>();` on each rerendener (Update), we can do it in Awake() or Start().