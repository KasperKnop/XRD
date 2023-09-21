## Unity Setup

1. Install Unity 2022.3 LTS with Android Build support enabled (this is currently the only version, that has access to the new 6.0.2 VR template)

## Project Setup

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

###### XR Interaction Toolkit \[RECOMMENDED\]

XR Interaction Toolkit for cross platform VR interaction patterns (grab, teleport, etc) is already enabled in the 6.0.2 VR template. It has the **BasicScene** and **SampleScene** that you can take advantage of, as well as the **DemoScene** in the **Samples** folder. If you want more examples for e.g. hand tracking, you can go to **Window** > **Package Manager** > XR Interaction Toolkit > Samples. This is also where you find the **XR Device Simulator**, that can help you test out your scene without a headset.

> _N.B.: There is a known issue when upgrading from an older version of the Starter Assets to a newer version. Script references in the Demo Scene for scripts included in the Starter Assets become disconnected when upgrading in-place. It is recommended that you delete the **Starter Assets** folder from your **Samples** directory before importing the new Starter Assets sample package._

If you ever get stuck, take a look at the [official documentation](https://docs.unity3d.com/Packages/com.unity.xr.interaction.toolkit@2.5/manual/general-setup.html). For even more elaborate examples, check out [the official XR Interaction Toolkit examples](https://github.com/Unity-Technologies/XR-Interaction-Toolkit-Examples) on Github.

###### Oculus Integration \[OPTIONAL\]

If you want to use specific features from the Oculus platform (avatars, social, etc) you can use the [Oculus Integration](https://assetstore.unity.com/packages/tools/integration/oculus-integration-82022). It comes with prefabs for e.g. native looking controllers, as well as sample scenes for you to explore. You can use the XR Interaction Toolkit and Oculus Integrations in the same project, if you wish.

## Developer Tools \[OPTIONAL\]

These tools are already installed on the lab PCs. If you install them on your own device, you will have to create your own [Meta Account](https://auth.meta.com/).

###### Quest as a PC VR headset (Quest Link)

If your development machine meets the [minimum requirements](https://www.meta.com/en-gb/help/quest/articles/headsets-and-accessories/oculus-link/meta-quest-link-compatibility/) for Quest Link, you can run your VR applications directly from your machine without building for Android:

1. Install the [Oculus Desktop Application](https://www.oculus.com/download_app/?id=1582076955407037).
2. Set Oculus as the active runtime under OpenXR Runtime in the Oculus Desktop application.
3. If you want passthrough, eye tracking, and similar features to work over Oculus Link: **Oculus Desktop App** > **Settings** > **Beta** > **Developer Runtime features**.
4. Make sure your Quest is running the latest software update (settings > about).
5. If Quest Link is not present in the Quick Settings, go to Settings > Quest Link to enable it.
6. Connect your Quest to the PC through USB and accept any prompts.
7. Activate Quest Link in the Quick Settings

###### Additional Wireless PC VR (Quest Air Link)

1. Make sure your Quest and your PC is on the same network (XR-Lab WiFi password: "VIAxrlab2021").
2. Enable Quest Air Link in the Quick Settings of the headset under Quest Link.

###### Additional Tools

1. Install [Oculus Developer Hub](https://developer.oculus.com/documentation/unity/ts-odh/).
2. Connet your Quest to the PC.
3. Open Oculus Developer Hub, click Set Up New Device and follow the instructions.
4. You can have easy access to common development features such as ADB over WiFi to install builds without the Quest physically attached to the PC, casting and recording from the Quest to the PC, diagnostics, disabling proximity sensor, etc.
