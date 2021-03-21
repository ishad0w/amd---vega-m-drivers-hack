# Intel 8I7HVK "Radeon RX Vega M GH" Driver Hack.
... with fully working AMD Software.

Long story short. Intel and AMD has drop support for Radeon RX Vega M.

* Last BETA driver - [20.4.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-4-1).
* Last WHQL driver - [20.2.2](https://www.amd.com/ru/support/kb/release-notes/rn-rad-win-20-2-2).

# DISCLAIMER: I take no responsibility for damage to your hardware. You do this at your own risk. 
That being said, we want the latest and greatest, so moving on... (c) __jcmlsn__

# Hack-to!
* __Clean install is preferred. Use [DDU](https://www.guru3d.com/files-details/display-driver-uninstaller-download.html) for driver uninstall and Windows Driver update disabling.__

1. Go to [Releases](https://github.com/ishad0w/amd---vega-m-drivers-hack/releases) and get latest one ZIP release (or WHQL).
2. Download driver from release notes link. (Original AMD Driver).
3. Execute. Wait for unpack and error. :)
4. Go to C:\AMD\\__DRIVER_NAME__\Packages\Drivers\Display\WT6A_INF\ and make a backup of \*.inf files that we will replace next.
5. Go to Windows Settings, Updates & Security, Recovery, Advanced startup, Restart now, Troubleshoot, Advanced options, Startup settings. 
6. When Windows Starts up choose option 7 (Disable driver signature enforcement). (Press F7).
7. Replace files in C:\AMD\\__DRIVER_NAME__\ with extracted files from release.
8. Run __Setup.exe__.
9. When prompted “driver is not signed” continue anyway. Error alert may appear (if not clean install) at the installation end. it’s ok.
10. Do not restart PC yet! (Just close installation window).
11. Restore original \*.inf files in C:\AMD\\__DRIVER_NAME__\Packages\Drivers\Display\WT6A_INF\.
12. Manually update your Display Driver by launching "Device Manager" ("WinFlag" + "R", followed by "devmgmt.msc") and right-clicking "Display adapters > 'Radeon RX Vega M GH/GL'", followed by "Update driver".
13. Choose "Browse my computer for driver software", followed by "Let me pick from a list of available drivers on my computer".
14. Paste full path to folder C:\AMD\\__DRIVER_NAME__\Packages\Drivers\Display\WT6A_INF\ don't click "Browse..."!
15. Once you've entered the correct path, click "OK", and a list will be populated with available drivers to use. 
16. Select the first "Radeon RX Vega". It will prompt you a warning, click "Yes" to proceed.
17. Wait until screen stop "blinking".
18. Restart!
19. You are ready to go with Latest AMD driver and fully working AMD Software.

Not the easiest way, but working pretty great.

// Many thanks to __jcmlsn__ and __msrl__ from community.{amd,intel}.com. :)
