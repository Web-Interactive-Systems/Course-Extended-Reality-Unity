---
type: NoteCard
---

# lab5-Unity Vector
In Unity we use vectors to manipulate positions, directions, and distances of objects in the scene. There are different classes in unity to work with vectors.

**Vector2:** <https://docs.unity3d.com/ScriptReference/Vector2.html>

**Vector3:** [https://docs.unity3d.com/ScriptReference/Vector3.html](https://docs.unity3d.com/ScriptReference/Vector2.html)

**Vector3.magnitude:** [https://docs.unity3d.com/ScriptReference/Vector3-magnitude.html](https://docs.unity3d.com/ScriptReference/Vector2.html)

**Vector3.Dot:** <https://docs.unity3d.com/ScriptReference/Vector3.Dot.html>

`Vector3`, a commonly used classes, represents points and vectors in 3 dimensional space (x, y, z) (more info: <https://docs.unity3d.com/ScriptReference/Vector3.html>)

```js

public class CubeSpinner : MonoBehaviour {

    float speed = 50.0f;

    void Update() {
      transform.Rotate(Vector3.right * Time.deltaTime * speed);
    }
}
```