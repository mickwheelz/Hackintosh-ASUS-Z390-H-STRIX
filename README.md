# Hackintosh-ASUS-Z390-H-STRIX

**Very** basic guide to hackintosh your ASUS Z390-H Strix based machine using opencore

https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/ is **the** resouece for using opencore, it covers everything you need to know.

## Getting Started

You need a 4gb or larger USB flash drive to begin. You also need a working windows, mac or linux install on your target machine. I used the windows tools as detailed in the guide [here](https://khronokernel-2.gitbook.io/opencore-vanilla-desktop-guide/opencore-efi)

Once you have done this, then move on to the 'Gathering files' section of this repo (and the tutorial)

## Gathering files

I have not included the files needed in this repo (aside from SSDT/DSDTs), as they not my work. You will need to download them from the links under each section (or in some cases use what was included with OpenCore)

### Drivers

The three drivers needed for this board are

`ApfsDriverLoader.efi` APFS DriverSSDT-PLUG, get this [here](https://github.com/acidanthera/AppleSupportPkg/releases)

`FwRuntimeServices.efi` - Patch for boot.efi and NVRAM fixes, this is included with OpenCore

`HFSPlus.efi` HFS+ Driver, get this [here](https://cdn.discordapp.com/attachments/606452360495104000/633621011887292416/HFSPlus.efi)

These should be dowloaded from the links above and placed in the `/OC/Drivers` folder

### Kexts

`Lilu.kext` - Required to use WhateverGreen and AppleALC and recomended for VirtualSMC, get it [here](https://github.com/acidanthera/Lilu/releases)

`VirtualSMC.kext` - Emulates the SMC (Like FakeSMC if you've built hackintoshes in the past), get it [here](https://github.com/acidanthera/VirtualSMC/releases)

`SMCProcessor.kext` - Allows monitoring of CPU temp on Intel CPUs, this is included with VirtualSMC

`SMCSuperIO.kext` - Allows monitoring of fan speed (Intel Only), this is included with VirtualSMC

`USBInjectAll.kext` - Support for Intel USB controllers, get it [here](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455146&cid=FE4038DA929BFB23) (bitbucke repo [here](https://bitbucket.org/RehabMan/os-x-usb-inject-all/src/master/))

`IntelMausiEthernet.kext` - Support for Intel ethernet, get it [here](https://onedrive.live.com/?authkey=%21APjCyRpzoAKp4xs&id=FE4038DA929BFB23%21455134&cid=FE4038DA929BFB23) (github repo [here](https://github.com/Mieze/IntelMausiEthernet))

`AppleALC.kext` - Allows for Audio support, get it [here](https://github.com/acidanthera/AppleALC/releases)

`WhateverGreen.kext` - Used for graphics patching, get it [here](https://github.com/acidanthera/WhateverGreen/releases)

`XHCI-unsupported.kext` - Support for Intel USB controller, get it [here](https://github.com/RehabMan/OS-X-USB-Inject-All)

These should be dowloaded from the links above and placed in the `/OC/Kexts` folder

### SSDT/DSDT

`DSDT` - This was generated with 

`SSDT-EC` - This was generated with 

`SSDT-PLUG` - 

`SSDT-EC-USBX` - 

`SSDT-AWAC` - 

`SSDT-PMC` - 

These are in this repository and belong in the `/OC/ACPI` folder

## Config.plist

I have included my working config.plist, this is for my **specific** hardware configuration, so you should not use it as-is. However, it will make a good starting point for you.

Things that you will **need** to change

`DeviceProperties`


