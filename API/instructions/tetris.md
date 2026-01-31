# Prerequisites:
- PC

# Clean flash:
- Reboot to bootloader
- Flash boot, init_boot, vendor_boot, dtbo and recovery images and wipe super
   -  `fastboot flash boot boot.img`
   -  `fastboot flash init_boot init_boot.img`
   -  `fastboot flash vendor_boot vendor_boot.img`
   -  `fastboot flash dtbo dtbo.img`
   -  `fastboot flash recovery recovery.img`
   -  `fastboot wipe-super super_empty.img`
- Reboot to recovery
- Sideload ROM zip
   -  `adb sideload PixelOS*.zip`
- Format data after sideload
- Reboot and voila!

# Updating to a newer build (dirty flash):
- Sideload ROM zip via recovery or update via OTA updater
- Reboot and voila!

# If sideloading rom gives error 7:
- Reboot to recovery
- Enter fastbootd
- fastboot wipe-super super_empty.img
- Enter recovery
- Sideload the rom zip
- Format data
- Reboot

# If after sideloading rom, device boots to bootloader:
- Do clean flash steps again
- When it asks for Yes/No prompt for installing additional packages, select Yes
- After device reboots recovery, sideload again.
- This time when it asks for Yes/No prompt for installing additional packages, select No
- Format and Reboot
