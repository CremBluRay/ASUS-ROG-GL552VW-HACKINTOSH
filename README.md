# ASUS-ROG-GL552VW-HACKINTOSH MAC OS MOJAVE 10.14.5
## What Works
- Intel HD Graphics
- HDMI (widescreen displays have some issues)
- USB ports
- Keyboard (backlight doesn't work)
- Function Keys
- Ethernet
- Wifi (Replace the original with `BCM94352Z`
- Battery Status (Says zero percentage but it knows when charging)
- UVC HD Webcam
- Speaker and Microphone
- Touchpad (it's a pain to get working though)
## What doesn't work
- NVIDIA Optimus
- SD Card Reader
---
# Install Guide
1. Clone the repo with `git clone https://github.com/CremBluRay/ASUS-ROG-GL552VW-HACKINTOSH.git`
2. Use Unibeast to make a usb install drive (Replace the CLOVER and BOOT folders on the EFI partition of the drive with the folders from the repo).
3. Boot from the usb install drive
4. Use the arrow keys to select `Mac OS install from Install Mac OS` and press `Enter`
5. When the installer loads, select `Disk Utility`
6. In the menubar, select View > All Devices
7. Format the hard drive by clicking erase, naming it anything you'd like, formatting with MacOS exntended (Journaled), and selecting the GUID partitioning scheme.
8. When the drive is done formatting, close disk utility.
9. Click `Install Mac OS`
10. Select the drive you just formatted and install macOS. (If the computer restarts, DO NOT boot into the usb install drive in clover. Instead, boot into the drive you just formatted using clover).
11. During the install process, do not remove the usb install drive form the computer.
12. The computer may restart a few times, so be patient.
13. Eventually, the computer will boot and you'll be asked to setup an account the settings for the computer. You may need to plug in a usb mouse to be able to progress through the setup.
14. Once finished with the setup, use clover configurator to mount the EFI of the hard drive.
15. In the EFI partition, you'll see a folder called EFI. (If you don't see this, make one and drag the folder labelled Apple into it as well). Open it and place the BOOT and CLOVER folders from the usb install drive into the folder (next to the folder labelled Apple). This will install clover onto the partition and you can now safely eject the usb install drive.
16. Open terminal and type `sudo trimforce disable` (this will make boot time much faster).
17. Done!
---

# Optional
You can read [this guide](https://github.com/fidele007/Asus-ROG-GL552VW-Hackintosh/wiki/TouchPad-with-VoodooI2C) by [fidele007](https://github.com/fidele007) for a tutorial on how to get the trackpad working.
### Thanks to:
- [fidele007](https://github.com/fidele007) for the original project and guide
- [RehabMan](https://www.tonymacx86.com/members/rehabman.429483/) for all the amazing guides and kexts
- [toleda](https://www.tonymacx86.com/members/toleda.2393/) for his [Broadcom WiFi/Bluetooth [Guide]](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/)
- [u/corpnewt](https://www.reddit.com/user/corpnewt) for the [vanilla guide](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/) which walks you through the steps in making a Hackintosh happen for each CPU architecture
- [alexandred](https://github.com/alexandred) and other contributors to the project [VoodooI2C](https://github.com/alexandred/VoodooI2C) who made the support for ASUS's ELAN touchpad possible
- [acidanthera](https://github.com/acidanthera) for their work on [AppleALC](https://github.com/acidanthera/AppleALC) and [Lilu](https://github.com/acidanthera/Lilu)
- Everyone else on the tonymacx86 forums
