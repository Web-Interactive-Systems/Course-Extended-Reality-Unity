---
type: NoteCard
---

# lab6 - Unity Time
In Unity and generally, in all computer graphics, images are rapidly (re)-rendered to give the impression of movement and smoother change.

Let’s consider the analogy of a **flipbook**. Each page of the flipbook is like a frame in a video game. When you flip through the pages quickly, the images appear to move.

**Frame rate** is how many times you flip through the flipbook each second. A higher frame rate means the images appear to move smoothly.

**Time.deltaTime** is like the amount of time between each page flip. It tells you how long it took to draw the current frame and get ready to draw the next one.

**Why do we need to use Time.deltaTime?**

Sometimes, we want things in our games to move at a constant speed, no matter how fast or slow the computer is running (**fps-independent**). For example, we might want a car to move at 50 miles per hour no matter how many frames per second the game is running.

To do this, we use Time.deltaTime to tell the car how far it should move each frame (**distance over time**). For example, if Time.deltaTime is 0.016 seconds, then we would tell the car to move 0.8 miles (50 miles per hour * 0.016 seconds per hour).

Here is an example of how to use Time.deltaTime to move a Cube:

```js
public class CubeMover : MonoBehaviour {

    public float speed = 50;

    void Update() {
        transform.Translate(speed * Time.deltaTime * Vector3.forward);
    }
}
```