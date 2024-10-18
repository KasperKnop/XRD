# 03 Exercises: VR Development

## 1. Set Up Your Development Environment

### Project Setup

1. Start a new Unity Project using the **VR** core template (Unity 6 is recommended for the newest template).
2. In the menu, go to **File** > **Build Settings**.
3. Under **Platform**, select **Android**.
4. Set Texture Compression to ASTC.
5. Click **Switch Platform**.
6. Run the project in the editor with a Quest connected using either Oculus Link or Oculus Air Link, or build directly to the Quest to to verify that everything is set up correctly.

N.B.: If you cannot enable USB debugging for pushing the apk to the Quest, make sure that the headset have developer mode enabled. You can check this on the lab phone that controls the light. Open Meta Horizon, find the device, go to headset settings and check that the developer options are enabled. Retoggling the option and restarting the headset to make sure that it is registered.

For more information on the VR template, check out the [quick start guide](https://docs.unity3d.com/Packages/com.unity.template.vr@9.0/manual/index.html).  It is worth mentioning, that the template takes advantage of the Universal Render Pipeline.

### XR Interaction Toolkit

XR Interaction Toolkit for cross platform VR interaction patterns (grab, teleport, etc) is already enabled in the 6.0.2 VR template. It has the **BasicScene** and **SampleScene** that you can take advantage of, as well as the **DemoScene** in the **Samples** folder. If you want more examples for e.g. hand tracking, you can go to **Window** > **Package Manager** > XR Interaction Toolkit > Samples. This is also where you can update to the latest version of the XR Interaction Toolkit and find the **XR Device Simulator**, that can help you test out your scene without a headset.

> _N.B.: There is a known issue when upgrading from an older version of the Starter Assets to a newer version. Script references in the Demo Scene for scripts included in the Starter Assets become disconnected when upgrading in-place. It is recommended that you delete the **Starter Assets** folder from your **Samples** directory before importing the new Starter Assets sample package. If you find yourself with **disconnected script references** (which for the template scenes often results in both controllers showing permanent teleportation indicators and two raycasts), **try "Assets > Reimport all**"._

If you ever get stuck, take a look at the [official documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@3.0/manual/general-setup.html).

### Developer Tools

These tools are already installed on the lab PCs. If you install them on your own device, you will have to create your own [Meta Account](https://auth.meta.com/).

#### Quest as a PC VR headset (Quest Link)

If your development machine meets the [requirements](https://www.meta.com/en-gb/help/quest/articles/headsets-and-accessories/oculus-link/requirements-quest-link/) for Quest Link, you can run your VR applications directly from your machine without building for Android:

1. Install the [Meta Quest Link app](https://www.meta.com/en-gb/help/quest/articles/headsets-and-accessories/oculus-rift-s/install-app-for-link/).
2. Set Oculus as the active runtime under OpenXR Runtime in the Meta Quest Link app.
3. If you want passthrough, eye tracking, and similar features to work over Oculus Link: **Oculus Desktop App** > **Settings** > **Beta** > **Developer Runtime features**.
4. Make sure your Quest is running the latest software update (put on headset > Quick Settings > Settings > System > Sofware Update).
5. If Quest Link is not present in the Quick Settings, go to Settings > System > Quest Link to enable it.
6. Connect your Quest to the PC through USB and accept any prompts.
7. Activate Quest Link in the Quick Settings

##### Additional Wireless PC VR (Quest Air Link)

1. Make sure your Quest and your PC are on the same network (XR-Lab WiFi password: "VIAxrlab2021").
2. Enable Quest Air Link in the Quick Settings of the headset under Quest Link.

#### Additional Tools

1. Install [Meta Quest Developer Hub](https://developers.meta.com/horizon/documentation/unity/ts-odh/).
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

If you want to use specific features from the Oculus platform (avatars, social, etc) you can use the [Meta XR All-in-One SDK](https://assetstore.unity.com/packages/tools/integration/meta-xr-all-in-one-sdk-269657?srsltid=AfmBOoqhDrz1KhtGerb7Y2GkSjRGIo_U06XQP1Cmo8uMmrZbTT7zQEyf). It comes with prefabs for e.g. native looking controllers, as well as sample scenes for you to explore.

![Further Exploration](https://github.com/KasperKnop/XRD/blob/main/03%20VR%20Development/img/6.png)
