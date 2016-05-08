# OS X El Capitan on W230ST

Clover configuration for OS X El Capitan (10.11.4) on laptop Clevo W230ST

To begin with Clover install check <a href="http://www.tonymacx86.com/threads/guide-booting-the-os-x-installer-on-laptops-with-clover.148093/">this link</a>

## Configuration

|  computer part       |  components                         |
|----------------------|-------------------------------------|
| Mobo                 | Clevo W230ST                        |
| CPU                  | Core i7 4702MQ 2.2Ghz               |
| IGPU                 | Intel HD4600                        |
| RAM                  | 16Go                                |
| Ethernet controller  | Realtek RTL8111/8168/8411 PCI       |
| Wifi/BT              | BCM4352 (Bluetooth 4.0) (half-size) |

## Current state

| features                 |  state     |
|--------------------------|------------|
| IGPU                     |   OK       |
| GPU Harware acceleration |   OK       |
| Wifi                     |   OK       |
| Bluetooth                |   OK       |
| Computer sleep           |   OK       |
| Display sleep            |   OK       |
| Lid open/close + sleep   |   OK       |
| HDMI video               |   TO FIX   |
| HDMI audio               |   TO FIX   |
| USB2.0                   |   OK       |
| USB3.0                   |   OK       |
| Backlight                |   OK       |
| Battery status           |   OK       |
| Speaker + Headphones     |   OK       |

## HDMI issues

At this moment, HDMI video is not working on this configuration. <br/>Actually, It is working if you set `IntelGFX` to `0x0` instead of `0x04128086` in `config.plist` but doing this, you will lose hardware acceleration which will give some glitches when moving windows and other display issues...

## DSDT patch used 

From https://github.com/RehabMan/Laptop-DSDT-Patch :

* "Fix _WAK Arg0 v2"
* "HPET Fix"
* "SMBUS Fix"
* "IRQ Fix"
* "RTC Fix"
* "OS Check Fix"
* "Fix Mutex with non-zero SyncLevel"
* "Fix PNOT/PPNT"
* "Add IMEI"
* "Brightness Fix"

check <a href="http://www.tonymacx86.com/threads/guide-patching-laptop-dsdt-ssdts.152573/">this patching guide</a>

## DGPU

I didn't test GeForce GTX 765M since I cant disable IGPU from bios (all rendering is going through igpu)

## Attempts so far to fix HDMI

* frame buffer edit (trial/error with connector types)
* dsdt/ssdt patches (from https://github.com/RehabMan/Laptop-DSDT-Patch)

## Credits

* <a href="https://github.com/RehabMan">Rehabman</a>
* <a href="https://github.com/toleda">Toleda</a>
* <a href="https://github.com/Piker-Alpha">Piker-Alpha</a>
* <a href="https://github.com/the-darkvoid">the-darkvoid</a>
* http://www.tonymacx86.com
* http://www.insanelymac.com 

## External ressources

* <a href="http://www.tonymacx86.com/threads/volume-adjustment-and-display-brightness-control.147851/">volume-adjustment-and-display-brightness-control</a>
* <a href="http://www.tonymacx86.com/threads/guide-patching-laptop-dsdt-ssdts.152573/">guide-patching-laptop-dsdt-ssdts</a>
* <a href="http://www.tonymacx86.com/threads/fix-hd4200-hd4400-hd4600-hd5600-on-10-11.175797/">fix-hd4200-hd4400-hd4600-hd5600-on-10-11</a>
* <a href="http://www.tonymacx86.com/threads/guide-intel-igpu-hdmi-dp-audio-sandy-ivy-haswell-broadwell.189495/">guide-intel-igpu-hdmi-dp-audio-sandy-ivy-haswell-broadwell</a>
* <a href="http://forum.osxlatitude.com/index.php?/topic/1969-guide-for-enabling-vga-and-hdmi-in-intel-hd3000-gpu/">guide-for-enabling-vga-and-hdmi-in-intel-hd3000-gpu</a>
* <a href="http://www.tonymacx86.com/threads/guide-booting-the-os-x-installer-on-laptops-with-clover.148093/">guide-booting-the-os-x-installer-on-laptops-with-clover</a>
* https://github.com/toleda/wireless_half-mini
* https://github.com/RehabMan/OS-X-Fake-PCI-ID
* https://github.com/Piker-Alpha/AppleIntelFramebufferAzul.sh
* https://github.com/toleda/audio_CloverHDMI
* https://github.com/RehabMan/OS-X-MaciASL-patchmatic
* https://github.com/RehabMan/Laptop-DSDT-Patch
* https://github.com/the-darkvoid/XPS9530-OSX
* https://github.com/toleda/graphics_Intel_framebuffers
* https://github.com/RehabMan/OS-X-Clover-Laptop-Config
