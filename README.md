==============================================================================
                                 VRFSReplay
                            by: Albert Bulletson
==============================================================================

A MelonLoader mod for the VRFS camera build that turns it into a dedicated
replay viewer. You start the camera, a full-screen replay screen comes up,
you type a replay code, and the camera takes you straight into that match.
Nothing else opens, nothing else runs in the background.

This is a fan-made mod. It is not made by, endorsed by, or affiliated with
the VRFS developers. "VRFS" and the VRFS logo belong to their owners.


------------------------------------------------------------------------------
 CONTENTS
------------------------------------------------------------------------------

  1.  What it does
  2.  What you need
  3.  Installing
  4.  First start
  5.  Watching a replay
  6.  The lock (how and when the screen locks)
  7.  Keys and controls
  8.  Settings (MelonPreferences.cfg)
  9.  Files the mod creates
  10. Updating
  11. Uninstalling
  12. Troubleshooting
  13. FAQ
  14. Privacy
  15. Credits


------------------------------------------------------------------------------
 1. WHAT IT DOES
------------------------------------------------------------------------------

  * Replay screen built into the game
      A full-screen screen is drawn by the game itself (Unity's own GUI).
      It does not use WebView2, Edge, a browser, a web server, a second
      window, or any other program. Everything lives inside the one
      VRFSReplay.dll file.

  * Locked until a replay is playing
      When the camera starts, the replay screen covers the whole display and
      cannot be closed. There is no close button, Escape does nothing, and
      the hide key does nothing. The game's own menus underneath it cannot
      be clicked while it is up. The only way forward is to enter a replay
      code.

  * Unlocks after a replay starts
      As soon as a replay you entered actually starts playing, the screen
      unlocks and hides itself. From then on you can bring it back and hide
      it again whenever you like (F8 by default), for example to load a
      different replay.

  * Locks again at the solo practice map
      Whenever the camera ends up on the solo practice map (for example when
      a replay finishes and the camera returns to it), the screen comes back
      and locks again until a new replay code is entered.

  * Watches replays in their own stadium
      Replays open the same way the game's Replays menu does: the camera
      downloads the replay and loads the stadium it was played in. It does
      not use the replay table.

  * Turns moderator and camera mode off for you
      The camera build normally starts with moderator / camera settings that
      get in the way of watching replays offline. VRFSReplay switches those
      off in the game's SystemSettings automatically, every time a scene
      loads. You do not need to touch anything.

  * Remembers your recent codes
      The last few codes you watched are shown under the Watch button. Click
      one to watch it again.

  * Waits for the camera if you are fast
      If you type a code before the camera has finished starting up, the mod
      keeps it and loads it the moment the camera is ready. You do not need
      to type it again.


------------------------------------------------------------------------------
 2. WHAT YOU NEED
------------------------------------------------------------------------------

  * The VRFS camera build (Camera.exe). Tested against camera 0.7.9 running
    on Unity 6000.3.20f1.
  * MelonLoader 0.7.x installed into the camera folder (0.7.3 was used while
    making this). MelonLoader must already work, meaning the camera starts
    with the MelonLoader console / log and creates the "Mods", "UserData",
    and "MelonLoader" folders.
  * Windows 10 or 11.
  * An internet connection (replays are downloaded from VRFS's replay
    servers by the game itself).

  You do NOT need:
  * a VRFS account or login
  * WebView2, Edge, or any browser
  * .NET installed separately (MelonLoader brings what it needs)
  * any other mod


------------------------------------------------------------------------------
 3. INSTALLING
------------------------------------------------------------------------------

  1. Close the camera completely if it is running.

  2. Open your camera folder. It is the folder that has Camera.exe in it,
     for example:

         C:\Users\<you>\Downloads\camera-0.7.9\Camera

  3. Open the "Mods" folder inside it. If there is no Mods folder,
     MelonLoader is not installed yet, or the camera has not been started
     once with MelonLoader. Install MelonLoader first and start the camera
     one time so the folders get created.

  4. Copy VRFSReplay.dll into the Mods folder:

         Camera\Mods\VRFSReplay.dll

  5. IMPORTANT: remove any other replay mod from the Mods folder. In
     particular, if you have any of these, move them out (to your desktop,
     for example):

         skuchangerandstuff.dll
         skuchangerandstuff-simple.dll
         skuchangerandstuff-replay.dll

     Those are older / bigger versions. If they stay in Mods next to
     VRFSReplay.dll, they also run, and some of them open their own window
     at startup, which is exactly what VRFSReplay is meant to avoid.

  6. Start Camera.exe as you normally would.

  That's it. There is nothing to configure for normal use.


------------------------------------------------------------------------------
 4. FIRST START
------------------------------------------------------------------------------

  When the camera starts you should see, in the MelonLoader console / log:

      VRFSReplay v1.x.x
      by Albert Bulletson

  followed by lines starting with [VRFSReplay].

  On screen, the replay screen appears almost right away: a dark screen
  with the VRFS REPLAY logo, a box for the code, and a WATCH button.

  Behind the screen the camera keeps starting up normally. It goes through
  its start-up scene and then the solo practice map (scene "SB"). This can
  take a few seconds. You can already type your code during that time; it
  will load as soon as the camera is ready.


------------------------------------------------------------------------------
 5. WATCHING A REPLAY
------------------------------------------------------------------------------

  1. Get a replay code. These are the share codes from VRFS, usually 11 to
     13 digits, for example 1706752452098.

  2. Put it into the box:
       - type it, or
       - copy it anywhere (Discord, a browser, ...) and press Ctrl+V while
         the replay screen is up.
     Only letters, digits, "-" and "_" are accepted, so spaces or other
     characters that come along when you copy are dropped automatically.
     Backspace deletes one character, Ctrl+Backspace clears the box.

  3. Press Enter or click WATCH.

  4. The button changes to LOADING and a thin progress bar shows the
     download. The line under it tells you what is happening.

  5. When the replay is downloaded, the camera switches to the stadium the
     match was played in. The replay screen unlocks and hides itself.

  6. Watch the replay with the camera's normal controls.

  To watch another one, press F8 to bring the screen back, enter the new
  code, and press Enter. Press F8 or Escape (or click "Hide · F8" in the top
  right corner) to hide the screen again without loading anything.

  Recent codes: under the WATCH button you see up to three codes you
  watched before. Click one to load it again immediately.

  If something goes wrong (wrong code, replay deleted, no internet), the
  line under the button turns red and tells you. The screen stays up so you
  can try another code.


------------------------------------------------------------------------------
 6. THE LOCK (HOW AND WHEN THE SCREEN LOCKS)
------------------------------------------------------------------------------

  The screen has two states:

  LOCKED
    * Covers the whole screen, nothing behind it is visible.
    * Cannot be hidden: no close button, F8 and Escape do nothing.
    * The game's own clickable menus underneath are switched off.
    * The mouse cursor is always shown and free so you can click.

  UNLOCKED
    * Same screen, plus "Hide · F8" in the top right corner.
    * F8 (or Escape, or clicking Hide) hides it, F8 brings it back.
    * When hidden, the game behaves completely normally.

  It becomes LOCKED:
    * every time the camera starts, and
    * every time the camera loads a solo practice map. By default that is
      the scene called "SB" (the map the camera sits on before and after
      replays). Any scene whose name contains "practice", "training" or
      "solo" counts too. You can add more scene names, see section 8.

  It becomes UNLOCKED:
    * only when a replay code you entered has successfully started playing.
      Typing a wrong code, or a failed download, does not unlock it.

  Note: nothing can stop Windows itself. Alt+Tab, the Windows key and
  Alt+F4 still work as usual; the lock is about the camera, not the PC.


------------------------------------------------------------------------------
 7. KEYS AND CONTROLS
------------------------------------------------------------------------------

  While the replay screen is up:

    0-9, letters, - _  type into the code box
    Ctrl+V             paste a code from the clipboard
    Backspace          delete the last character
    Ctrl+Backspace     clear the box
    Enter              watch the code in the box
    Click a recent     watch that code again
    Escape             hide the screen (only when unlocked)
    F8                 hide the screen (only when unlocked)

  While the replay screen is hidden:

    F8                 show the replay screen again

  F8 can be changed, see PanelKey in section 8.


------------------------------------------------------------------------------
 8. SETTINGS (MelonPreferences.cfg)
------------------------------------------------------------------------------

  Settings are stored by MelonLoader in:

      Camera\UserData\MelonPreferences.cfg

  The file is created after the first start. Close the camera before
  editing it, then save and start the camera again. You normally never need
  to change anything here.

  [VRFSReplay_Lock]

    PracticeScenes = "SB"
        Scenes that lock the screen when the camera loads them. Separate
        several names with commas, e.g. "SB,MyOtherMap". Scene names are
        shown in the MelonLoader log as "Scene loaded: [number] name".
        Names containing practice / training / solo always lock, even if
        they are not listed.

  [VRFSReplay]

    PanelKey = "F8"
        The key that shows / hides the screen once it is unlocked. Use a
        Unity key name, for example "F6", "F9", "Insert", "BackQuote".

    UseWatchReplay = true
        true  = replays open in their own stadium (recommended).
        false = replays load into the replay table instead.

    OfflineReplayMode = true
        Turns moderator off and keeps it off. Leave this on.

    KeepCameraOff = true
        Turns the SystemSettings "camera" flag off and keeps it off. Leave
        this on.

    KeepDebugOn = false
        Turns the game's debug flag on when true. Not needed for replays.

    UseReplayTableController = true
        Only used when UseWatchReplay is false. Picks which part of the game
        handles replay-table loading.

    StartupScene, ForceReloadStartup, SkipCalibration, ReplaySceneToLoad,
    BlockModeratorComponent
        Advanced start-up options. Leave them as they are unless you know
        what you are changing.

  The section also contains a few entries that only the bigger version of
  the mod uses (SKU / app settings). VRFSReplay ignores them.


------------------------------------------------------------------------------
 9. FILES THE MOD CREATES
------------------------------------------------------------------------------

  Camera\UserData\MelonPreferences.cfg
      The settings above (shared with any other MelonLoader mods).

  Camera\UserData\VRFSReplay_recent.txt
      Your last replay codes, one per line. Delete it to clear the recent
      list.

  Camera\MelonLoader\Latest.log  (and MelonLoader\Logs\...)
      MelonLoader's log. VRFSReplay writes short lines into it, for example
      which scene loaded, when a replay was requested, and whether it
      loaded. This is the first thing to look at, or send, when something
      does not work.

  The mod does not create any other files, does not write into the game's
  own files, and does not change anything outside the camera folder.


------------------------------------------------------------------------------
 10. UPDATING
------------------------------------------------------------------------------

  1. Close the camera.
  2. Replace Camera\Mods\VRFSReplay.dll with the new one.
  3. Start the camera.

  Your settings and recent codes are kept.

  If Windows says the file is in use, the camera is still running (check
  the taskbar / Task Manager for Camera.exe) and has to be closed first.


------------------------------------------------------------------------------
 11. UNINSTALLING
------------------------------------------------------------------------------

  1. Close the camera.
  2. Delete Camera\Mods\VRFSReplay.dll.
  3. Optional: delete Camera\UserData\VRFSReplay_recent.txt and remove the
     [VRFSReplay] and [VRFSReplay_Lock] sections from
     Camera\UserData\MelonPreferences.cfg.

  The camera then starts exactly like before.


------------------------------------------------------------------------------
 12. TROUBLESHOOTING
------------------------------------------------------------------------------

  The replay screen never shows up
    * Check that the file is in Camera\Mods (not in Camera, not in
      UserData, not inside another folder).
    * Check the MelonLoader console / log. You should see "VRFSReplay" and
      "by Albert Bulletson" near the top. If it is not listed, MelonLoader
      did not load it: make sure the file is not blocked by Windows
      (right-click VRFSReplay.dll > Properties > tick "Unblock" if it is
      there > OK).
    * Make sure MelonLoader itself works (the console / log appears when
      the camera starts).

  A web window / app window still opens at startup
    * An older mod is still in the Mods folder. Remove
      skuchangerandstuff.dll / skuchangerandstuff-simple.dll /
      skuchangerandstuff-replay.dll (see Installing, step 5).

  Two replay screens, or things happen twice
    * Same reason: two versions of the mod are in Mods. Keep only
      VRFSReplay.dll.

  "The camera is still starting..." for a long time
    * The camera has not reached the solo practice map yet. Wait. If it
      takes more than about three minutes the mod gives up and tells you to
      restart the camera. Restart it and try again.

  "Could not load <code>..."
    * Check the code for typos.
    * The replay may have been deleted from VRFS's servers, or the code is
      not a replay share code.
    * Check your internet connection.
    * VRFS's replay server may be down for a moment. Try again later.

  The screen unlocked but I see the practice map instead of the replay
    * The download worked but the stadium is still loading. Give it a few
      seconds.
    * If it keeps happening, set UseWatchReplay = true in the settings (it
      is the default).

  The screen locks again right after the replay starts
    * The camera went back to the practice map, for example because the
      replay is very short and already ended. This is expected; enter the
      code again to rewatch it.
    * If a map that is not a practice map locks the screen, its name
      contains "practice", "training" or "solo". That always counts as a
      practice map.

  F8 does nothing
    * F8 only works after a replay has started (the screen is locked until
      then; that's on purpose).
    * Another program may be using F8. Change PanelKey to a different key.

  Ctrl+V does not paste
    * Make sure the replay screen is showing and the code was copied as
      text. You can always type the code instead.

  The text or logo looks tiny / huge
    * The screen scales with the camera window size. Run the camera in a
      normal resolution (720p or bigger) for the best result.

  Sending a bug report
    * Close the camera right after the problem happens and send
      Camera\MelonLoader\Latest.log together with the replay code you used
      and a short description or screenshot.


------------------------------------------------------------------------------
 13. FAQ
------------------------------------------------------------------------------

  Do I need a VRFS account?
    No. Replay codes are downloaded by the camera the same way the game's
    own Replays menu does it, without logging in.

  Does this work in the normal VRFS game?
    It is made for the camera build. The normal game is not supported.

  Can people get past the lock?
    Not from inside the camera. The screen cannot be hidden until a replay
    is playing, and the game's menus below it are switched off. Windows
    shortcuts like Alt+Tab or Alt+F4 still work because those belong to
    Windows, not the camera.

  Why does it lock again on the practice map?
    So the camera always ends up in one of two states: watching a replay,
    or asking for one. When a replay ends and the camera goes back to the
    practice map, the replay screen takes over again.

  Can I change the colors / logo?
    Not from the settings. The logo and colors are built into the DLL.

  Does it use WebView2 / a browser / a local web server?
    No. It is drawn with Unity's own GUI inside the game. No other process
    is started and no network port is opened.

  Does it send anything anywhere?
    No. See Privacy.

  Can I run it together with the bigger skuchangerandstuff mod?
    No, use one or the other. They share parts and would both run.


------------------------------------------------------------------------------
 14. PRIVACY
------------------------------------------------------------------------------

  * VRFSReplay itself makes no network connections. Replays are downloaded
    by the camera's own replay code, exactly like the game's Replays menu.
  * No accounts, keys, passwords or tokens are asked for, stored or sent.
  * Nothing is uploaded, tracked or reported.
  * The only things written to disk are the settings, your recent replay
    codes, and short lines in MelonLoader's log (see section 9).


------------------------------------------------------------------------------
 15. CREDITS
------------------------------------------------------------------------------

  VRFSReplay ............ Albert Bulletson
  MelonLoader ........... LavaGang and contributors (melonwiki.xyz)
  Il2CppInterop ......... BepInEx / Il2CppInterop contributors
  Rubik font (logo) ..... Hubert & Fischer, Meir Sadan, Cyreal,
                          SIL Open Font License 1.1
  VRFS .................. the VRFS team. VRFS and the VRFS logo are theirs.
                          This mod is unofficial.

==============================================================================
