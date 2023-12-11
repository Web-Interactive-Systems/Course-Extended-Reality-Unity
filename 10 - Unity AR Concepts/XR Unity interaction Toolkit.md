---
type: NoteCard
---

# XR Unity interaction Toolkit
A component-based package for creating 3D and UI interactions in Unity. It supports different interactions, such as

*   Cross-platform XR controller input: Meta Quest (Oculus), OpenXR, Windows Mixed Reality, and others
*   Interaction with GameObject: Hover, Select, Focus, and Activate (see below)
*   Haptic feedback through XR controllers
*   Visual feedback (color rendering) to indicate possible and active interactions
*   Audio feedback (sound) to indicate possible and active interactions
*   Interaction with Canvas UI using XR controllers
*   Utility for interacting with XR Origin and camera

These interaction states always involve two aspects:

*   [Interactor](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/architecture.html#interactors)
*   [Interactable](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/architecture.html#interactables)

Both are notified upon entering or exiting an interaction state.

## Interaction States

| State        | Function                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Hover**    | If an Interactable is a valid target for the Interactor its state changes to Hover. Hovering on an object signifies an intention to interact with it, but doesn't typically change the behavior of that object, though it might create a visual indicator for this change of state, like how a hovered button changes tint.                                                                                                                                                                                                                                                    |
| **Select**   | Selection requires an action such as a button or trigger press from the user to enable the Select state. When an Interactable is in the Select state, Unity considers the selecting Interactor to be interacting with it. For example, Selection can simulate picking up a grabbable object, holding a lever, or preparing to push a door that has focus via hovering.                                                                                                                                                                                                         |
| **Focus**    | An Interactable is focused when it is selected. This focus persists until another Interactable is selected or the Interactable explicitly attempts to select nothing. This state is useful for performing actions on an object. For example - gaining focus of an object and then manipulating its color in a menu.                                                                                                                                                                                                                                                            |
| **Activate** | Activation is an extra action, typically mapped to a button or trigger that affects the currently selected object. This lets the user further interact with an object they've selected. The Activate action depends on the Interactable. For example, you can use Activate to toggle a grabbable flashlight on/off or shoot a ball launcher. You can hook the component to process Activate into an action without any additional code by hooking an existing callback using the Inspector window under **Interactable Events** and then add to **Activated** via UnityEvents. |

> — source: <https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/index.html>

## Touchscreen gestures

XR Interaction Toolkit has pre-defined gestures. It is also possible to extend the package by defining your gestures.

| Gesture             | Triggered by input                                                          |
| ------------------- | --------------------------------------------------------------------------- |
| **Tap**             | User touches the screen                                                     |
| **Drag**            | User drags finger across screen                                             |
| **Pinch**           | User moves two fingers toward or away from each other along a straight line |
| **Twist**           | User rotates two fingers around a center point                              |
| **Two Finger Drag** | User drags with two fingers                                                 |

##