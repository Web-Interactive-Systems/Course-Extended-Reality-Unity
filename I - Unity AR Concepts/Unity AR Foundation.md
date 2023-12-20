---
type: NoteCard
---

# Unity AR Foundation

AR Foundation is a developer framework for creating AR/MR applications. It supports different provider plugins:

- ARCore for Android devices
- ARKit for iOS devices
- OpenXR for Hololens 2
- Meta OpenXR for Meta Quest

## AR Features

AR Foundation has built-in scripts and managers for a wide range of features for MR applications.

| Feature                                                                                                                                  | Description                                                                                |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| [Session](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/session.html)                                  | Enable, disable, and configure AR on the target platform.                                  |
| [Device tracking](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/device-tracking.html)                  | Track the device's position and rotation in physical space (such as hand-held, head-worn). |
| [Camera](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/Camera/camera.html)                             | Render images from device cameras and perform light estimation.                            |
| [Plane detection](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/plane-detection.html)                  | Detect and track flat surfaces.                                                            |
| [Image tracking](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/image-tracking.html)                    | Detect and track 2D images.                                                                |
| [Object tracking](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/object-tracking.html)                  | Detect and track 3D objects.                                                               |
| [Face tracking](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/face-tracking.html)                      | Detect and track human faces.                                                              |
| [Body tracking](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/api/UnityEngine.XR.ARFoundation.ARHumanBodyManager.html) | Detect and track a human body.                                                             |
| [Point clouds](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/point-clouds.html)                        | Detect and track feature points.                                                           |
| [Raycasts](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/raycasts.html)                                | Cast rays against tracked items.                                                           |
| [Anchors](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/anchors.html)                                  | Track arbitrary points in space.                                                           |
| [Meshing](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/meshing.html)                                  | Generate meshes of the environment.                                                        |
| [Environment probes](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/environment-probes.html)            | Generate cubemaps of the environment.                                                      |
| [Occlusion](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/occlusion.html)                              | Occlude AR content with physical objects and perform human segmentation.                   |
| [Participants](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/participant-tracking.html)                | Track other devices in a shared AR session.                                                |

## AR Managers

AR Foundation provides different managers that enable different AR features in an application. For example, if your application requires “**plane detection**”, we can use **AR Plane Manager**.

### Adding AR managers to your scene

Most AR managers are added to the GameObject **XR Origin**.

1.  Select XR Origin
2.  Click **Add Component** button
3.  Search by name and select the manager to be added

![{width=281,height=auto}](../attachments/xr-origin-ar-managers.png)

Many AR managers detect and track objects in the real environment. They are called *trackable managers. *A *trackable* is a special component representing anything that can be detected and tracked in the real world. Examples of objects that we can track include planes, point clouds, anchors, environment objects, faces, human bodies, images, and 3D objects.

| Trackable Manager                                                                                                                                                           | Purpose                                     |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [ARPlaneManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/plane-detection.html#ar-plane-manager-component)                           | Detect and track surfaces.                  |
| [ARTrackedImageManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/image-tracking.html#ar-tracked-image-manager-component)             | Detect and track 2D images.                 |
| [ARTrackedObjectManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/object-tracking.html#ar-tracked-object-manager-component)          | Detect and track 3D objects.                |
| [ARFaceManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/face-tracking.html#ar-face-manager-component)                               | Detect and track human faces.               |
| [ARHumanBodyManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/body-tracking.html#ar-human-body-manager-component)                    | Detect and track a human body.              |
| [ARPointCloudManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/point-clouds.html#ar-point-cloud-manager-component)                   | Detect and track feature points.            |
| [ARRaycastManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/raycasts.html#ar-raycast-manager-component)                              | Repeats a raycast every frame.              |
| [ARAnchorManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/anchors.html#ar-anchor-manager-component)                                 | Track an arbitrary point in space.          |
| [AREnvironmentProbeManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/environment-probes.html#ar-environment-probe-manager-component) | Generate cubemaps of the environment.       |
| [ARParticipantManager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/participant-tracking.html#ar-participant-manager-component)          | Track other devices in a shared AR session. |

## Want to learn more

The documentation of AR Foundation is a great place to learn more:

<https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/index.html>
