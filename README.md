# Intel® NUC 8i7HVK/8i7HNK "Radeon RX Vega M" Driver Hack
...with a fully functional AMD Software suite.

> **Project is discontinued.**  
> Intel and AMD have officially dropped support for the Radeon RX Vega M.  
> **Use at your own risk.**

---

## Overview

### Official Radeon RX Vega M drivers:
- **Last WHQL driver:** [20.2.2](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-2-2)
- **Last Beta driver:** [20.4.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-4-1)
- **Last “Stable” driver (IMHO):** [20.3.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-20-3-1)

#### Intel’s Recommended Version
- **Radeon™ RX Vega M Graphics Driver for Windows® 10 64-bit for NUC8i7HVK** (from Intel Download Center):  
  [Download Link](https://downloadcenter.intel.com/download/28600/Radeon-RX-Vega-M-Graphics-Driver-for-Windows-10-64-bit-for-NUC8i7HNK-NUC8i7HVK)

> Many users also recommend [19.12.1](https://www.amd.com/en/support/kb/release-notes/rn-rad-win-19-12-1) for heavy workloads (e.g. [Adobe compatibility issues](https://community.intel.com/t5/Intel-NUCs/HELP-Hades-Canyon-NUC8i7HVKVA-with-AMD-Adrenaline-freezes/m-p/1191030)).

---

## Disclaimer
I take **no responsibility** for any damage to your hardware. You proceed **at your own risk**.  
That being said, if you want the latest AMD Adrenaline driver and software for your Radeon RX Vega M, here is a method that has worked for many.

---

## Hack Instructions

> **Tip:** A clean install is preferred. Use [DDU (Display Driver Uninstaller)](https://www.wagnardsoft.com/display-driver-uninstaller-ddu-) to remove existing drivers and disable Windows Driver Updates before proceeding.

1. **Download Required Files:**
   1. Go to [Releases](https://github.com/ishad0w/amd---vega-m-drivers-hack/releases) on GitHub and download the latest ZIP release (or WHQL release if available).
   2. Download the desired driver from the release notes link (the official AMD driver, e.g., 20.2.2, 20.4.1, etc.).

2. **Extract and Prepare:**
   1. Run the downloaded AMD driver setup. It will unpack and then likely error out (since the hardware is not officially supported).
   2. Navigate to `C:\AMD\DRIVER_NAME\Packages\Drivers\Display\WT6A_INF\` and make a backup of all `*.inf` files.  
      *(You can skip this if you previously downloaded the original INFs from the GitHub release assets.)*

3. **Disable Driver Signature Enforcement:**
   1. Go to **Windows Settings** → **Update & Security** → **Recovery** → **Advanced startup** → **Restart now**.
   2. After reboot, select **Troubleshoot** → **Advanced options** → **Startup settings**.
   3. When the system restarts again, press **F7** (or option **7**) to **Disable driver signature enforcement**.

4. **Replace INF Files:**
   1. From the ZIP you downloaded in Step 1, extract the modified INF files.
   2. Replace the files in `C:\AMD\DRIVER_NAME\` (and its subfolders as indicated) with the modified versions.

5. **Install the Driver:**
   1. Run `Setup.exe` in `C:\AMD\DRIVER_NAME\`.
   2. If prompted about unsigned drivers, click **Install this driver software anyway**.
   3. If you get an error alert at the end (especially if it wasn’t a completely clean install), ignore it for now.
   4. **Do not restart** when prompted. Close the installation window instead.

6. **Restore Original INF Files:**
   1. Copy the backup `*.inf` files back to `C:\AMD\DRIVER_NAME\Packages\Drivers\Display\WT6A_INF\`.
   2. This ensures the final manual driver update will reference valid (original) INF files.

7. **Manually Update Driver in Device Manager:**
   1. Press **Win + R**, type `devmgmt.msc`, and press **Enter**.
   2. In **Device Manager**, expand **Display adapters**.
   3. Right-click on **Radeon RX Vega M GH/GL** (it may show a warning icon) and select **Update driver**.
   4. Choose **Browse my computer for driver software**.
   5. Choose **Let me pick from a list of available drivers on my computer**.
   6. Click **Have Disk...**, then enter the full path to `C:\AMD\DRIVER_NAME\Packages\Drivers\Display\WT6A_INF\`.
      > **Important:** Do not just click “Browse...” again; you must manually enter the path.
   7. Click **OK**. A list of available drivers should appear.
   8. Select the **first** listed **Radeon RX Vega** driver (it may be titled slightly differently, but it should be the top option).
   9. A warning message will pop up. Click **Yes** to confirm.

8. **Finish Up:**
   1. Wait for the driver to finish installing (your screen may flicker).
   2. **Restart your PC** once the installation completes.

After the reboot, your Radeon RX Vega M should be running the newer AMD Adrenaline software with all features enabled. 

---

## Credits
- **jcmlsn**, **msrl**, and other community members from [community.amd.com](https://community.amd.com/) and [community.intel.com](https://community.intel.com/) for their research and shared knowledge.
- Everyone else who has contributed to or tested this workaround.

---

**Enjoy the latest AMD driver and software on your Intel NUC!**
