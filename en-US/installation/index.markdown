# Installation instructions

Before you get started there are a few things that need to be in place. These are
*S-OFF*, *CWM recovery*, *Fast boot* turned off and the ROM that the MD5 sum matches. 

What are these? I'll tell you, 

S-OFF is where the security check of the Bootloader is disabled so that custom
firmware can be loaded. 

CWM recovery is a custom recovery system know as *ClockworkMod recovery* which
enables you to backup and restore your current firmware, install zip files,
partition the SD Card, fix permissions, wipe battery stats, mount folders and USB storage.

Fast boot is an option in the system setting which puts the handset into a
sleep state rather than a full shutdown when turned off. You will find this here:
*menu/settings/power*. Make sure this is unchecked as you can't getting into the
bootloader without taking out the battery otherwise. 

ROM and MD5 sum, The ROM is the firmware that will be running on your handset,
in this case it's InsertCoin and the MD5 sum is a compact digital fingerprint of
a file. It's good practice to check these match as if they don't the file could
be corrupt and/or modified with malicious software. To check these match is
easy all you need to do is follows. 

**Mac OS X:** Open terminal and type *openssl md5 /path-to-file/file.zip* 
(e.g. *openssl md5 /Users/ME/Downloads/InsertCoin_Sensation_Android_2.3.5_Stable_2_4.0.zip*)

**Linux:** Open terminal and type *md5sum /path-to-file/file.zip*
(e.g. *md5sum /home/ME/Downloads/InsertCoin_Sensation_Android_2.3.5_Stable_2_4.0.zip*)

**Windows:** Download *md5sum.exe* and copy the file to *C:\Windows*, Open a DOS
prompt by clicking “Run” in the start menu, then type cmd, In the DOS prompt
window, use the cd command to navigate to the subdirectory where you stored
the downloaded file. For example, assume that your downloaded file is in
*C:\Users\ME\My Documents\Downloads\*, then the command would be:
*cd "C:\Users\ME\My Documents\Downloads"*. Now type *md5sum filename.zip* and
the MD5 sum will be displayed.

## What is a bootloader?
Every Android phone has a bootloader that loads the operating system on the
hardware's memory when the system is booted and also starts the operating system.
Every manufacturer has their own version of bootloader specific for the hardware
present in it’s environment.

By default, most bootloaders are locked and secured by cryptographic signatures.
Before you can install any custom software you need to unlock it. Read the following
part to find out how to do this.

## How to unlock my phone?
There are 2 ways of unlocking the bootloader. First is the official HTC way but is
only available on selected devices due to operator restrictions (this option
only allows you to install custom firmware not recoveries or kernels) and then
there is the revolutionary way (this gives you full control of your hardware for
maximum customisation). This is the only way we are interested in as unlocking
your bootloader will void your warranty and doing it the revolutionary way can
be reverted back to stock if a warranty repair is required. Whilst the HTC way
is done through them and they could hold your serial number to track handsets
that have been unlocked using that method. For more information on the
revolutionary way head on over to [http://revolutionary.io/](http://revolutionary.io/).

**NOTE: we're not responsible for any harm you do to your phone by unlocking the
bootloader. Doing so might void you warranty or brick your device. We can't be
held to account for this!**

## Installation
Once you've unlocked your phone we can start the installation. First you need to
download the latest ROM version, which can be found on
[http://insertcoin-roms.org/](http://insertcoin-roms.org/).
As with anything it is always best to have the latest version, updates are often released
to fix bugs, add optimizations etc.

Download the zip, check its MD5 sum as described above and follow the instructions
below thoroughly.

**Again: we're not responsible for any damage. Do all this at your own risk!**

**Also be aware that wiping your phone in order to install InsertCoin ROM will
erase ALL your data on the device. Please make a backup before proceeding!**

### Before you start
01. Get a big SD card
02. Partition the card order: [  Xgb FAT32    ][1gb ext3/4] (step 5 of http://forum.xda-developers.com/showthread.php?t=1016084)
01. Choose you IC type: app2sd or CM7.
02. If CM7: need to change the hboot. Use "Bravo CM7 r2"'s hboot at: http://alpharev.nl/

#### Alpharev
01. Use this method: You can also download the corresponding PB99IMG zipfile, put it on your sdcard, and rename it to PB99IMG.zip. Then start the phone in HBOOT mode (VolDown+POWER) to flash the HBOOT without a PC. It is however still necessary to either restore your nandroid, or reflash your ROM after doing this. The partition LAYOUT has changed, the actual data still needs to be 'moved'

### How do I flash InsertCoin ROM?
 1. Make sure you have the latest FULL ROM and place it on your SD card. 
 2. Boot into recovery by powering off your device and turning it back on
    whilst holding down the power + volume down keys.
 3. Scroll down (volume keys) to “recovery” then press the power key.
 4. Scroll down to “wipe data/factory” reset and press the power key.
    (all other cache's will be wiped automatically).
 6. Scroll to ”install zip from your sdcard” and press the power key again.
 7. Scroll to “choose zip from sdcard” and press the power key.
 8. Scroll to the InsertCoin ROM file (i.e InsertCoin_Sensation_Android_x.x.x_Stable_x.x.x.zip)
    then press the power key once again.
 9. Wait for the install to finish.
 10. Push the back button, select “reboot system now” and press the power key.

Congratulations! You have sucessfully installed InsertCoin ROM
 
### How do I upgrade from previous versions?
If you have flashed any custom kernel before you need to reflash it after upgrading InsertCoin.
Otherwise your device might not work as expected. Download the zip file for your kernel as
well, place it next to the InsertCoin file on your SD card and repeat the steps
below for it (if not stated otherwise in your kernel's docs).

 1. Place the update on the SD card. 
 2. Boot into recovery by powering off your device and turning it back on
    whilst holding down the power + volume down keys.
 3. Scroll down (volume keys) to “recovery” then press the power key.
 4. scroll to “install zip from your sdcard” and press the power key.
 5. Scroll to “choose zip from sdcard” and press the power key.
 8. Scroll to the InsertCoin update (i.e InsertCoin_Sensation_Android_x.x.x_Stable_x.x.x.zip)
    then press the power key.
 9. Wait for the install to finish.
 10. Push the back button, select “reboot system now” and press the power key.