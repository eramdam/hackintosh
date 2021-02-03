Quick documentation of what I had to do to successfully update from OpenCore 0.6.5 to OpenCore 0.6.6

By following this link https://dortania.github.io/OpenCore-Post-Install/multiboot/bootstrap.html#updating-bootstrap-in-0-6-6.

NOTE: This is specifically tied to my own configuration and I'm mainly documenting this as to not forget about it in the future. I would advise you follow the instructions in the link above before anything else.

1. IMPORTANT: Prepare a USB key with `OpenShell.efi` copied to `/EFI/BOOT/BOOTx64.efi`
2. Set `Misc -> Security -> AllowNvramReset` to `True` and `Misc -> Boot -> BootProtect` to `None`
3. Reset NVRAM
4. Boot normally
5. Update OpenCore files
   1. `OpenCore-0.6.6-RELEASE/X64/EFI/BOOT/BOOTx64.efi` -> `EFI/EFI/BOOT/BOOTx64.efi`
   2. `OpenCore-0.6.6-RELEASE/X64/EFI/BOOT/BOOTx64.efi` -> `EFI/EFI/OC/Bootstrap/Bootstrap.efi`
   3. `OpenCore-0.6.6-RELEASE/X64/EFI/OC/Drivers/OpenCanopy.efi` -> `EFI/EFI/OC/Drivers/OpenCanopy.efi`
   4. `OpenCore-0.6.6-RELEASE/X64/EFI/OC/Drivers/OpenRuntime.efi` -> `EFI/EFI/OC/Drivers/OpenRuntime.efi`
   5. `OpenCore-0.6.6-RELEASE/X64/EFI/OC/OpenCore.efi` -> `EFI/EFI/OC/OpenCore.efi`
6. Set `Misc -> Boot -> LauncherOption` to `Full`
7. Reboot into the OpenShell USB from the first step
8. End up in OpenShell
9. Adjust resolution by typing `mode` and then `mode col row` where `col` and `row` correspond to one of the modes listed
10. Cycle through volumes by typing `FS0:`,`FS1:`, `FS2:`.. until we find macOS' EFI partition (in my situation it's `FS6:`)
11. Type `efi\boot\BOOTx64.efi` to launch OpenCore
12. Boot macOS normally
13. Reboot
14. The BIOS should have an `OpenCore` entry corresponding to the boot volume
15. Optional: you should be able to safely remove `EFI/BOOT/BOOTx64.efi` from the boot volume
