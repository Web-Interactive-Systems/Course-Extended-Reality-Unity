---
type: NoteCard
---

# lab2 - Unity Callbacks
## Callbacks and their order

Unity provides different callbacks with different timing.

*   Start: called once on the first frame when the script is active
*   Update: called every frame
*   Awake: called once before the start callback (best for initializations)
*   LateUpdate: called every frame after the Update callbacks

## Frame rate-independent behavior

The Update callback runs every frame, depending on the frame rate of the project (frame rate).

Sometimes we need to control the Update. In our CubeMover example, the translation speed will differ depending on the frame rate, which might cause inconsistencies between devices. We can control for this by normalizing the behavior using Time.deltaTime:

```js
void Update()
    {
        var movement = direction * speed;

        movement *= Time.deltaTime;

        this.transform.Translate(movement);
    }
```

*   `Time.deltaTime`: represents the amount of time elapsed since the last frame.
*   `movement *= Time.deltaTime`: represents a distance over time (not a fixed distance).