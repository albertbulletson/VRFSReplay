![image alt](https://github.com/albertbulletson/VRFSReplay/blob/37a474bbef265fbfb4291a19452c2b834a008aef/VRFSReplaylogo.png)

# VRFSReplay

A MelonLoader mod for the VRFS camera that turns it into a replay viewer. When the camera starts, a full-screen replay screen comes up. Enter a replay code and the camera takes you into that match. Nothing else opens.

Fan-made, not affiliated with VRFS.

## Setup

1. Install MelonLoader into your camera folder (the one with `Camera.exe`) and start the camera once.
2. Put `VRFSReplay.dll` in `Camera\Mods`.
3. Remove any older versions from `Mods` (`skuchangerandstuff.dll`, `skuchangerandstuff-replay.dll`).
4. Start the camera.

## How to use

- Type a replay code or paste it with **Ctrl+V**, then press **Enter** or **WATCH**.
- The screen is locked until a replay starts. After that, **F8** shows and hides it.
- Going back to the solo practice map locks the screen again until a new code is entered.
- Click the **star** next to a code (or press **Ctrl+D**) to favorite it. Favorites stay at the top.
- Click any recent or favorite code to watch it again. **Clear** empties the recent list.

## Good to know

- No account or login needed. Replays download the same way as the game's Replays menu.
- On first start, old replay history from earlier versions is cleared.
- Settings are in `Camera\UserData\MelonPreferences.cfg` (for example `PanelKey` and `PracticeScenes`).
- Favorites and recent codes are saved in `Camera\UserData`.
- If something breaks, send `Camera\MelonLoader\Latest.log`.
