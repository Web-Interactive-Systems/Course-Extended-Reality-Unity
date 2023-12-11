---
type: NoteCard
---

# lab3 - Initial XR Scene
## Unit 1: Importing AR Foundation in a new AR Project

1.  Locate the folder of your project: NameOfYourGameStarter

2.  Create a copy of your project (just to keep your initial project clean, in case you want to start again)

3.  Add and open your your project in Unity Hub

4.  Import the package from the main menu by selecting Assets | Import Package | Custom Package

5.  Locate the arf-samples.unitypackage file on your system and click Open

6.  The Import Unity Package window will open. Click Import

7.  Then, go to Player Settings using Edit | Project Settings | Player, select Configuration | Active Input Handling, and choose Both, … click Apply

8.  Check the console you will see errors. Let’s fix them.

9.  Install com.unity.xr.interaction.toolkit (Window | Package Manager | “+” | … by name)

10. Assets/Scenes/ARKit/ARCollaborationData/AnchorInfoManager.cs(52,23): error CS0227: Unsafe code may only appear if compiling with /unsafe. Enable "Allow 'unsafe' code" in Player Settings to fix this error.

    1.  Open Edit | Project Settings
    2.  Select tab Player
    3.  Find “Script compilation”; then, check “allow unsafe code”

11. Now you should not have any errors in the console

## Unit 2: Running an AR Scene

1.   Open the SimpleAR scene from the Project window by navigating to the ARF-samples/Scenes/SimpleAR/ folder and double-clicking the SimpleAR scene file
2.  Open the Build Settings window by going to File | Build Settings
3.  For the Scenes in Build list, click the Add Open Scenes button and uncheck all the scenes in the list other than the SimpleAR one
4.  Ensure your device is connected via USB
5.  Build And Run

## Unit 3: Create a new sample scene

1.  Create a new scene by going to File | New Scene

2.  If prompted, choose the Basic (Built-in) template. Then, click Create

3.  Delete Main Camera from the Hierarchy

4.  Add an AR Session by selecting GameObject from the main menu, then XR | AR Session

5.  Add an XR Origin by selecting GameObject from the main menu, then XR | XR Origin

6.  Unfold XR Origin and select its child; that is, Main Camera. In the Inspector window, use the Tag selector at the top left to set it as our MainCamera. (This is not required but it is a good practice to have one camera in the scene tagged as MainCamera

7.  Save the scene using File | Save As, navigate to the Assets/Scenes/ folder, name it BasicARScene, and click Save

8.  Explore / Inspect / Check the documentation of the following objects: 

    1.  XR Session
    2.  XR Origin
    3.  Camera

XR Session: Manager of XR session. It enables or disables XR on the target device.

XR Origin: Manager of objects and tracking features in the scene, it processes, computes, and updates objects’ position, orientation, and scale.

Camera: Player’s viewport in a scene.

## Unit 4 Adding a AR Plane detection

1.  Select the XR Origin object from the Hierarchy window
2.  Add a Point Cloud Manager by selecting Add Component, searching for ar in the search input field, then clicking AR Point Cloud Manager
3.  Add a Plane Manager by selecting Add Component, searching for ar in the search input field, and clicking AR Plane Manager
4.  On the AR Plane Manager, change Detection Mode to only horizontal planes by selecting Nothing (to clear the list), then selecting Horizontal
5.  In the Inspector window, go to AR Point Cloud Manager | Point Cloud Prefab and press the doughnut icon on the right-hand side of the field to open the Select GameObject dialog box
6.  Click the Assets tab and double-click the AR Point Cloud Visualizer prefab
7.  Likewise (do the same as for list item 6.), for AR Plane Manager | Plane Prefab, press the doughnut icon on the right-hand side of the field to open the Select GameObject dialog box
8.  Click the Assets tab and double-click AR Feathered Plane
9.  Save the scene by going to File | Save

## Unit 5: Adding AR Raycast Manager

1.  Select the XR Origin object from the Hierarchy window
2.  Select Add Component | search for ar in the search input field, and click AR Raycast Manager

AR Raycast Managers belong to Unity AR Foundation’s Trackable Managers.

In AR Foundation, "trackables" are all features that we can detect and track in the real world.

Trackable features include planes, point clouds, anchors, environment probes, faces, images, and 3D objects.

AR Raycast Managers is a component script, that will process and update a raycast automatically. Raycast will then be used to detect planes.

## Unit 6: Adding Light Estimation

1.  In the Hierarchy window, select the Directional Light object
2.  In the Inspector, click Add Component, search for light estimation, and add the Basic Light Estimation component
3.  In the Hierarchy window, find AR Camera (child of XR Origin), drag it into the Inspector window, and drop it onto the Light Estimation | Camera Manager slot
4.  In the Hierarchy window, select AR Camera, then set AR Camera Manager | Light Estimation to Everything. Note that not all platforms support all light estimation capabilities, but using the Everything flags will have them use all of the ones that are available at runtime
5.  Save your work by going to File | Save

In XR (AR/MR) the user environment has already a real light. Light estimation is a technique for capturing, replicating, and integrating the user environment's light in Unity XR.

As the user moves through their environment, their device will take pictures and build an internal representation of the lighting, which is then injected into Unity's lighting system for use with materials and shaders.

## Unit 7: Building and running the scene

1.  Open the Build Settings window by going to File | Build Settings
2.  For the Scenes in Build list, click the Add Open Scenes button and uncheck all the scenes in the list other than this current scene (mine is named BasicARScene)
3.  Ensure your device is connected to your computer via USB
4.  Press the Build And Run button to build the project and install it on your device. It will prompt you for a location; I like to create a folder in my project root named Builds/. Give it a filename (if required) and press Save. It may take a while to complete this task”