## Phoenix-RTOS port Raspberry Pi 4B

Warning! This is a work-in-progress, experimental, AI-driven port and *extension* of the fantastic Phoenix RTOS (Real-Time Operating System) to Raspberry Pi 4B single board computer. In this project, not only did we port the system to Pi4, but we also ported a lot of software and made significant system extensions.

To learn more about official Phoenix RTOS go to: https://phoenix-rtos.com - it's an amazing project!

This port is 100% AI-authored - no signle line of code was written by hand (obviosuly I mean the "porting" code, not the original Phoenix RTOS which is proudly writtne by its authors).

Due to this, this work is to be consider higly experimental, risky, unstable, untested etc. You most likely should **not** use it for any purpose. You have been warned. 

Yet, I (the human author) did use and test it extensivley on my Raspberry Pi 4B 4GB board and it seems to work amazingly well. See here:
![Screenshot](rpi-phoenix-x11.jpg?raw=true "Phoenix RTOS on RPi4 with X11 running WMaker")

On the screen you see Xorg running Window Maker and a number of apps ported. All these functionalities are not present at all in the up-stream Phoenix-RTOS. But this is not all!

... as our fork of Phoenix-RTOS runs **GPU accelerated Quake** in Full HD at ~40fps! Both **OpenGL** (Quakespasm) and **Vulkan** (vkQuake) ports are available showing that both graphics APIs work correctly with full hardware acceleration! 

Moreover it runs **Quake 2** and **Quake 3** with full **GPU acceleration** and reasonable performance.

Note that for now GPU applications can work only in fullscreen mode outside of X11 (like in old DOS times). This will likely change in the future. 

In addition more software ports and system changes are provided including support for **full CPython**, SQLite, Redis, **bash and coreutils**, simple ML model inference, ffmpeg **video playback** and more. In order to get this running, some system-level, and libphoenix-level changes / improvements were implemented (for example support of dynamic loading).

This is a **work in progress** with frequent commits and documentation updates. It is not stable and not finished. 

More details, screenshot and video recording will be published here soon.

To start look at https://github.com/rpi-phoenix-rtos/rpi-phoenix-rtos-coordination repo - there is a build/run instruction documentation.
