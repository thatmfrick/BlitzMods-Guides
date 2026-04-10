## Content in this guide 📜

> [!NOTE]
> **Quick Links**
> - [Info](#before-modding)
> - [Tools](#tools-and-apps-we-need)
> - [Shizuku](#shizuku-setup)
> - [File system](#file-system-info)
> - [Plug&Play](#install-plugplay-modifications)
> - [non-Plug&Play](#install-non-plugplay-modifications)
> - [Updates](#what-happens-if-an-update-gets-released)

## Before Modding ℹ️ <a id="before-modding"></a>

> [!NOTE]
> **Android versions <= 10?**
> Well things are easier, you have direct access to the game files in `Android/data`, allowing you to skip the Shizuku setup.

> [!NOTE]
> **Android versions > 10?**
>
> Access to `/Android/data` has been limited for security reasons; only the applications can directly access to this path to use their files.
> - There are several ways to gain access to this path:
>
>  1. **~~adb debugging~~** ❌ Requires a PC
>  2. **~~Rooted device~~** ❌ too risky/and unnecessary for our purposes
>  3. **A tool like Shizuku** ✅ No PC required and easy setup

## Tools and Apps We Need 🧰 <a id="tools-and-apps-we-need"></a>

> [!IMPORTANT]
> **Advanced File System** 🗂️
>
> - [*MT manager*](https://pan.mt2.cn/mt/MT2.26.1.apk) ✅ A two-sided file manager with numerous useful options and integrated file editors.
> - Other similar tools at your choice 🤷‍♂️

> [!IMPORTANT]
> **Tool for accessing `Android/data`** 🗝️
>
> - [*Shizuku*](https://github.com/RikkaApps/Shizuku/releases/download/v13.6.0/shizuku-v13.6.0.r1086.2650830c-release.apk) ✅

> [!IMPORTANT]
> **WoTB `.apk` archive 🎮 (*for non-Plug&Play mods*)**
>
> - [*Wargaming version*](https://wotblitz-gc.gcdn.co/wotbp/wotblitz_11.16.1.314_1fd5db155ca2582b4210141fc90357b316fccd83.apk) ✅
> - Play/Galaxy Store version ❌ More complex compared to the Wargaming version; it may be covered in the future 👀

> [!IMPORTANT]
> **`.dvpl` Converter 📂 (*for non-Plug&Play mods*)**
>
> - [*BINT*](https://github.com/thatmfrick/BlitzMods-Guides/releases/tag/dvpl_converter) ✅ Decompresses modded files to pack in the `.apk`.
> - Better tools will be available soon 👀

## Shizuku Setup 📋 <a id="shizuku-setup"></a>

- Once **Shizuku** is installed, we need to choose a method to enable and start it.
- We will use the `Wireless Debugging method`

<img width="597" height="976" alt="main" src="https://github.com/user-attachments/assets/ec7461ac-6978-4353-87b8-b8d7facd41bc" />

### Step 1 - Pairing 🔗

1. Press the ***`Pairing button`***
2. You need to enable Shizuku to post notifications

   ![notify](https://github.com/user-attachments/assets/05c57166-c281-4199-9209-d3caf7bf111f)
   - Tap on ***`Notification options`*** and enable it.
   - Go back to the `Pairing` page.
3. You should now see this screen:

   ![pair](https://github.com/user-attachments/assets/9e657113-286d-454d-b813-972dd45eaab7)


> [!WARNING]
> **If you encounter any issues regarding network permissions, refer to the section with the ⚠️ symbol.**

4. Press on **`Developer options`**

> [!CAUTION]
> **If you don't have Developer options enabled; you cannot continue.**
> - To Enable them:
>   - Go to System settings -> About phone/tablet -> scroll to build number -> tap 7 times on it -> enter PIN/password to unlock -> done
> - In settings, search for Developer options and ensure they are enabled.

5. In the Developer options, find the **Wireless debugging** option:
   1. Turn it on.
   2. Tap on it.
6. You should see the option ***`Pair device with pairing code`***.

   ![code](https://github.com/user-attachments/assets/8805a5e3-8743-468f-862b-d0b0d2f5e0ff)
   1. Tap on the option, and a six digit code will appear along with a notification from Shizuku prompting you to enter the code.
   2. Type the code and Send.
   3. Below the **`Pair device with pairing code`** you should see Shizuku listed in the paired devices section.

   ![paired](https://github.com/user-attachments/assets/4307f4e2-8943-404d-b5ec-fb7917d23252)
7. Go back to Shizuku.

> [!NOTE]
> **Pairing done** ✅

### Step 2 - Start ▶️

1. Press on **`Start`**.
2. You will see this window:

   ![start](https://github.com/user-attachments/assets/5e746a88-7857-469f-b2d5-6bf3cb266d98)

> [!NOTE]
> **Shizuku is fully working** ✅

## Install Plug&Play Modifications

> [!NOTE]
> **Plug&Play is a [Blitz-Mods](https://blitz-mods.com/mod/new) tag used to identify modifications that do not need to be packed in the `.apk` archive of the game.**
> - These modifications can be placed directly in the `Android/data` folder and will work seamlessly, similar to the Drag&Drop action we perform on a PC.

### Quick File System Info ℹ️ <a id="file-system-info"></a>

> [!NOTE]
> **Useful Information Before Modding**
> - `/` is the root directory (parent of every other directory and sub-directory in the file system).
> - `..` represents the parent directory. Tapping on it in **MT manager** will take you one directory back; continuing to tap will eventually lead you to the root.
> - There are two main paths to access the `HOME` directory on your device:
>   1. `/sdcard/` -> Shortest path
>   2. `/storage/emulated/0/` -> Default path when you open MT manager
> - Depending on the version of the game you have installed, you can find the game files in:
>   1. `/storage/emulated/0/Android/data/app.wotblitz.com` -> **Wargaming version**
>   2. `/storage/emulated/0/Android/data/com.wargaming.wot.blitz` -> **Play Store version**
>   3. `/storage/emulated/0/Android/data/com.wargaming.wot.blitz.flexion` -> **Galaxy Store version**
>   4. Alternatively, you can access these paths via `/sdcard/Android/data/...`

### Step 1 - MT Manager Setup

> [!CAUTION]
> In order to simplify the installation, for the different store versions, most of the new android mods once extracted will start from the `packs` folder.
> - So when installing the Plug&Play mod just navigate inside the `files` folder in `/storage/emulated/0/Android/data/<your game version>/files` and you will see the `packs` folder.
> - Now just follow the [extraction step](#step-2---extraction) where you just hold the mod's `packs` folder and press on extract in `/storage/emulated/0/Android/data/<your game version>/files`

1. We will download this [*Leopard 1*](https://blitz-mods.com/mod/remodelings/remodeling-leopard-1-c2-mexas-209) remodel.
2. Open MT Manager and navigate in the `Download` folder on one side.
3. On the other side go to `Android/data`.
4. Tap on the downloaded modification `.zip` file; you should see the `net.wargaming.wot.blitz` folder.
   1. If you see the `net.wargaming.wot.blitz` folder on both sides, you can proceed to the [extraction step](#step-2---extraction) (you are using the Play Store version).
   2. If you have the Wargaming/Galaxy Store version, you will notice a name mismatch.

   ![paths-diff](https://github.com/user-attachments/assets/e9ec91cc-0052-4b9f-8721-503f29a9a32e)

> [!TIP]
> **Fix Folder Name Mismatch**
> - ***Solution 1***
>   - One tap on both folders, and you will have the matching `files` folder. ![match](https://github.com/user-attachments/assets/b6b1de46-b98e-46e3-9a0f-8b57f062451c)

> - ***Solution 2***
>   - Hold the `net.wargaming.wot.blitz` and select rename to change it to `app.wotblitz.com` (or the Galaxy store equivalent). ![rename-export](https://github.com/user-attachments/assets/bc0b3ff7-0823-4045-a88c-2185ec063cab)

### Step 2 - Extraction

- As you can see in the image above, by holding the `files`, `app.wotblitz.com`, `net.wargaming.wot.blitz.flexion`, `net.wargaming.wot.blitz` or `packs` folder, a window with the `<- Extract ->` option will appear.
1. Tap on ***`Extract`***.
2. Confirm that you want to extract files into `/storage/emulated/0/Android/data/<your game version>/` or `/storage/emulated/0/Android/data/<your game version>/files/` if you want to extract the **files** folder.
3. Make sure to select **`Copy and replace`** and **`Apply to subsequent conflicts`**, then press OK.

   ![merge](https://github.com/user-attachments/assets/3b14b1d9-f1f8-4097-bfd4-32f5aa3e8cb4)

> [!NOTE]
> Congrats, your mod is installed ✅
>
> ![leo](https://github.com/user-attachments/assets/d2f3c8fa-79c2-43ac-a2b4-eff2292c1d1f)


## Install non-Plug&Play Modifications

### Before Proceeding ℹ️

> [!NOTE]
> **What's the difference between Plug&Play and non-Plug&Play mods?**
> - A modification that is not marked as Plug&Play on [Blitz-Mods](https://blitz-mods.com/mod/new) (and is available on Android) also needs to be packed into the game's `.apk` file.

> [!NOTE]
> **Only for Wargaming Version?**
> - Even if it's possible to install modifications that require packing into the `.apk` archive of the Play/Galaxy Store version, I won't explain how to do that at the moment due to:
>   1. **Complexity:** Compared to the **Wargaming** version, there are extra steps involved (many of you may get lost).
>   2. **Possible Compatibility Issues:** Different versions of Android may lead to compatibility problems.

> [!NOTE]
> **What happens if I don't pack the modification that requires packing into the `.apk`?**
> - Common issues:
>   1. The modification does not appear in the game, such as UI/GFX modifications (but also others).
>   2. The modification appears (if installed as [Plug&Play](#install-plugplay-modifications)) but all the textures are missing; this is typical for tanks and hangar modifications.
>
>   ![error](https://github.com/user-attachments/assets/6c5bf23e-fde4-4c7b-8eb9-7c7c0ac32532)


### Step 1 - Download and Sign the `.apk`

1. Uninstall the current game, regardless of the version.
2. Download (**DO NOT INSTALL!**) the [*Wargaming .apk*](https://wotblitz-gc.gcdn.co/wotbp/wotblitz_11.16.1.314_1fd5db155ca2582b4210141fc90357b316fccd83.apk)
3. Download and install the `.dvpl` converter, [*BINT*](https://drive.usercontent.google.com/download?id=1k1Js2UHQbFMUWoGPxH_Yh8FPdih7nD6X&export=download&authuser=0&confirm=t&uuid=2be0288c-ab35-47cd-a0b2-867956c13c28&at=ANTm3cye_-OhWNtfcXNR8REt4gTf:1768901119905)
4. It's optional but recommended to rename the downloaded `.apk`.

   ![rename](https://github.com/user-attachments/assets/aa5706f8-1bda-4979-a7ef-d1eeeb7f99fc)

5. Hold the `.apk` and tap on ***Sign***

   ![sign-opt](https://github.com/user-attachments/assets/e92c7ff1-1be0-40b8-8cb4-34608ae32c99)

> [!CAUTION]
> **Careful, this is the most important step**
> - Scheme:
>   - Leave the `Scheme V1+V2` if you are on Android < 9.
>   - From Android 9 and above you can select `Scheme V1+V2+V3` (supports key rotation), **but** `V1+V2` will work as well.
> - Omit the `Custom V1 signature data filename`
> - Enable `Remember signing options for this package name ...`
> - Press OK
>
> ![final-sign](https://github.com/user-attachments/assets/1e8879ab-c3d6-479e-af17-4338623c955a)

6. In the `Download` folder, you will now find the "old" non-signed `.apk` and the newly signed one `_sign.apk`.
   - To avoid mistakes, you may remove the non-`_signed` `.apk`.
7. Tap on the `wotblitz_<version xyz>_sign.apk` and press install.

> [!NOTE]
> **Our signed version is installed** ✅

### Step 2 - Download, Extract and Decompress the Modification

- We will download this [*WZ 113-G FT*](https://blitz-mods.com/mod/remodelings/remodeling-wz-113g-ft-mwt-p9-366) remodel.
1. Press on the `.zip` of the mod and select `Extract to...`.
2. In the `Extract` window, choose `Extract to current directory` and press OK.

   ![extract-to](https://github.com/user-attachments/assets/27cd253a-9b60-490f-8e1e-9e299b66a8d5)

3. Open the `.dvpl` converter and select `EXTRACT FROM DVPL`.
4. Navigate in the Download folder; you should see the previously extracted modification in the `net.wargaming.wot.blitz` folder.
   - Tap on it

   ![selectfolder](https://github.com/user-attachments/assets/3f4214bf-4925-485a-bdde-0c95901dbd6f)

   - When you see this press `CONFIRM`
   - The program will decompress the files, creating a copy of the `net.wargaming.wot.blitz` folder (containing decompressed files) named `net.wargaming.wot.blitz_NORMAL`
5. If everything was done correctly, you should see the following in the Download folder:

   ![converted](https://github.com/user-attachments/assets/aaebda85-5cc5-401d-9d63-d3e63739fb5f)

### Step 3 - Install the Modification

> [!IMPORTANT]
> **What to do with those folders?**
> - 🟢 Decompressed files to install in the `.apk`
> - 🔴 `.dvpl` files to install as a [Plug&Play mod](#install-plugplay-modifications)

- To install the **modification** in the `.apk` follow these steps:
  1. Open the **Download** folder on both sides of MT Manager.
  2. On one side, tap on the `net.wargaming.wot.blitz_NORMAL` 🟢 folder and navigate to the `packs` folder:

     ![packs](https://github.com/user-attachments/assets/ca624958-2de0-47fd-8da4-e1bff13704c5)

     - In this folder, you will see the `3d` folder (or more if the mod requires other files/folders).
  3. On the other side tap on the signed `.apk`, press `view`, and navigate to the `Data` folder:

     ![Data](https://github.com/user-attachments/assets/75b9dd75-0ac9-47af-bad3-7ebd4fd83745)

  4. At this point you should see a match of folders on both sides (`3d | 3d`).

     ![Data-match](https://github.com/user-attachments/assets/c27165ef-8704-4333-9acf-5c702001eb7c)

  5. Hold the mod's `3d` folder and press on **`Add`**.

> [!CAUTION]
> **Make sure to enable `AUTO SIGN`; it's very important!**
> - This will apply the signing options used for installing the `.apk`, allowing the system to update the current game without any conflicts when we install the `.apk` with the mod.
>
> <img width="1120" height="690" alt="Add-Sign" src="https://github.com/user-attachments/assets/e02081d4-1bc1-44b4-9bf3-aacbe20afcbd" />

> [!TIP]
> **What if we have more files/folders than just the single `3d` folder?**
> - Tap on the three dots in the top right corner, select `Select All`, then hold one of the files from the **mod** and perform the same operation explained above.

6. Once we have added and auto-signed the `.apk`, we need to install the `_sign.apk` again, as if we are "actually" updating the game to a newer version.

> [!NOTE]
> **The mod has been successfully packed into the `.apk`** ✅

> [!WARNING]
> **Do not expect the modification to appear in the game if you haven't installed it as a Plug&Play modification.**
> - If you haven't installed it yet as a Plug&Play mod, jump to the steps [here](#install-plugplay-modifications) for guidance.

> [!WARNING]
> **If, after installing the modification in the `.apk` and in `Android/data`, we don't see it in the game, it means:**
> 1. The HD resources have not been downloaded (especially for 3d remodels). Try enabling HD textures in the settings to download them.
>    - You will need to reinstall the mod as Plug&Play because the `HD` resources will overwrite the modded files previously installed.
> 2. We may have missed some steps, so ensure that all steps were completed correctly.
>    - Ensure that you **do not** have the decompressed 🟢 files installed in `Android/data`.

> [!NOTE]
> **If everything was done correctly (and any issues have been fixed), you should see the modifications in the game.**
>
> <img width="834" height="403" alt="mod-success" src="https://github.com/user-attachments/assets/2fbefe9e-0120-4b92-8878-0658cbf9a29f" />


## What happens if an update gets released?

> [!NOTE]
> **What happens to the modifications?**
> - ***Play/Galaxy Store (Plug&Play):***
>   - Modifications will most likely remain in place; however, if a specific component receives an update (such as tanks getting PBR, icons, etc.), the mod will be replaced, and you'll need to reinstall it only if the creator updates the modification.
> - ***Wargaming (Plug&Play):***
>   - The same situation will apply as with the Play Store version.
> - ***Wargaming (.apk)***
>   1. When an update is released, you will have to download the [latest version](https://wotblitz-gc.gcdn.co/wotbp/wotblitz_11.16.1.314_1fd5db155ca2582b4210141fc90357b316fccd83.apk) of the game.
>
>      <img width="1600" height="862" alt="update" src="https://github.com/user-attachments/assets/18e95255-eb27-412b-9c01-ecd1a6610edf" />

>   2. After that, you need to sign the new version by repeating [Step 1](#step-1---download-and-sign-the-apk).
>   3. Then, you can remove any unnecessary `.apk(s)`.
>
>      ![ok-version](https://github.com/user-attachments/assets/9105b657-d20b-423d-8979-24c0b98c2990)

>   4. Finally, you will need to repeat [Step 2](#step-2---download-extract-and-decompress-the-modification) and [Step 3](#step-3---install-the-modification) to reinstall the modification(s) you had before -> New version = all mods installed in the old `.apk` are gone.
>      - You can omit the installation of the mod in `Android/data` if you see the [texture error](#before-proceeding-ℹ️).
