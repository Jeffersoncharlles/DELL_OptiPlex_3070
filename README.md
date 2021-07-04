# OpenCore 0.70 EFI Config for the Dell Optiplex 3070mff

This is the 100% working OpenCore EFI for Dell 3070 MFF with Two Displays!

BigSur

## 4k display
```
If you are working with 1080p monitor, just stay away from this fix. Only do this if you really need 4k!

To make it work with 4K monitor you have to edit the BIOS by yourself. WARNING!!! DO IT ON YOUR OWN RISK. THIS METHOD IS FOR THE DELL OPTIPLEX 3060 MFF only (it might work with SFF or MT but check your BIOS before you do this). It might brick your machine.

1.Create a bootable USB with EFI Shell
    1-a. Format a USB 2.0 Stick as FAT32 with MBR named EFI
    1-b. Create /EFI/BOOT/
    1-c. copy BOOTX64.efi into that folder

2. Boot with it
    2-a.  on grub command type : setup_var 0x8DC to check the current value it should be 0x01
    2-b.  Change to 0x02 by typing : setup_var 0x8DC 0x2
    2-c.  Check the value again : setup_var 0x8DC make sure that it is 0x02
    2-d.  Reboot!
    
After successfully boot, edit the config.plist with clover configurator delete the framebuffer-stolenmem, framebuffer-fbmem and the enable-hdmi20. Reboot again, and set your 4k display resolution in the display preference.

You can have 4K @ 30Hz with the HDMI port and 4K @ 60Hz with the Display Port.
```