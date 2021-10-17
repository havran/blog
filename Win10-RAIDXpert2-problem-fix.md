<small>2021 October 17</small>

---

# Windows 10 and problem with AMD RAIDXpert2 initialization

I have my desktop computer few years already. Configuration is pretty normal:

- ASRock Fatal1ty AB350 Gaming K4
- AMD Ryzen 7 1700 (yes, first one)
- Gainward GTX 1060 6Gb graphic card
- Samsung SSD 850 (512Gb), as system drive
- 2x Seagate 2Gb hard drives in RAID 1 configuration (on AMD software RAID)
- 2x G-Skill DDR4-2400 8Gb RAM

It's happens few time to me. I update bios on my motherboard... Or I'm trying update 
Windows 10...

My **RAID** disappears.

When this happens I look at **BIOS** and realize **BIOS** update or something else change my 
disk **_SATA Controller(s)_** settings from **RAID** to **AHCI**.   

When Windows 10 boots to this configuration, it's effectively forget how to 
initialize **RAID** drivers. When I go to **BIOS** again and set **_SATA Controller(s)_** 
back to **RAID**, I always get **BSOD** (_Blue screen of death_).


I try many attempts to fix that. **RAIDXpert2** software update, install latest version 
Windows 10,  over existing installation. Nothing helps...

## Solution

After few attempts I found simple solution with few steps:

- open **_Run_** window by keys combination **WIN + R**
- run **_msconfig.exe_** to open **_System configuration_** app
- go to **_Boot_** tab
- set windows boot options to **_Safe boot_**
- hit **Apply** and then **OK**, to close **_System configuration_** app
- reboot your system and go to your **_BIOS_** settings
- find **_SATA Controller(s)_** option and set it to **_RAID_**
- save changes
- boot to windows - should boot without problems to safe mode
- again open Run windows by keys combination WIN + R
- run **_msconfig.exe_** to open **_System configuration_** app
- go to **_Boot_** tab
- disable windows boot options **_Safe boot_**
- hit **Apply** and then **OK**, to close **_System configuration_** app
- reboot windows

Windows should boot normally now and your **RAID** should be back!



