# Dell-Inspiron-7590-Hackintosh-Opencore
OpenCore EFI for Dell Inspiron 759x.        
✅ Current macOS version:  `11.3 Beta 5` `(20E5217a)`  / Current EFI version: `21.3.18`      
✅ Support macOS `11.0.*`, `11.1.*`, `11.2.*` & `11.3 Beta (>=4)`         
❌ This branch will no longer supports `macOS 10.15`, if you need install macOS `10.15`, please use branch `Catalina_Backup`.        
❌ DO NOT install `macOS 11.3 Beta 1~3`. It can't boot normally.      
In theory, this EFI supports for all models of Dell Inspiron 7590 / 7591 Series.
![](https://img03.sogoucdn.com/app/a/100540022/2021031801114349486906.jpg)

# Introduction
* The EFI is based on @[tctien342](https://github.com/tctien342/Dell-Inspiron-7591-Hackintosh)'s repo. Thanks!
* `config.plist` is designed for 4K model and `config-1080P.plist` for 1080P model. For users of 1080P model, please rename `config-1080P.plist` to `config.plist` first.
* [⚠️ **IMPORTANT**] **Default strategy for Bluetooth & WIFI**: <br> The default settings are designed for Broadcom DW1820A (`BCM94356ZEPA50DX_2` is highly recommended). If you need to make Intel bluetooth work, please enable those relative kexts in config.plist manually.
* Version number is same as the date of each commit. (e.g. `20.3.6` is the version which updated on 2020/3/6)

# Fix the Combojack Support
Execute `install.sh` in folder `ComboJack` to install an combojack protecting process, so that your computer can make response when you plug in an audio device automatically.
Thanks to @[hackintosh-stuff](https://github.com/hackintosh-stuff/ComboJack) and @[tctien342](https://github.com/tctien342).

# Color Profiles for 4K Screen
It will load the default sRGB color profile. For 4K model, it is an incorrect profile but you can apply other color profiles for your screen to improve the color experience.
> Download: ([Sharp SHP14C7](http://oss.pm-z.tech/temp_files/SHP14C7_ICC.zip)) ([AUO AUO41EB](http://oss.pm-z.tech/temp_files/AUO41EB_ICC.zip))<br>Each package includes all 6 profiles which are extracted from Dell PremierColor. <br>Copy .icm files to `~/Library/ColorSync/Profiles` and apply the color profile you need in `System Preferences→Displays→Color`.<br>Using `Adobe RGB` or `DCI-P3` profile is recommended, due to the 4K screen covers 100% Adobe RGB and 90% DCI-P3.

# Known Problems
- [ ] It won't response automatically after HDMI cable plug in or plug out. You possibly need to refresh the display status manually.
    > Temporary Solution: After plugging in or plugging out HDMI cable, hold  `Option` button (`Windows` Button on Hackintosh) on `System Preferences→Displays`, and click button `Detect Displays` to re-detect the monitors.
- [ ] Monitor maybe blink while HDMI plugged in with audio output on 1080P model.
    > You can solve it by turn it to sleep and wake up afterwhile.<br>For 1080P model, HDMI audio output is controlled by `alc-device-id` and `alc-vendor-id` in `DeviceProperties`->`PciRoot(0x0)/Pci(0x1f,0x3)`. If these 2 arguments are not assigned, HDMI audio won't be outputted.<br>According to some feedbacks about this problem, these arguments will be defaultly disabled after `20.7.16` and you can enable it by yourself if you are in need.
- [ ] Wireless Card & ThunderBolt have not been tested yet and can't confirm whether they are available.
- [ ] Internal Microphone doesn't work.
- [ ] DW1820A can not receive files from other devices.
    
# What's New
## 2020/2/16
* Generalized this repo for all models of Inspiron 7590 / 7591 Series.
* Added Color Profiles for 4K screen.
## 2020/2/18
Replaced `SMBIOS` from `MacbookPro15,1` by `15,3` and cleaned up SSDTs to reduce the battery consumption. Thanks to @tctien342.
## 2020/2/24
Added `NullEthernet.kext` so that you can test some original macOS application (e.g. `App Store` & `FaceTime`) without a built-in network card.
## 2020/3/6
* Now, HDMI Port can output both of video & audio. 
* Updated `VoodooI2C` and added argument `-btnforceclick` to treat press the trackpad as `Force Click`. Thanks to @tctien342.
* Updated `AppleALC` and added argument `alc-delay=500` to ensure that sound card can be driven at proper time. Thanks to @lvs1974.
## 2020/3/7
Added `IntelBluetoothFirmware` & `IntelBluetoothInjector` again.
> The solution to slow booting due to loading these kexts:<br>Roll back the Intel Bluetooth driver to initial version in `Devices Manager` on Windows. It will roll back the firmware of bluetooth too. New firmware maybe imcompatible with macOS.
## 2020/3/8
* Replaced `VoodooTSCSync` with `CPUTSCSync` to fix kernel panic after wake up from sleep.
* Fixed recognization of HDMI plug-out.
* Modified stolen memory of UHD630 to 3072MB.
## 2020/3/9
Fixed graphics glitch on external screen when using HDMI connection on 1080P model. (Thanks to @Arien for testing)
## 2020/3/25
The macOS has been upgraded to `10.15.4`.
## 2020/4/12
* Upgraded `Opencore` to `0.5.8 (20200410)`.
* Upgraded `WhateverGreen` to `1.3.8`, in order to fix black screen after sleep possibly occur on certain models. (Thanks to @kihsu for testing)
## 2020/4/13
Upgraded `Lilu` to `1.4.3`, which is compatible with `WhateverGreen` (`1.3.8`). (Thanks to @XHL669 & @ChasonJiang for testing)
## 2020/4/17
The macOS has been upgraded to `10.15.5 Beta 2 (19F62f)`.
## 2020/5/3
* Disabled `SSDT-PLUG-_SB.PR00.aml` to make CPU have a better performance (PL1 = 45W / PL2 = 90W)
* ~~Updated `WhateverGreen` to `1.3.9`, added boot argument `igfxfw=2` to use Apple GuC Firmware.~~
    > This version of WhateverGreen will lead to a kernel panic after HDMI plugging in. It has been rolled back to `1.3.8`.
## 2020/5/6
Temporarily rolled back `WhateverGreen` to `1.3.8` to fix the kernel panic after HDMI plugging in.
> It has been fixed on version `20.5.28`.
## 2020/5/28
* The macOS has been upgraded to `10.15.5 GM (19F96)`.
* Updated `WhateverGreen` to `1.4.0`, added boot argument `igfxfw=2` to use Apple GuC Firmware.
## 2020/5/30
Made it compatible with DW1820A and stopped the support for Intel bluetooth.
## 2020/6/3
The macOS has been upgraded to `10.15.6 Beta (19G36e)`.
## 2020/7/16
* Disabled HDMI audio output for 1080P model's default setting.
* Added `DellSMCSensors` to control speed of fans.
## 2021/3/18
* Abandoned support for macOS 10.15
* Updated some kexts
* Updated `Opencore` to `0.6.8 (2021-03-05)`
# Tested Hardware
## Can be driven
**Dell Inspiron 7590** with Sharp SHP14C7 4K Display
* CPU: Intel Core i7-9750H @ 2.60 Ghz (Boost to 4.50 Ghz)
* IGPU: Intel Graphics UHD 630
* RAM: Hynix DDR4 2666Mhz / 16 GB * 2 = 32 GB RAM
* Display: Sharp SHP14C7 @ 15.6' / 4K
* SSD: WD PC SN730 NVMe WDC 512GB SSD
* Audio: Realtek ALC295 (ALC3254) (Internal Mic couldn't be driven) (Layout-ID = 77, if you choose 28 may lead to high CPU utilization by kernel_task）
* Micro SD Card Reader: Goodix fingerpint reader (Couldn't be recognized on system report, but could work properly)
* WLAN + Bluetooth: Broadcom DW1820A (`BCM94356ZEPA50DX_2`)

## Can not be driven
* Nvidia Geforce GTX 1650
* Goodix fingerpint reader

