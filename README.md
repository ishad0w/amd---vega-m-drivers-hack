# Intel 8I7HVK "Radeon RX Vega M GH" Driver Hack.
... with fully working AMD Software.

Long story short. Intel and AMD has drop support for Radeon RX Vega M.

__Official Drivers__:
* Last __WHQL__ driver - [20.2.2](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-2-2).
* Last __BETA__ driver - [20.4.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-4-1).
* Last __STABLE__ driver - [20.3.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-3-1). _IMHO_. 

Last "Intel Recommended" driver at __Download Center__ - [Radeon™ RX Vega M Graphics Driver for Windows® 10 64-bit for NUC8i7HVK](https://downloadcenter.intel.com/download/28600/Radeon-RX-Vega-M-Graphics-Driver-for-Windows-10-64-bit-for-NUC8i7HNK-NUC8i7HVK)

_Many people reccomends [19.12.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-19-12-1) for hard workloads. [Adobe compatibility](https://community.intel.com/t5/Intel-NUCs/HELP-Hades-Canyon-NUC8i7HVKVA-with-AMD-Adrenaline-freezes/m-p/1191030)._

# DISCLAIMER: I take no responsibility for damage to your hardware. You do this at your own risk. 
That being said, we want the latest and greatest, so moving on... (c) __jcmlsn__

# Hack-to!
* __Clean install is preferred. Use [DDU](https://www.wagnardsoft.com/display-driver-uninstaller-ddu-) for driver uninstall and Windows Driver update disabling.__

__FYI__: You can download original INFs or WHOLE original driver from release files.

1. Go to [Releases](https://github.com/ishad0w/amd---vega-m-drivers-hack/releases) and get latest one ZIP release (or WHQL).
2. Download driver from release notes link. (Original AMD Driver).
3. Execute. Wait for unpack and error. :)
4. Go to C:\AMD\\__DRIVER_NAME__\Packages\Drivers\Display\WT6A_INF\ and make a backup of \*.inf files that we will replace next. (You can Skip this step, if you early downloaded original INFs from release assets).
5. Go to Windows Settings, Updates & Security, Recovery, Advanced startup, Restart now, Troubleshoot, Advanced options, Startup settings. 
6. When Windows Starts up choose option 7 (Disable driver signature enforcement). (Press F7).
7. Replace files in C:\AMD\\__DRIVER_NAME__\ with extracted files from release.
8. Run __Setup.exe__.
9. When prompted “driver is not signed” continue anyway. Error alert may appear (if not clean install) at the installation end. it’s ok.
10. Do not restart PC yet! (Just close installation window).
11. Restore original \*.inf files in C:\AMD\\__DRIVER_NAME__\Packages\Drivers\Display\WT6A_INF\.
12. Manually update your Display Driver by launching "Device Manager" ("WinFlag" + "R", followed by "devmgmt.msc") and right-clicking "Display adapters > 'Radeon RX Vega M GH/GL'", followed by "Update driver".
13. Choose "Browse my computer for driver software", followed by "Let me pick from a list of available drivers on my computer" and then click on "__I have disk__”.
15. Paste full path to folder C:\AMD\\__DRIVER_NAME__\Packages\Drivers\Display\WT6A_INF\ don't click "Browse..."!
16. Once you've entered the correct path, click "OK", and a list will be populated with available drivers to use. 
17. Select the __first__ "__Radeon RX Vega__". It will prompt you a warning, click "__Yes__" to proceed.
18. Wait until screen stop "blinking".
19. __Restart!__
20. You are ready to go with Latest AMD driver and fully working AMD Software.

Not the easiest way, but working pretty great.

// Many thanks to __jcmlsn__, __msrl__ and other __great people__ from community.{amd,intel}.com. :)
