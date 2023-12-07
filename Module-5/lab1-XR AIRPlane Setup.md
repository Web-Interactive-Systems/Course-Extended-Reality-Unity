---
type: NoteCard
---

# lab1-XR AIRPlane Setup
This is a project created using the URP template and integrates AR Foundation.

## Unit 1: Clone and open the project

1.  Clone the project: [Todo]
2.  Add the project to your Unity hub
3.  Open the project in Unity

## Unit 2: Set up

1.  Make sure that the build support for mobile is all setup

    1.  Android platform
    2.  Target Platform: make sure your build platform is android
    3.  XR Plugin: make sure the ARCore plugin is installed, Edit | Project Settings, then select XR Plug-in Management (check project validation for errors)
    4.  USB Debugging: make sure you enable debug mode on your mobile device

2.  Build and deploy the project

## Unit 3: Explore Plane Prefabs

1.  Create and open a new scene called PrefabsScene
2.  Add the prefab PathRainbowPlane to the scene
3.  Explore the scene in the editor, the prefab in the hierarchy, and the associated components in the Inspector
4.  Play the scene, you should see a Plane following a path.
5.  Notice that the engine of the Plane is not running (the propeller is not spinning)
6.  Inspect the Plane Prefab using Hierarchy and Inspector windows. Identify the script that manages the engine and activate it
7.  Add the other Path Plane prefabs to the scene
8.  Activate their engine if it is not done already
9.  You can activate or deactivate prefabs in a scene to explore them one by one (select a gameObject then in the Inspector click on the checkbox next to the name of the gameObject).

## Unit 4: Explore Missile Prefab

1.  Deactivate the three-plane prefabs
2.  Add Missile Prefab to the scene
3.  Explore the scene in the editor, the prefab in the hierarchy, and the associated components in the Inspector
4.  Notice that the missile is not rotating as seen in the demo
5.  Inspect the Missile Prefab using Hierarchy and Inspector windows. Identify the script that manages the Missile
6.  Explore the script. There are four main functions: IdleRotate, FollowTarget, CheckForTarget, and Shoot
7.  Can you make the Missile rotate

## Unit 5: Explore Bullet Prefab

1.  Do the same as Unit 3 to explore Bullet Prefab