## Phoenix-RTOS port Raspberry Pi 4B

Warning! This is a work-in-progress, experimental, AI-driven port and *extension* of the fantastic Phoenix RTOS (Real-Time Operating System) to Raspberry Pi 4B single board computer. In this project, not only did we port the system to Pi4, but we also ported a lot of software and made significant system extensions.

To learn more about official Phoenix RTOS go to: https://phoenix-rtos.com - it's an amazing project!

This port is 100% AI-authored - no signle line of code was written by hand (obviosuly I mean the "porting" code, not the original Phoenix RTOS which is proudly writtne by its authors).

Due to this, this work is to be consider higly experimental, risky, unstable, untested etc. You most likely should **not** use it for any purpose. You have been warned. 

Yet, I (the human author) did use and test it extensivley on my Raspberry Pi 4B 4GB board and it seems to work amazingly well. Moreover the AI agent tested it over many hundreds of cold-boot ups on real device (AI driven testing on-device 100% automated in the project so AI agent is actually developing and testing on-device autonomously). This means, among other things, that the system is relatively stable and A LOT of bigger and smaller bugs have been fixed along the way. Obviously, it is VERY far from being useful as a "desktop" - but obviously Pheonix-RTOS was never meant to be a desktop OS.

On the other hand, see here - we are pretty desktop-looking already:
![Screenshot](rpi-phoenix-x11.jpg?raw=true "Phoenix RTOS on RPi4 with X11 running WMaker")

On the screen you see Xorg running Window Maker and a number of apps ported. All these functionalities are not present at all in the up-stream Phoenix-RTOS. But this is not all!

... as our fork of Phoenix-RTOS runs **GPU accelerated Quake** in Full HD at ~40fps! Both **OpenGL** (Quakespasm) and **Vulkan** (vkQuake) ports are available showing that both graphics APIs work correctly with full hardware acceleration! 

Moreover it runs **Quake 2** and **Quake 3** with full **GPU acceleration** and reasonable performance. Recently it also started to run SuperTuxKart (yet, for now at around 10fps in 1080p).

Note, that for now GPU games work only in fullscreen mode outside of X11 (like in old DOS times). There is an experimental X11 variant using glamor GPU acceleration, which supports windowed OpenGL applications, but for now this is slow and doesn't really support the ported games (only some small demos).

In addition more software ports and system changes are provided including support for **full CPython**, SQLite, Redis, **bash and coreutils**, simple ML model inference, ffmpeg **video playback** and more. In order to get this running, some system-level, and libphoenix-level changes / improvements were implemented (for example support of dynamic loading).

The default "easy" way of testing the system is via SD card. BUT, there is also support for netboot with TFTP kernel and NFS rootfs! Yet, in order to have such an environment - you need to have a Linux host (or VM or container) that would host the netboot environment (instructions for this are provided). 

This is a **work in progress** with frequent commits and documentation updates. 

See here: https://youtu.be/LH-CkSJ_nL8 for a boring screencast (no audio) of the system running. Grabbed with an HDMI grabber connected to the HDMI out of Rpi4 board. Edited by AI (cut of multiple recordings). 

To start look at https://github.com/rpi-phoenix-rtos/rpi-phoenix-rtos-coordination repo - there is a build/run instruction documentation. Build is fully Docker based, so you can safely build your an SD card image in a sandboxed container on any platform supporting Docker. With an SD card image, just flash it an empty card and boot your Pi4. It should "just work".

You can also test it with qemu, yet keep in mind qemu doesn't emulate GPU and many other RPi4 devices, so the experience will be VERY limited. Since there is a **fully autonomous on-device testing**, support for qemu is not a priority. 
