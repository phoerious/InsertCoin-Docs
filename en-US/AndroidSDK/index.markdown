# Android SDK Installation

The Android SDK installation will provide you with ADB and Fastboot tools as well
as many other tools. ADB is the command line interface that allows you to access
your phone from a PC. It is basically like running terminal emulator from your computer.
It allows you to access the file system (push and pull files) and debug problems.
Fastboot allows you flash radios, recovery, etc from the bootloader.
This tutorial will get you started.

## Windows Installation

1. For the HTC drivers, look here [http://forum.xda-developers.com/showthread.php?t=1161769](http://forum.xda-developers.com/showthread.php?t=1161769)

2. Download and install the latest Java JDK found here
[http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).
Be sure to install the JDK and not JRE.

3. Download and install Android SDK from
[http://developer.android.com/sdk/index.html](http://developer.android.com/sdk/index.html).
For this tutorial we will be using the Windows installer (second option in the Windows section) .

4. At the end of the Android SDK install, you are given the option to
“Start SDK Manager (to download system images, etc.), go ahead and allow SDK to
start. You are presented with a list of packages that will be installed.
The list is rather long and contains packages for developing on all versions of
Android going back to Android 1.5. If you would like to install all of these
packages, go ahead, but they are not necessary for ADB and FastBoot.
If you only plan on using ADB and Fastboot, click “Cancel”. Keep in mind,
you can always add packages if you decide you would like to develop.

5. Once you hit cancel, you are now in the Android SDK and AVD Manager.
In the left pane select “Available Packages” and in the right pane expand
“Android Repository” by clicking the “>” next to it. The only package we need
for ADB is “Android SDK Platform-tools”. Put a check in the box for that package
and select “Install Selected” and in the next window click “Install”.
You are prompted to restart ADB, go ahead and click “Yes”. Now, you can close all windows.

6. One last thing we need to do is to add ADB to our PATH so that ADB will run
from any command prompt. To do this Go to Start-->Control Panel-->System and
select Advanced System Settings in Windows 7 or Advanced Tab in XP. Click
Environment variables. Under the “System Variables” section, find PATH and
double click. In the Variable Value box, at the end put
**C:\Program Files\Android\android-sdk-windows\platform-tools** separating
the previous entry with a semi colon. For x64 you would use
**C:\Program Files(x86)\Android\android-sdk-windows\platform-tools**.

7. To test if we have been successful, plug your phone into your PC,
allow the drivers to see your phone, and then open a command prompt.
At the command prompt type **adb devices** . You should see ADB
return with your device number. 

## Fedora Java JDK Installation

1. Download Java JDK from [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html).
Be sure to download the JDK and not JRE.
Select jdk-<version>-linux-<platform>.rpm.bin to download

2. Open a terminal and navigate to the folder you downloaded JDK using cd.
For example, I use a “Download” folder on my desktop for easy cleanup, so
I would type **cd /home/SymLink/Desktop/Download**
Type **sudo chmod a+x jdk-<version>-linux-<platform>.rpm.bin** (note : I
am assuming you have added your user name to the sudoers file. If not, an easy
tutorial a be found here [http://www.mjmwired.net/resources/mjm-fedora-fc6.html#sudo](http://www.mjmwired.net/resources/mjm-fedora-fc6.html#sudo))

3. Run **sudo ./jdk-<version>-linux-<platform>.rpm.bin**

4. Add the JDK to the list of Java alternatives by running
**/usr/sbin/alternatives --install /usr/bin/java java /usr/java/latest/bin/java 2**

5. Make your new JDK the default by running **update-alternatives --config java**
and selecting the option that contains /usr/java/latest/bin/java

## Ubuntu Java JDK Installation

1. At the time of this writing, the Sun Java JDK is not available in the Ubuntu
Maverick (10.10)repositories, so we need to make the Lucid partner repository
active. Note : If you are running Lucid (10.04) this step is not necessary.
To activate the Lucid partner repository, open a terminal and type

    sudo add-apt-repository “deb http://archive.canonical.com/lucid partner”
    sudo apt-get update

2. Install Java JDK by running **sudo apt-get install sun-java6-jdk**

## Android SDK Install Ubuntu/Fedora

1. Install necessary libraries (from terminal)
Ubuntu – **sudo apt-get install ia32-libs**
Fedora x64 – **yum install glibc.i686 glibc-devel.i686 libstdc++.i686 zlib-devel.i686 ncurses-devel.i686 libX11-devel.i686 libXrender.i686 libXrandr.i686**
Fedora x86 – **yum install glibc glibc-devel libstdc++ zlib-devel ncurses-devel libX11-devel libXrender libXrandr**

2. Download and install Android SDK from
[http://developer.android.com/sdk/index.html](http://developer.android.com/sdk/index.html)

3. Extract to location you would like to use. I chose my home folder “/home/SymLink”
and for simplicity I renamed “android-sdk-linux-x86” to “android”

4. Add Android SDK to your environment variables by opening a terminal and running
**gedit ~/.bashrc** and at the end of the file add
**export PATH=$PATH:<your android folder>/tools** (mine looked like export
PATH=$PATH:/home/SymLink/android/tools)
**export PATH=$PATH:<your android folder>/platform-tools** (mine looked like
export PATH=$PATH:/home/SymLink/android/platform-tools)

5. Refresh your Environment Variables by running **source ~/.bashrc**

6. Run the Android SDK Manager by simply typing **android**

7. You are now in the Android SDK and AVD Manager. In the left pane select
“Available Packages” and in the right pane expand “Android Repository” by
clicking the “+” next to it. The only package we need for ADB is “Android
SDK Platform-tools”. Put a check in the box for that package and select
“Install Selected” and in the next window click “Install”. You are prompted to
restart ADB, go ahead and click “Yes”.

8. Fastboot is not included with Android SDK for Linux, so we must add it
manually. The binary can be found at [http://developer.htc.com/adp.html](http://developer.htc.com/adp.html)
about one-quarter of the way down the page. Download it and unzip it to
<your android folder>/tools

9. To allow adb and fastboot to access your phone, we need to set udev rules for
your device. From terminal type
**sudo gedit /etc/udev/rules.d/51-android.rules**
Add **SUBSYSTEM=="usb", SYSFS{idVendor}=="0bb4", MODE="0666"** to the file and save

10. Refresh udev rules by running
Ubuntu – **sudo reload udev**
Fedora – **sudo udevadm control –reload-rules**

11. To test if we have been successful, plug your phone into your PC, allow the
drivers to see your phone, and then open a command prompt. At the command prompt
type adb devices . You should see ADB return with your device number.

One last thing to do. If you plan on accessing the adb shell as root, we need to
allow access on your phone. Plug your phone in and in command prompt or terminal
type adb shell. Then, with your phone screen on, in command prompt or terminal
type su. A pop up will appear on your phone to for you to allow superuser permissions.
