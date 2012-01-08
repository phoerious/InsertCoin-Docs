# Troubleshooting
This page will help you to solve common problems with InsertCoin.

## Market problems

* **Problem:** App download from Market causes “Error downloading <application name>.
  There isinsufficient space on the device.”
  
  **Fix:** Boot into recovery, scroll down to “wipe cache partition” then scroll down to
  “advanced”, then run it, then scroll down to “wipe dalvik cache”, run it, then go back and “reboot system” 
  
* **Problem:** “Insufficient storage space” error message when trying to download and install app.
  
  **Fix:** Go to settings/applications/manage applications then select the all Tab,
  scroll down to Download manager, open it, and clear the data. There should only
  be a few hundred KB stored and it will not affect anything else. If that does
  not work on its own try Question 1’s fix.
  
* **Problem:** You get a “Authourizing Purchase” hang.
  
  **Fix:** Isn’t one as such, this is a problem on the Google backend and nothing we
  can do about it. If you try and download more than 5 or 6 apps all at once the market can get
  all confused and just “hangs” on you, try downloading fewer apps in one go.


## Problems with WIFI

* **Problem:** I cant enable wifi when in airplane mode
  
  **Fix:** No official fix, as that is what the airplane mode was designed for, to turn
  off all call functions, data services, Bluetooth, and Wi-Fi.
  You can however get apps like “Airplane Edit” from
  [the Market](https://market.android.com/details?id=net.cenkalti.airplane&feature=search_result).
  That may give you what you want.


## SD Card Problem:

* **Problem:** I just bought a new sd card and my phone does not see it, I formatted on
  Windows and works fine on my pc. Help!
  
  **Fix:** Make sure the sd card you bought is compatible with your phone. Check
  that it is formatted as FAT32, Windows has a habit of formatting in NTFS and
  that will be why you pc will read/write to it but your phone won’t. The phone
  will only work with FAT32 sd cards.
  As a side note, always try and purchase the fastest sd card you can afford,
  anything over a Class 6 should be fine, higher the better.


## Other problems

* **Problem:** Contact pictures don't show up in the messages app.
  
  **Fix:** This is a common problem and can be caused by many things. Most often it's
  Titanium backup messing things up. This issue can be solved by changing the permissions
  of the contacts folder.
  Install a [terminal emulator](https://market.android.com/details?id=jackpal.androidterm),
  open it and type in the command
  **su -c "chmod 744 /data/data/com.android.providers.contacts/files/\*"** (write it *exactly*
  as is, case and punctuation matter!). When you hit enter, the Superuser app asks
  you whether you want to grant root rights. Confirm, close the terminal and restart the messages
  app. You should now see contact pictures again.