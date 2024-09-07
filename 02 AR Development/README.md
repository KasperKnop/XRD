# 02 Exercises: AR Development

## 1. Set Up Your Development Environment

To get started on the exercises, you will need to have a few things set up and ready:

-   Install Unity 6 (Make sure you install the same version as your team for future collaboration)
-   Add the Android/iOS build support module depending on what device you have access to (building for iOS generally requires a Mac).
-   Set up Rider, Visual Studio Code or any other C# IDE of your choice.

## 2. Create A New AR Project

Use the AR template in Unity Hub to get started.

> You can also enable AR Foundation in an existing project:  
> Project settings > XR Plugin Management > "Install XR Plugin Management"  
> Toogle Google ARCore (installs AR Foundation and ARCore provider plugin)  
> Accept the restart to enable the new input system

For more information about the AR template, you can refer to [the documentation]([https://docs.unity3d.com/Packages/com.unity.template.ar@4.0/manual/index.html]).

What is the purpose of the GameObjects and components already in the scene? What is the difference between session space and world space?

![New AR Project](https://github.com/KasperKnop/XRD/blob/main/02%20AR%20Development/img/2.png)

## 3. Using The Simulator

Unity has an XR Simulation plugin that lets you quickly test your AR app in the Editor, simulating the behavior of device and environment.

To enable it, toggle XR Simulation in the XR Plugin Manager.

When you enter Play Mode with XR Simulation enabled, AR Foundation loads your XR Simulation environment into the scene with keyboard and mouse navigation controls (hold down the right mouse button and use WASD to fly around).

You can configure this environment by going to Window > XR > AR Foundation > XR Environment. Click on the drop down to install the sample environments and select one of your choosing.

Not all AR Foundation features can be tested in the simulator. Refer to [the documentation](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/xr-simulation/simulation-overview.html) for details.

Test out the AR templates “SampleScene” using various simulated environments.

<blockquote>
It is worth noting that touch input is not currently supported by the simulator.
The SampleScene uses <a href="https://docs.unity3d.com/ScriptReference/Touch.html">Touch</a> for placing objects, which means that you will be able to detect planes in the simulation, but not place down objects. When writing your own applications, you can get around this by using <a href="https://github.com/Unity-Technologies/arfoundation-samples/blob/main/Assets/Scripts/Runtime/PressInputBase.cs">InputActions</a> instead, which works for both touch and pointer input, or you can use <a href=”https://docs.unity3d.com/Packages/com.unity.inputsystem@1.0/api/UnityEngine.InputSystem.EnhancedTouch.EnhancedTouchSupport.html”>EnhancedTouchSupport</a>, which can simulate other types of Pointer devices (e.g. Mouse or Pen).
</blockquote>

![AR Simulator](https://github.com/KasperKnop/XRD/blob/main/02%20AR%20Development/img/3.png)

## 4. Building To Device

Test out the SampleScene by building it to an Android or iOS device.

> Building to iOS is a more elaborate process. Refer to [the documentation](https://docs.unity3d.com/Manual/iphone-BuildProcess.html) for more info on that setup.

Go to Project Settings and enable ARCore for Android (or ARKit for iOS). Then switch your build target under build settings and click “Build and Run”.

When running the application, you should be able to detect planes and place cubes.

## 5. Detecting Planes

It’s time to implement an AR scene from scratch. Create a new scene, delete or convert the camera to an [XR Origin](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/device-tracking.html) and add an [AR Session](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/session.html) GameObject. Take some time to familiarize yourself with the two GameObjects and their purpose.

Add [plane tracking](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/plane-detection.html) to the experience. The plane visualization should look different from the SampleScene. How come? Can you change the visualization so that it matches that of the SampleScene?

![Plane Detection](https://github.com/KasperKnop/XRD/blob/main/02%20AR%20Development/img/5.png)

## 6. Raycasting

You can [cast rays](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/raycasts.html) to perform hit detections against trackables such as planes. The API is similar to Unity's physics module. Use this to spawn a cube at the position on a plane where the user is touching. If you want to test using the simulator, make sure that you are using an API that registers mouse input as well as touch input.

![Raycasting](https://github.com/KasperKnop/XRD/blob/main/02%20AR%20Development/img/6.png)

## 7. Augmented Images

Image targets can be a good way to anchor virtual experiences and are useful for calibrating with real world locations.

Use the [AR Tracked Image Manager](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@6.0/manual/features/image-tracking.html) to spawn a cube on top of a tracked image.

![Augmented Images](https://github.com/KasperKnop/XRD/blob/main/02%20AR%20Development/img/7.png)

## 8. Further Exploration

To get a deeper understanding of the various features included in AR Foundation, explore the [AR Foundation Samples](https://github.com/Unity-Technologies/arfoundation-samples) repository. Depending on your interests - and maybe a vague idea about what features you will need for your AR project - you should try to create a scene utilizing the following:

-   Light estimation
-   Occlusion
-   XR Interaction Toolkit
-   Onboarding UX
-   Environment Propes
-   Anchors
-   Session recording
-   Face tracking

There are also features outside of AR Foundation, which might be worth looking into. E.g. [Cloud Anchors](https://developers.google.com/ar/develop/cloud-anchors), which is part of the [AR Core Extensions](https://developers.google.com/ar/develop/unity-arf/getting-started-extensions).

You can also familiarize yourself with a 3D modeling tool like [Blender](https://www.blender.org/download/) for creating or modifying models for your experiences.

![Further Exploration](https://github.com/KasperKnop/XRD/blob/main/02%20AR%20Development/img/8.png)
