---

# chromebook-fedora-install

Linux installation documentation on ChromeOS hardware.

## Project Goal

Replacing the default ChromeOS with a full-fledged Fedora Linux distribution to create a flexible environment for learning server administration and using Docker.

## Hardware & Technologies

* **Device:** Lenovo ThinkPad Yoga C13
* **Operating System:** Fedora Linux
* **Tools:** USB flash drive, hardware servicing tools (for case disassembly)
* **Firmware:** MrChromebox Firmware Utility Script, coreboot (open-source UEFI)

## Main Challenges & Setup Process

* **Enabling Developer Mode:** The first step was switching the Chromebook into Developer Mode, which provided access to the advanced system console (`crosh` -> `shell`).
* **Bypassing Hardware Protection (Write Protect):** The motherboard had a factory lock preventing BIOS overwriting. To bypass it, I had to physically disassemble the laptop and disconnect the internal battery. This hardware intervention unlocked write access to the chip's memory.
* **Flashing New UEFI:** After bypassing the hardware lock, I used the MrChromebox utility script to wipe the locked factory firmware and flash an open UEFI firmware (coreboot).
* **Smooth OS Installation:** Following the firmware change, the computer successfully booted the Fedora installer from the USB drive. The system ran perfectly on the first boot, acting as a true "out of the box" experience with no missing drivers.

## Key Commands & Configuration

**Flashing Custom UEFI Firmware**
After accessing the root shell in Developer Mode, I downloaded and executed the MrChromebox firmware utility script to replace the default BIOS:

```bash
cd; curl -LO mrchromebox.tech/firmware-util.sh
sudo bash firmware-util.sh

```

## Final Result

The device has been completely freed from ChromeOS restrictions and now operates as a native Linux machine, fully capable of running local servers, containers, and network tools like Tailscale.
