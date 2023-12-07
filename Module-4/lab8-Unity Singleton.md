---
type: NoteCard
---

# lab8-Unity Singleton
Sometimes in Unity, we need to create a class that is instantiated only once. We call this type of class a `singleton`. Typical use cases for singleton classes are scene managers and spawners.

```js
public class GoalManager : MonoBehaviour
{
    public static GoalManager instance;

    void Awake()
    {
        instance = this;
    }

    public void OnInit()
    {
        Debug.Log("[GoalManager:Singleton] init");
    }

    // Accessing methods
    // GoalManager.instance.OnInit();
}
```