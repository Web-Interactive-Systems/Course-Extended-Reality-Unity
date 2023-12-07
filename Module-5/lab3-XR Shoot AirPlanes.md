---
type: NoteCard
---

# lab3-XR Shoot AirPlanes
## Unit 2: Shooting AirPlanes

In the previous module, we created a gameObject ShooPlane which is part of the missile variant prefab. It’s time to create a script for this gamaObject.

### Unit 2.1: Create a shooting script

In the folder \_App/Scripts create a script called **Shoot**

Add a public property missile to the script

```js
public GameObject missile;
```

### Unit 2.2: Adding shooting logic when the user touches the screen

Will use some Unity APIs

Input: an API to work with the user’s input, touch, keyboard, etc.

Here is an indented algorithm that we should implement (in Unity terms):

1.  Check if there is any touch interaction: Input.touchCount > 0, then

    1.  Get the first touch: Touch touch = Input.GetTouch(0);

    2.  Check if a touch has begun: touch.phase == TouchPhase.Began, then

        1.  Create a raycast to get the collision point between the user's touch and a game object: RaycastHit hit;

        2.  Create a ray from camera to the touch point: Ray ray = Camera.main.ScreenPointToRay(touch.position);

        3.  Create a variable to store hit on touch: bool hitOnTouch = Physics.Raycast(ray, out hit);

        4.  Check if hit on touch is true: hitOnTouch, then

            1.  log what was hit: Debug.Log("Touch on hit: " + [hit.transform.name](http://hit.transform.name));
            2.  Assign the touched gameObject to the currentTarget of the missile’s TurretAI script: missile.GetComponent\<TurretAI>().currentTarget = hit.transform.gameObject;
            3.  Call shoot function: missile.GetComponent\<TurretAI>().Shoot(hit.transform.gameObject);

        5.  Otherwise, log: Debug.Log("Nothing was hit");

Implement this algorithm in the Update method.

## Unit 3: Building and deploying the app

Build and deploy the app.

You should be able to:

*   detect horizontal planes
*   tap to add a rotating missile object on the plane
*   see the airplanes following their paths
*   touch a plane to shoot it

The plane does not explode

## Unit 4: Adding collision effects

The prefab “Bullet\_Missle Variant” has

*   the projectile script, and
*   capsule collider

The collider will a callback OnTriggerEnter when there is a collision with other objects

Check the projectile script

Locate the callback OnTriggerEnter

Notice the condition that checks if the bullet collided with RedPlane

```js
if (other.transform.tag == "RedPlane")
```

If so, destroy the collided object (which is the “other”) then call the Explosion function

```js
Destroy(other.transform.gameObject);
Explosion();
```

## Unit 5: Building and deploying the app

Build and deploy the app.

What do you notice?

RedPlane is destroyed when we shoot it.

Other planes are not destroyed.

Check the Projectile script

Locate the callback OnTriggerEnter

Complete the following conditions, to consider other types of planes

```js
if (other.transform.tag == "RedPlane")
```

Build, deploy, and test the app.

Notice that when a plane is destroyed it is not re-created again. Let’s do that.

## Unit 6: Spawning new AirPlane after shooting it

Open the Spawner script.

Create a function

```js
public void spawnRedPlaneAfterTime(float time)
{
  Invoke("spawnRedPlane", time);
}
```

Open Projectile script

Inside the condition of OnTriggerEnter callback

Add anther condition if other.transform.tag, then == “RedPlane”, then

Call Spawner.Instance.spawnRedPlaneAfterTime(2.0f);

Do the same work to spawn other planes.

## Unit 7: Building and testing

Build, deploy, and test the app.

## Unit 8: Adding a debugging script LogToScreen

Analyze the following script to understand it:

```js
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class LogToScreen : MonoBehaviour
{
	uint qsize = 15;
	Queue logQueue = new Queue();


	// Start is called before the first frame update
	void Start()
	{
		Debug.Log("start logging...");
	}

	void OnEnable()
	{
		Application.logMessageReceived += HandelLog;

	}

	void OnDisable()
	{
		Application.logMessageReceived -= HandelLog;
	}

	void HandelLog(string logString, string stackTrace, LogType type)
	{
		logQueue.Enqueue("" + type + ": " + logString);

		if (type == LogType.Exception) {
			logQueue.Enqueue(stackTrace);
			while (logQueue.Count > qsize) {
				logQueue.Dequeue();
			}
		}

	}

	void OnGUI()
	{
		GUILayout.BeginArea(new Rect(Screen.width - 400, 0, 400, Screen.height));
		GUILayout.Label("\n" + string.Join("\n", logQueue.ToArray()));
		GUILayout.EndArea();
	}
}
```

Create an empty game object add LogToScreen to the scene

Attach the debug script to the gameObject LogToScreen

## Unit 9: Building and testing

Build, deploy, and test the app.