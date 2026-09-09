# CS 417 MP1a: The Room

A Unity VR room created for **CS 417: Introduction to Extended Reality**. The project targets Meta Quest through OpenXR and demonstrates the scene-building, materials, tracking, controller-input, and scripting requirements for MP1a.

## Contributor

- Daryl Okeke

## Project Setup

- Unity Editor: `6000.5.6f1`
- Render pipeline: Universal Render Pipeline (URP)
- Build target: Android (`arm64-v8a`)
- XR runtime: OpenXR with Meta Quest Support
- Controller profile: Oculus Touch Controller Profile
- Main scene: `Assets/Scenes/MP1a_DecontaminationRoom.unity`

This repository uses Git LFS for binary assets. After cloning, make sure Git LFS is installed and retrieve the LFS files before opening the project:

```bash
git lfs install
git lfs pull
```

Open the repository folder through Unity Hub using Unity `6000.5.6f1`. Allow Unity to restore packages and finish importing assets before entering Play Mode or building.

## Controls

| Action | Meta Quest controller | Editor fallback |
|---|---|---|
| External view / return | Right controller A button | `T` |
| Exit application | Right controller B button | `Escape` |
| Change room-light color | Left controller X button | `L` |

`Application.Quit()` exits the built application. In the Unity Editor, the quit action stops Play Mode instead.

## Rubric Features

- **The Room:** A complete enclosed 15-by-15-by-15-unit room made from four inward-facing walls, a floor, and a ceiling with collision.
- **Lighting:** A bright realtime point light with soft shadows is positioned at the center of the ceiling.
- **Planet and Moon:** A moon is parented to a planet positioned at the center of the room.
- **Text:** A high-resolution world-space TextMeshPro canvas displays the controls inside the room.
- **Skybox:** A six-sided skybox is visible from the external vantage point.
- **Material Maps:** Two walls use the provided tile base map and normal map.
- **Material Tiling:** The two textured walls use visibly different `1x1` and `4x4` tiling settings.
- **Material Properties:** The textured wall materials use different metallic and smoothness settings.
- **Flat Color Material:** Another wall uses a material with a flat color and no texture maps.
- **VR Tracking:** The scene uses an XR Origin containing a tracked camera and tracked controllers.
- **Controller Inputs:** OpenXR controller buttons are mapped through a Unity Input Actions asset and trigger C# scripts.
- **Quit Key:** The right controller B button exits the built application.
- **Light Switch:** The left controller X button switches the ceiling light between white and red.
- **Orbiting Moon:** The planet rotates continuously using `Time.deltaTime`, causing its child moon to orbit at a frame-rate-independent rate.
- **Break Out:** The right controller A button alternates the XR Origin between the room and an external viewpoint.

The optional headset-hardware point requires a demonstration video recorded from a user in the headset and is therefore documented in the submission evidence rather than claimed by the repository alone.

## Building for Meta Quest

1. Open `MP1a_DecontaminationRoom`.
2. Open **File > Build Profiles** and select Android.
3. Confirm that `MP1a_DecontaminationRoom` is enabled in the scene list.
4. Confirm **OpenXR**, **Meta Quest Support**, and the **Oculus Touch Controller Profile** are enabled for Android.
5. Build the APK and install it on the headset for final testing.

Generated builds are intentionally excluded from Git. The validated local build is named `TheRoom_MVP1_Quest.apk`.

## Course Assets

The tile base map, tile normal map, and six skybox images were supplied through the CS 417 MP1a assignment materials.
