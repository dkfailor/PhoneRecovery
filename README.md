# PhoneRecovery
Notes on my work with cell phone recovery and forensics.

# Android Phones

## LG Prepaid LML212VL Android phone
My cell phone died and fortunately I had an identical one which was previously
used by someone else until they purchased a high end phone.  I performed several
steps to transfer/mirror my phone over to the new phone including:
  1. reset the replacement phone to factory defaults
  2. import my Google accounts
  3. reinstall essential apps like Google Authenticator and Microsoft Authenticator and import the third part
     accounts for which these apps were used as MFA security.
  4. I changed the default settings to my liking (screen timeout, background theme, and preferred apps.
  5. I uninstalled or disabled unwanted apps after stopping them and deleting their data.
  6. I now have a good working phone that functions identically to the one that "died".

## Samsung Galaxy S23 forensics and virus eradication
I was given this phone to fix for a relative.  They could not use certain apps and they keep getting virus flags
in their notifications. This happened after they installed a free Security software suite (of which I was immediately
suspect).

## Here are some of the steps I took. In the cases where I either bypassed or removed security measures I won't document here 
how I did it for ethical reasons.
  1. I turned off my WiFi network before the person dropped off the phone at my house.  I did this because I was not sure if they
     ever accessed our network before (because I gave them the password when they were here).  I trust this person but many of our
     phones are set to automatically log in to the strongest WiFi network.
  2. The person gave me their pin and Google account information.  I did not need the pin because there are ways to bypass it,
     but it is much easier if you already have it.
  3. I discussed the problem with the phone owner to get more details on what was wrong.  I told them it could take a couple of
     days for me to fix it depending on how bad the malware infection is.  I explained that "worse case scenario" I would have to
     reset the phone to factory defaults and reinstall the necessary software.
  4. I bypassed the fingerprint lock on the phone.  Now that I have full access I turned off WiFi and BlueTooth and put the
     phone in "Airplane Mode".  This protects my network and prevents more malware from downloading from the cellular network.
  5. I researched the "Security Suite" that the person had installed on their phone right before the problem.  It is very
     suspicious so I restored the phone default settings and then totally uninstalled it from their device. (This software changed
     the home UI to its own so that was one of the items I changed back to default).
  6. I changed the screen timeout and lock screen timeout to never so that I would not have to keep entering the pin. I will change it          back to 5 minutes or less when I am done.
  7. I then allowed guest access only to their WiFi on my network.
  8. I made sure Google Play Protect was turned on and I had it scan the apps and it showed "no threats".  I then installed both AVG free       and Malwarebytes free version on the phone.  I updated the software and scanned separately using both programs.  All of the hundreds       of apps (many of them hidden system apps) scanned as "no threat". (After discussion with the owner, I didn't feel that there was any       real additional threat based on my experience so I didn't attach the phone to a different PC and use ClamAV and other software on my       Linux PC, but that certainly would be an option to isolate the phone completely while checking it.  Of course one has to be aware of       stealth malware and rootkits which may hide themselves).
  9. I removed the AVG free software but left Malwarebytes installed.  Sometimes anti malware programs can conflict with each other and
     I have previous good results with the free version of Malwarebytes on my phone.  (AVG is good as well but I personally find the free       version is more effective for PCs.
  10.I backed up the phone to the cloud with Google Backup (which is built in to the phone. I told it to "backup now").
  11.I added the app tray to the home screen since all the apps were hidden and I needed to make sure I could see which user apps
     were installed. I also looked at all the apps from the settings/apps menu on the device.  There you can see all apps including
     system apps. Then I took several screenshots of the user apps and other apps to export to my PC.
  11.I created a quick backup.ab file using ABD. In order to create a complete system backup I believe that one has to root the
     phone. I've rooted several phones before but since this one was not mine and the user is not savy to security and potential
     threats I did not want to root it. (This could also void your warranty). I believe there are other forensic methods that do
     not involve root (there has to be because a forensic copy is write-blocked and a bitwise exact copy but when you root a device
     you change settings and install other software).
  12. To create the quick backup you have to install developer options on the phone by tapping
     the build number several times under the software option in the settings.  Then enable "USB Debugging". When you connect the phone to
     your PC and run ADB commands (adb devices, adb shell, etc.) a prompt appears on the phone to see if you authorize the backup
     and if you trust the PC.  I used adb shell to peruse the files on the device and adb push/pull to copy the screenshots from the            sdcard/DCIM/Screenshots folder to an examination folder my PC so I have them as reference. It will also help me to discuss any
     other issues over the phone with the owner without having to be there in person.
  13.The next step will be to convert the ab file into a linux zipped file that is accesible by Autopsy or other Forensic software to
     see if there is any other evidence of malware.  FTK Imager may work better but I believe the only free version is a trial version.
  14.The owner and I had a discussion about not clicking on messages that state that your "phone has a virus" or your "facebook has a           virus", but instead to delete them. I also showed them how to scan their phone with the real antivirus software.




