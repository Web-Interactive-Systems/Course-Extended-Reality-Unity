---
type: NoteCard
---

# Unity XR Trackable Managers
In AR Foundation, a "trackable" is anything that can be detected and tracked in the real world. Planes, point clouds, anchors, environment probes, faces, images, and 3D objects are all examples of trackables.

Each trackable has a trackable manager. All the trackable managers must be on the same `GameObject` as the AR Session Origin. This is because the session origin defines the transform to which all the detected trackables are relative. The trackable managers use the session origin to place the detected trackables in the correct place in the Unity scene graph.