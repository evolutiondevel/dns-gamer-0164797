# Make DNS Gamer 0164797 as Macbook pro early 2013

# Notebook specs:
 - Processor : i7 3630qm 2.4 Ghz with turboboost up to 3.4 Ghz , 6mb L3 cache.
 - Chipset: HM76 Express
 - Memory : 4+4gb 1600mhz ddr3.
 - Graphics: HD 4000 integrated + nvidia GT 650m with 2GB dedicated DDR3 memory.
 - 3 SATA ports: 1xSata + 1x mSata + 1 replaced DVD Rom to sata Optibay.
 - PS2 keyboard + Panel buttons.
 - PS2 synaptic touchpad.
 - USB: 2xUsb2.0 + 2xUSB3.0 ports + USB Webcamera + USB Bluetooth AR3011 (on Atheros wifi chip).
 - Wifi: Atheros AR9485.
 - Ethernet :  Atheros AR8161. 
 - Audio:  ALC269 2 combo ports + Internal Microphone + Internal Speakers.
 - Card Reader: Rts5229 PCIe Card Reader
 - Battery : 4400 Mah 
 - Video Output: Internal LVDS 1366x766 pixels + VGA + HDMI

# What works:

 - Processor with Power managment  Config.plist + ssdt.aml in acpi/patched
 - Integrated Graphics HD4000 with qe/ci - Lilu + Whatevergreen
 - Keyboard + Touchpad  with VoodooPS2Controoler
 - USB ports - USBinject All + UIAC-ALL.SSDT in acpi/patched + dsdt patch
 - Webcamera -  out of the box with patched usb
 - Wifi  - AR9485 - IO80211Family.kext( installed to S/L/E in Catalina ) and HS80211Family.kext in Kexts/Other for Big Sur
 - Ethernet - AtherosE2200Ethernet.kext
 - Audio - AppleALC + config.plist (do not update to latest version)
 - Internal monitor and HDMI
 - Battery - ACPIbatteryManager + dsdt patch
 - Internal display backlight - WhateverGreen + SSDT-PNLF in acpi/patched
 - Bluetooth - only after loading firmware on Windows and reboot to OS X
 - Buttons on panel : Display off, Throttle CPU, Vol+, Vol -
 - Fn Buttons
 
 # What not works:
 
 - GT650m - optimus technology not supported in OS x (you can disable it for better power saving).
 - VGA port
 - HDMI audio - easy to patch , but i dont need this
 
 # Not tested
 
 - RTS CardReader 
 
 # Notes for OSX 10.16 - 11.0.1 Big Sur
 
 - For Big Sur need update Clover to v5126 or highter and fill Quirks in config.plist
 - For Big Sur im replaced FakeSMC to VirtualSMC to avoid apfs_module_start error 2436
 - For download and install need mask notebook to macbook 11 and highter in config.plist , becouse older models not have official support
 - Need replace AptioMemiryFix-3drv to OpenRuntime.efi
 - If you are using HWmonitor.app , need replace to HWmonitorSMC2.app 
 - ApplePS2smarttouchpad replaced with VoodooPs2Controoler, which support gestures and Settings via system trackpad options.
 
