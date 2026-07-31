## Phoenix-RTOS port Raspberry Pi 4B

Warning! This is a work-in-progress, experimental, AI-driven port of fantastic Phoenix RTOS (Real-Time Operating System) to Raspberry Pi 4B single board computer.

To learn more about official Phoenix RTOS go to: https://phoenix-rtos.com - it's an amazing project!

This port was 100% AI-authored - no signle line of code was written by hand (obviosuly I mean the "porting" code, not the original Phoenix RTOS which is proudly writtne by its authors).

Due to this, this work is to be consider higly experimental, risky, unstable, untested etc. You most likely should not use it for any purpose.

Yet, I did test it extensivley on a Raspberry Pi 4B 4GB board and it seems to work amazing. See here:
![Screenshot](rpi-phoenix-x11.jpg?raw=true "Phoenix RTOS on RPi4 with X11 running WMaker")

... and it runs **GPU accelerated Quake** in Full HD at ~40fps! Both **OpenGL** (Quakespasm) and **Vulkan** (vkQuake) ports are available showing that both graphics APIs work correctly with full hardware acceleration! This potentially opens a way to other graphics intensive software to be ported. Note that for now GPU applications can work only in fullscreen mode outside of X11 (like in old DOS times). This will likely change in the future. 

More details, screenshot and video recording will be published here soon.

To start look at https://github.com/rpi-phoenix-rtos/rpi-phoenix-rtos-coordination repo - there is a build instruction.
