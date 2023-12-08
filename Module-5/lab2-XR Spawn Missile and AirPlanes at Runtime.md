---
type: NoteCard
---

# lab2-XR Spawn Missile and AirPlanes at Runtime
## Unit 1: Creating a scene

Create a scene that detects horizontal planes

Add the script PlaceObjectsOnPlane to XR Origin

Explore the script PlaceObjectsOnPlane in the Inspector and your code editor

Add the script DisableTrackedVisuals to XR Origin

Explore the script DisableTrackedVisuals in the Inspector and your code editor

## Unit 2: Placing objects on the plane

Our application can detect horizontal planes. That’s interesting but not that much useful.

Let us add the missile game object on the plane when the user taps it through the device.

Select XR origin and add script “Place Objects on Plane”

Notice the different attributes of the script “Place Objects on Plane”

One of the attributes is Spawner which is of type gameObject.

→ Right-Click on the scene’s name and add a gameObject called **Spawner** (select gameObject | Create Empty …)

→ Drag and drop this **Spawner** into its slot in “XR Origin | Place Objects on Plane”

Another one is ShootPlane, also of type gameObject.

→ Right-Click on the scene name and add a gameObject called **ShootPlane**

→ Drag and drop this **ShootPlane** into its slot in “XR Origin | Place Objects on Plane”

A third one is “Placed Prefab”, this will be the object that we will place on the plane.

→ Click on the donut next to the slot of the attribute, select assets from the popup tab, and search for the prefab “**missile variant**”, then double-click on it in the result search list to add it to the slot.

Another attribute is “Can reposition”

→ Uncheck this attribute if you want the object to state still in its original place after the first tap.

## Unit 3: Creating a spawner script

Create a script called Spawner inside the folder \_App/Scripts

Remove Start and Update callbacks

Add a static \`Instance\` property to make the script singleton

```js
public static Spawner Instance { get; private set; }
```

Add Awake callback function

Change the Awake callback function to assign `this` to `Instance (Instance = this;)` if it’s null otherwise destroy this (`Destroy(this);`).

Add the script to the gameObject **Spawner** (select Spawner in the Hierarchy window then click on Add Component and search for the script Spawner OR drag and drop the script as a component into the Inspector window of the gameObject).

## Unit 4: Building and testing the app

Build and deploy the app.

You should be able to

*   detect horizontal planes.
*   tap to add a missile object on the plane

The missile should rotate (randomly in place) when there is no target in the sky.

Double-click the prefab “missile variant” to open it in the Hierarchy window

Check the script “Turret AI” component.

Double-click on the script slot to open your code editor

Scan this script to locate the parts responsible for handling the object rotation

Add the missing code so that the missile rotate

You can build a test again to see the missile rotating

## Unit 5: Adding a plane prefab to the scene

In the **Spawner** script file, create a public property of type GameObject: redPlane

The object redPlane will be added to the scene at runtime at the same time as the missile object.

Select the gameObject Spawner in the Hierarchy window,

→ You should be able to see “Red Plane” property in the Inspector window

→ Click on \_App/Prefabs folder and drag and drop PathRedPlane into the slot of “Red Plane” property

We want to instantiate Red Plane at runtime but:

> The question is how we determine the position of the redPlane? Where can we place it in 3D space? We need XYZ coordinates.

For this, we can use the position of the missile as a reference and we place the plane at a specific position on the top of the missile.

So let’s create a variable (property) to store the missile position.

### Unit 4.1: Storing the missile position in Spawner

Create a private property called `missilePosition` of type `Vector3`. This will be the position of the missile on the plane

Create a public function called `setMissilePosition` it takes `Vector3 pose` as a parameter

```js
public void setMissilePosition(....)
{
  // ....
}
```

We make it public so that other scripts can access it.

Other scripts can call public functions.

### Unit 5.1: Setting the missile position

Remember the Script “Place Objects One Plane”. When the user taps on the screen, we get the position of the hit (using raycast) and we instantiate the missile at the hit position.

Open the script: explore once again this script. Locate when we get ***hitPose*** to instantiate **PlacedPrefab**.

Then, call `setMissilePosition`

```js
Spawner.Instance.setMissilePosition(hitPose.position);
```

### Unit 5.3: Spawning plane

Now we have the position of the missile set up. We can now create a function that instantiates a plane. This function will take a plane game object and instantiate it on the top of the missile.

Here is a function with some missing parts that you should complete:

```js
public void spawnPlane(GameObject plane)
{
// empty object to work with the transfrom
GameObject planeSpawnPoint = ??


// random height for the plane
// assign a random value between (range) 0.5f, 1.5f
float extraHeight = ??


// random depth for the plane's Z axis
// same, assign a random value between .5f, 1.5f
float extraDepth = ??

// plane position
Vector3 planeSpawnPosition = new Vector3(.0f, this.missilePosition.y + extraHeight, this.missilePosition.z + extraDepth);

// set the position of the spawn
planeSpawnPoint.transform.position = ??;

// instanciate a plane at the spawn position
Instantiate(plane, planeSpawnPoint.transform);

}
```

Add a function `spawnRedPlane` that uses `spawnPlane:`

```js
public void spawnRedPlane()
{
  spawnPlane(redPlane);
}
```

### Unit 4.4: Instantiating RedPlane

Ok. Now, we can call spawnRedPlane to instantiate RedPlane when we add the missile object to the scene.

Open the script: explore once again this script. Locate when we get ***hitPose*** to instantiate **PlacedPrefab**.

Call the function spawnRedPlane

```js
Spawner.Instance.spawnRedPlane();
```

### Unit 4.5: Building and testing the app

Build and deploy the app.

You should be able to

*   detect horizontal planes.
*   tap to add a rotating missile object on the plane
*   see the red airplane following a path

This is great, but the missile is rotating randomly. It should follow its targets airplanes (for now we have only the red one).

Double-click on the prefab “missile variant” and open the script “Turret AI” associated with it.

Check the function `FollowTarget`

Check the `Update` callback of the script

In the Update callback, we have the condition of currentTarget, we should call `FollowTarget` if the currentTarget is not null:

```js
if (currentTarget != null) 
{
// Todo 
// call follow target here
```

Now the missile object should follow the target redPlane.

You can build a test again to see the missile rotating.

## Unit 6: Spawning greenPlane and rainbowPlane prefabs

Repeat the same step as for redPlane to instantiate `greenPlane` and `rainbowPlane` prefabs in the scene

## Unit 7: Building and testing the app

Build and deploy the app to see if everything is working as expected.