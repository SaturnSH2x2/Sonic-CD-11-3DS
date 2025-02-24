![](header.png?raw=true)
# **THIS PORT IS DEPRECATED**
+ This port is no longer maintained. Please use Voxel9's [Sonic CD port](https://github.com/Voxel9/Sonic-CD-11-3DS-Redux/releases) instead.

# **SUPPORT THE OFFICIAL RELEASE OF SONIC CD**
+ Without assets from the official release this decompilation will not run.

+ You can get the official release of Sonic CD from:
  * [Windows (Via Steam)](https://store.steampowered.com/app/200940/Sonic_CD/)
  * [IOS (Via the App Store)](https://apps.apple.com/us/app/sonic-cd-classic/id454316134)
  * [Android (Via Google Play)](https://play.google.com/store/apps/details?id=com.sega.soniccd.classic&hl=en&gl=US)
  * [Android (Via Amazon)](https://www.amazon.com/Sega-of-America-Sonic-CD/dp/B008K9UZY4/ref=sr_1_2?dchild=1&keywords=Sonic+CD&qid=1607930514&sr=8-2)

Even if your platform isn't supported by the official releases, you **must** buy it for the assets (you dont need to run the official release, you just need the game assets)

# Features/Tweaks
* Complete stereoscopic 3D (HW build only)
* Video playback support courtesy @Oreo639's [3ds-theoraplayer](https://github.com/Oreo639/3ds-theoraplayer)
* Built-in mod support, accessible from the Dev Menu
* There is now a settings.ini file that the game uses to load all settings, similar to Sonic Mania
* Dev menu can now be accessed from anywhere by pressing the SELECT button if enabled in the config
* If `devMenu` is enabled in the config, pressing the R button will activate a palette overlay that shows the game's 8 internal palettes in real time

# How to build:
* Set up a working 3DS Homebrew Environment. You can find more information on this [here](https://www.3dbrew.org/wiki/Setting_up_Development_Environment).
* Make sure `SDL`, `SDL_mixer`, `3ds-dev`, `3ds-libvorbisidec`, `3ds-libtheora`, `3ds-mikmod`, and `3ds-libmad` are installed.
* Edit `RetroEngine.hpp` as necessary depending on what version of the port you want to build. If you want to build the software rendered version, set `RETRO_USING_C2D` to 0.
* Run `make -f Makefile.3ds`. Run `make -f Makefile.3ds cia` to build a `.cia` file.

# FAQ
### Q: What's the difference between HW and SW builds?
A: SW builds use software rendering, using the same basic rendering backend that the PC/console
ports of Sonic CD used. Rendering is more accurate, and all effects like scanline deformation and
realtime palettes are supported.  However, its rather CPU-intensive, and requires a N3DS to run at
full-speed.  HW builds use a completely custom Citro2D-based backend, using the 3DS's PICA200
to get graphics on-screen, and thus can run at full-speed on O3DS systems, in addition to 
supporting features like stereosopic 3D, however, certain features like realtime palettes aren't 
supported. tl;dr use HW if on O3DS or if you care about 3D, use SW if on N3DS.

### Q: Why is the port separated into HW and SW builds?
A: Because that's how the base decomp was set up initially, at the time the port was started.
I plan on integrating both backends into a single build eventually, however, this probably won't
happen until the HW backend is complete.

### Q: Why dont some buttons in the menu work?
A: Buttons like leaderboards & achievements require code to be added to support online functionality & menus (though they are saved anyways), and other buttons like the controls button on PC or privacy button on mobile have no game code and are instead hardcoded through callbacks, and I just didnt feel like going through the effort to decompile all that, since its not really worth it

### Q: I found a bug/I have a feature request!
A: Submit an issue in the issues tab and I'll fix/add it (if possible). Keep in mind, however, I won't fix bugs that aren't exclusive to the 3DS port; if the issue also occurs on the base decomp (i.e. on PC), you're better off submitting the issue to the [main branch](https://github.com/Rubberduckycooly/Sonic-CD-11-Decompilation).

### Q: Is there a port of the Sonic 1/Sonic 2 decompilation?
A: Yes! You can check out @JeffRuLz's RSDKv4 port [here](https://github.com/JeffRuLz/Sonic-1-2-2013-Decompilation).

### Q: Why is video playback so slow?
A: You're going to want to scale down your videos for them to run well on 3DS. You can find pre-scaled versions of the videos [here](https://gamebanana.com/mods/313570).

# Special Thanks
* [Rubberduckycooly](https://github.com/Rubberduckycooly): For decompiling CD in the first place, as well as helping me out with a few aspects of the port.
* [JeffRuLz](https://github.com/JeffRuLz): For implementing frame limiting and helping out with the SW backend, as well as for porting OpenHCL to the 3DS, which helped immensely in developing the Citro2D backend.
* [Oreo639](https://github.com/Oreo639): For helping out with the Makefile, as well as being behind [3ds-theoraplayer](https://github.com/Oreo639/3ds-theoraplayer), which the port uses to play back videos.

# Contact:
Join the [Retro Engine Modding Discord Server](https://dc.railgun.works/retroengine) for any extra questions you may need to know about the decompilation or modding it. My Discord is saturnsh2x2#3840, and while I'm not the most active on there, ping me if you have a question and I'll see what I can do.
