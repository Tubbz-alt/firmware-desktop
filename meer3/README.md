# To update firmware:

1. Backup all data. There is a small possibility that updating firmware can cause data loss.

### Downloading and preparing new firmware
1. Updating firmware requires a flash drive at least 2 GB in size.
2. The firmware.bio file needs to be placed on a thumbdrive with MBR FAT32 formatting.
3. Feel free to skip ahead to the later sections if this is familiar ground.
4. To properly format a flash drive, follow the next instructions:

### Preparing Flash Drive
1. Plug in the flash drive.
2. Open the "Disks" program.
3. The left panel of the "Disks" application shows all of the drives connected to your machine. Select the flash drive.
4. Select the menu button in the top right corner. Select "Format Disk".
5. A pop-up will appear asking how the drive should be formatted. The defaults are desired so select "Format...".
6. Confirm the execution by selecting "Format".
7. Once this process is complete, the volume should be listed as "Free Space".
8. Select the "+" button to create a partition for this drive.
9. The default settings should be sufficient. A name for the partition can be added to help identify the use of the drive.
10. Select "Create". The drive should be labeled with the name(if any) as well as the size and the parition type, FAT.
11. Mount the drive by selecting the "Play" button.
12. When the drive is ready, download the `firmware.bio` file from here: [meer3 firmware](https://github.com/system76/firmware-desktop/blob/master/meer3/firmware.bio). Click `Download` to begin the download of the firmware.

13. The sha512sum checksum for this download is:
```e2cea03c1902af6f11eb0b14ea41daf98f85697f5b8d6627d2f5cccec8ac628e6e974421bc7049bd51b54bc27027fb1a1078c395cd48e8b33fb6fa72654e269e```.

    Confirm that the download has the same checksum by executing the following command in the firmware.bio directory:

    `sha512sum -b firmware.bio`

14. Copy over the firmware file to the flash drive.


### Writing new firmware
1. After saving and backing up all work, make sure the flash drive with the updated firmware is plugged into the computer.
2. Power off the machine.
3. Power back on the machine. As the machine is powering back up, hold down the 'F7' key.
4. After seeing the System76 logo, you should be brought to a Blue and grey screen with the title containing the words "Intel NUC Board". This should look somewhat similar to the following screenshot.

![BIOS Update page](https://raw.githubusercontent.com/system76/firmware-desktop/master/meer3/images/1.jpg)

**Note: These images are for reference since these are screens you normally do not come across. These are not exact screenshots. The names of your drives will named differently according to the make and model of your drive.**

5. If you only have one USB drive connected to your machine, the name of that drive will be listed in white. *White text is a selected option, blue text is not selected*
6. Go ahead and select "Enter" when your flash drive is selected in white. Use the arrow keys to go up and down to change selections.
7. Next, you will be presented with whatever folders and files are on that flashdrive.
8. Select the `firmware.bio` file and hit "Enter" on your keyboard.
9. A blue pop-up will appear. You will then be asked "Are you sure you wish to update the BIOS with "firmware.bio?". Hit "Enter" once again to confirm.
10. Your machine will now reboot, you will see the System76 logo once again.
11. The firmware update will now begin. A prompt may ask to confirm this choice once again, press the appropriate number if prompted.
12. Firmware updating may take up to 5 minutes. The following screenshot will look similar to what will appear on your screen.

![Firmware update](https://raw.githubusercontent.com/system76/firmware-desktop/master/meer3/images/2.jpg)


12. Keeping an eye on the update, when the update finishes, you will see the text that "Flash update has completed successfully". Promptly unplug the flashdrive as the machine will reboot shortly.
13. The machine should now reboot back into the operating system.

14. To confirm the update was successful, check in either the BIOS or using `dmidecode` in the terminal that the BIOS verison is: `BNKBL357.86A.0069.2018.0920.1250`. 

**Note:**
After the firmware update completes, if the system reboots with the flashdrive still plugged in, you may be brought to a yellow and black command line prompt titled: "EFI Shell version x". If this is the case, press the `ctrl`-`alt`-`del` keys all at once and your system will restart. Promptly remove the flashdrive and your system will reboot into your operating system.
