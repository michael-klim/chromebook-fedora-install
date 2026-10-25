# chromebook-fedora-install
Linux installation documentation on ChromeOS hardware

# Installing Fedora Linux on a Chromebook (Lenovo ThinkPad Yoga C13)

## Project Goal
Replacing the default ChromeOS with a full-fledged Fedora Linux distribution.

## Hardware & Technologies
* **Device:** Lenovo ThinkPad Yoga C13
* **Operating System:** Fedora Linux
* **Tools:** USB flash drive, firmware scripts (MrChromebox), hardware servicing tools (for case disassembly)

## Main Challenges & Installation Process
* **Enabling Developer Mode:** The first step was switching the Chromebook into Developer Mode, which provided access to the advanced system console.
* **Bypassing Hardware Protection (Write Protect):** The motherboard had a factory lock preventing BIOS overwriting. To bypass it, I had to physically disassemble the laptop and disconnect the battery. Only this hardware intervention unlocked write access to the chip's memory.
* **Flashing New UEFI:** After bypassing the lock, I used the MrChromebox utility script to wipe the locked factory firmware and flash an open UEFI firmware (coreboot). 
* **Smooth OS Installation:** Following the firmware change, the computer successfully booted the installer from the USB drive. After installation, Fedora ran perfectly on the first boot, acting as a true "out of the box" experience with no missing drivers or hardware issues.

## Final Result
The device has been completely freed from ChromeOS restrictions and now operates as a native Linux machine.
