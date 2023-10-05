# 03 Exercises: VR Development

## 1. Set Up Your Development Environment

### Unity Setup

Install Unity 2022.3 LTS with Android Build support enabled (this is currently the only version, that has access to the new 6.0.2 VR template)

### Project Setup

1. Start a new Unity Project using the **VR** core template.
2. In the menu, go to **File** > **Build Settings**.
3. Under **Platform**, select **Android**.
4. Set Texture Compression to ASTC.
5. Click **Switch Platform**.
6. If you are using the older 3.1 VR template: Go to **Edit** > **Project Settings** > **XR Plugin Management**.
    1. Make sure that **OpenXR** is enabled in both the desktop and Android tab. (desktop is required if you want to use Quest Link for faster development)
    2. **OpenXR** > Add Meta Quest Touch Pro as an Interaction Profile & Enable Meta Quest Support
7. Run the project in the editor with a Quest connected using either Oculus Link or Oculus Air Link, or build directly to the Quest to to verify that everything is set up correctly.

For more information on the VR template, check out the [quick start guide](https://docs.unity3d.com/Packages/com.unity.template.vr@6.0/manual/index.html). It is worth mentioning, that the new 6.0.2 template takes advantage of the Universal Render Pipeline.

### XR Interaction Toolkit

XR Interaction Toolkit for cross platform VR interaction patterns (grab, teleport, etc) is already enabled in the 6.0.2 VR template. It has the **BasicScene** and **SampleScene** that you can take advantage of, as well as the **DemoScene** in the **Samples** folder. If you want more examples for e.g. hand tracking, you can go to **Window** > **Package Manager** > XR Interaction Toolkit > Samples. This is also where you can update to the latest version of the XR Interaction Toolkit and find the **XR Device Simulator**, that can help you test out your scene without a headset.

> _N.B.: There is a known issue when upgrading from an older version of the Starter Assets to a newer version. Script references in the Demo Scene for scripts included in the Starter Assets become disconnected when upgrading in-place. It is recommended that you delete the **Starter Assets** folder from your **Samples** directory before importing the new Starter Assets sample package. If you find yourself with **disconnected script references** (which for the template scenes often results in both controllers showing permanent teleportation indicators and two raycasts), **try "Assets > Reimport all**"._

If you ever get stuck, take a look at the [official documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/general-setup.html).

### Developer Tools

These tools are already installed on the lab PCs. If you install them on your own device, you will have to create your own [Meta Account](https://auth.meta.com/).

#### Quest as a PC VR headset (Quest Link)

If your development machine meets the [minimum requirements](https://www.meta.com/en-gb/help/quest/articles/headsets-and-accessories/oculus-link/meta-quest-link-compatibility/) for Quest Link, you can run your VR applications directly from your machine without building for Android:

1. Install the [Oculus Desktop Application](https://www.oculus.com/download_app/?id=1582076955407037).
2. Set Oculus as the active runtime under OpenXR Runtime in the Oculus Desktop application.
3. If you want passthrough, eye tracking, and similar features to work over Oculus Link: **Oculus Desktop App** > **Settings** > **Beta** > **Developer Runtime features**.
4. Make sure your Quest is running the latest software update (settings > about).
5. If Quest Link is not present in the Quick Settings, go to Settings > Quest Link to enable it.
6. Connect your Quest to the PC through USB and accept any prompts.
7. Activate Quest Link in the Quick Settings

##### Additional Wireless PC VR (Quest Air Link)

1. Make sure your Quest and your PC are on the same network (XR-Lab WiFi password: "VIAxrlab2021").
2. Enable Quest Air Link in the Quick Settings of the headset under Quest Link.

#### Additional Tools

1. Install [Meta Quest Developer Hub](https://developer.oculus.com/documentation/unity/ts-odh/).
2. Connet your Quest to the PC.
3. Open Meta Quest Developer Hub, click Set Up New Device and follow the instructions.
4. You can have easy access to common development features such as ADB over WiFi to install builds without the Quest physically attached to the PC, casting and recording from the Quest to the PC, diagnostics, disabling proximity sensor, etc.

![Oculus Developer Hub](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/1.png)

## 2. The XR Origin

Use the BasicScene from the VR template to familiarize yourself with the "Complete XR Origin Set Up" - specifically the XR Origin. What GameObjects and components does it consist of, and what is their purpose? How do you change the controls of the XR Rig? (move speed, turn/smooth rotation, etc?)

![BasicScene](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/2.png)

## 3. Interactables

Using the BasicScene as a starting point, create two cubes - one as a table and one as an object resting on the table that you can grab and interact with. Change the movement type of the interactable. What is the difference between instantaneous, velocity tracked and kinematic?

![interactables](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/3.png)

## 4. Handling Input

Familiarize yourself with the touch controllers. Make a script that registers whenever a specific button is pressed on the controller. Can you get access to a, b, triggers, thumb detection, etc?

![input system](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/4.png)

## 5. Interactable Events

Create a gun that can shoot balls! The gun should have an XR Grab Interactable component, so that you can grab it and use the “Activated” interactable events to shoot the balls.

![launcher](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/5.png)

## 6. Further Exploration

To get a deeper understanding of the various features included the XR Interaction Toolkit, explore the official [XR Interaction Toolkit examples](https://github.com/Unity-Technologies/XR-Interaction-Toolkit-Examples) repository. You could look into feature such as:

-   Hand tracking
-   Eye tracking (requires Quest Pro)
-   Gaze Interactors
-   Socket Interactors
-   2D or 3D UI
-   Physics Interactables
-   Various types of locomotion - e.g. climbing and using teleportation anchors

If you want to use specific features from the Oculus platform (avatars, social, etc) you can use the [Oculus Integration](https://assetstore.unity.com/packages/tools/integration/oculus-integration-82022). It comes with prefabs for e.g. native looking controllers, as well as sample scenes for you to explore. You can use the XR Interaction Toolkit and Oculus Integrations in the same project, if you wish.

![Further Exploration](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/6.png)
