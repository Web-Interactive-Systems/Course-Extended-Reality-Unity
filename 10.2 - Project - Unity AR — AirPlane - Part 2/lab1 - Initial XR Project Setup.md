---
type: NoteCard
---

# lab1 - Initial XR Project Setup
## Unit 1: Creating a Unity URP Project: You can call it MyAirPlaneGameStarter

1.  Create a new project using Unity Hub
2.  Select URP Template (Universal Render Pipeline) and click create
3.  Change the build settings  (File | BuildSettings) to Android and click “Switch Platform”

In Unity, it’s possible for developers can customize how the graphics system renders its frames. URP is a pipeline created on the top Scriptable Render Pipelines. The Scriptable Render Pipeline (SRP) system gives developers fine-grained control over what rendering features the engine should and should not enable, which allows them to meet very specific performance and visual quality targets to be met.

## Unit 2: Organizing a Project

1.  Create a folder named URP-examples inside the **Assets** folder
2.  Drag and drop the example folders into the URP-examples (Scenes, TutorialInfo, and the Readme file)
3.  Create an Assets folder named \_App
4.  Inside the folder **\_App/**, create these folders: Materials, Prefabs, Scenes, and Scripts

## Unit 3: Installing XR Plugin

1.  Open the Project Settings window by selecting( Edit | Project Settings)
2.  In the Settings menu on the left, select XR Plugin Management
3.  Click the Install **XR Plugin Management** button 

<!---->

5.  Check the checkbox for the AR plugin you want to use. For example, for Android, select **ARCore** (for iOS, it would be ARKit)
6.  Click “Yes“ if asked “*Do you want to enable the backends? Doing so will RESTART the editor.*”
7.  Select XR Plug-in Manager
8.  Select Project Validation
9.  Potential errors will appear in **red**. If so, click “Fix all” button (on top right of the popup window)

## Unit 4: Installing AR Foundation

1.  Open Package Manager (Window | Package Manager)
2.  Set the package filter in the top left to Unity Registry to see a list of all the official packages
3.  In the search box, type ar. You should now see all the AR-related packages in the list
4.  Select **AR Foundation**, and then press Install (if not installed)

Unit 5: Check (or configure) Input Handler

1.  Open Package Manager
2.  Select Registry 
3.  Find Input System (use the search field and type in input), and click Install (if not installed)
4.  Open the Player Settings window by going to Edit | Project Settings | Player
5.  Find **Other Settings** | **Configuration** | **Active Input Handling** and select Both (if not already in both) 

## Unit 5: Adding AR Camera Support to Universal Render Pipeline (URP)

1.  In the Project window, locate the folder that contains the URP renderer files. This is usually the *Assets/Settings/* folder (let us call it **URP-pipelines**)
2.  In the URP-pipelines **(step 1) folder,** select each file that ends with -Renderer
3.  In the inspector window: “Add Renderer Feature” component and “AR Background Renderer Feature”

## Unit 6: Make sure that you have mobile development (Android/ARCore)

1.  Build support modules: make sure you have installed the Android platform
2.  Target Platform: make sure your build platform is android
3.  XR Plugin: make sure the ARCore plugin is installed, Edit | Project Settings, then select XR Plug-in Management
4.  USB Debugging: make sure you enable debug mode on your mobile device

## Unit 7: Check Android Player settings

1.  Other Settings | Minimum API Level, select Android 7.0 (API Level 24) or higher (PS. this should be handled with “Unit 4 | step 9”)

## Unit 8: Install ARCore Extensions

1.  Download the latest arcore-unity-extensions-*.tgz tarball from the GitHub releases page at *[*https://github.com/google-ar/arcore-unity-extensions/releases/*](https://github.com/google-ar/arcore-unity-extensions/releases/)* (arcore-unity-extensions-*.tgz)
2.  Open the Package Manager using Window | Package Manager
3.  Click the add button and select Add package from a tarball
4.  Locate the file you downloaded from GitHub (arcore-unity-extensions-*.tgz tarball)
5.  Click Open

## Unit 9: Building a test scene

1.  In the Project window, open \_App/Scenes (double click)
2.  Right-click to create a new scene named **BasicTest**
3.  Double-click on **BasicTest** to open it in the Hierarchy window
4.  In the Hierarchy window, delete the default Main Camera
5.  Add an AR Session object by selecting GameObject | XR | AR Session
6.  Add an XR Origin object by selecting GameObject | XR | XR Origin
7.  Add a point cloud manager to the XR Origin object by clicking **Add Component** in the Inspector window. Then, enter “ar point” in the search field and select **AR Point Cloud Manager**
8.  Notice that the Point Cloud Manager has an empty slot for a “Point Cloud Prefab”
9.  Create a Particle System by selecting GameObject | Effects | Particle System
10. In the Inspector window, rename it PointParticle
11. On the Particle System component, uncheck the Looping checkbox
12. Set its “Start Size” to 0.1
13. Uncheck the Play on Awake checkbox
14. Click Add Component, enter “ar point” in the search field, and select **AR Point Cloud**
15. Click Add Component and select AR **Point Cloud Particle Visualizer**
16. Drag and drop the PointParticle object from the Hierarchy window to the Prefabs folder in the Project window (we created \_App/Prefabs before). This makes the GameObject into a prefab
17. Delete the PointParticle object from the **Hierarchy** window
18. In the Hierarchy window, select the AR Session Origin object
19. From the Project window, drag the PointParticle prefab into the AR Point Cloud Manager | Point Cloud Prefab slot
20. Save the scene using File | Save
21. Open the Build Settings window using File | Build Settings
22. Click the Add Open Scenes button to add this scene to the build list
23. In the Scenes in Build list, uncheck all scenes except the BasicTest one
24. Ensure your device is connected to your computer via USB cable
25. Press the Build And Run button to build the project and install it on your device. It will prompt you for a save location