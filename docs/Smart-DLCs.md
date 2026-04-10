# How to deal with micropatches and the packs folder

## Some info

> [!NOTE]
> In some updateds the developers releases some of the content in the packs folder, this usually happens when there are some bug fixes or events that will be later removed or merged in the Data folder when a major update is released.
> The packs folder has the same structure of the Data folder and if you take a look you may notice that some files are actually the same, when this happens the game will look for the file in the packs folder ignoring the one in the Data folder, so if a modification has a file that is in both Data and packs folder in order to work needs to be placed in the packs folder.

## Packs folder location

- Linux: `/home/<your username>/.local/share/Steam/steamapps/compatdata/444200/pfx/drive_c/users/steamuser/AppData/Local/wotblitz/packs/`
- Windows: `C:/Users/<your username>/AppData/Local/wotblitz/packs/`
- macOS: `/Users/<your username>/Library/Application Support/net.wargaming.wotblitz.macos/DAVAProject/packs`
- Android: check the [Android Modding Guide](https://github.com/thatmfrick/BlitzMods-Guides/blob/main/docs/Android.md).

## What to do if a mod is not working?

- The [Fake leggenday camouflages](https://blitz-mods.com/mod/camouflages/fake-legendary-camouflages-for-wotb-1142-274) mod, for example, is always affected when a micropatch is released.
- In order to make it working we have two solutions.

### Solution 1

1. Download the mod and simply install it in the packs folder: <img width="1890" height="565" alt="Screenshot_20260410_105942" src="https://github.com/user-attachments/assets/5534d026-0a1f-411b-8c03-95b97a0917df" />
2. Install the modification also in the Data folder.
> [!WARNING]
> You can skip this step if you have previously downloaded the modification (updated) in the Data folder and you noticed that it wasn't working, just intall into packs folder than and you are ready to go -> if the mod is not working check before if the packs folder is there, if is not than the mod is outdated or you have installed it incorrectly.

### Solution 2

If you don't want to install modifications here and there during a micropatch just do this trick:
**MOVE** to the **Data** folder those folders.
<img width="2390" height="623" alt="Screenshot_20260410_111744" src="https://github.com/user-attachments/assets/678ed837-5c9f-4d42-8935-d35f2a9d3ddb" />

> [!IMPORTANT]
> **DO NOT MOVE** those 4 files or the game will download at the startup all the packs folder content you moved to Data so you have done it for nothing...<img width="886" height="243" alt="Screenshot_20260410_112125" src="https://github.com/user-attachments/assets/ac832f24-b32d-456f-9a30-a9da7ccf94db" />


