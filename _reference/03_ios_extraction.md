---
layout: page
title: How Do I Get Text Messages Off an iPhone?
headline: How to get the phone backed up
permalink: /ios/
---

On a per-gigabyte basis, cell phones hold more interesting evidence than a corporate email account, a whole warehouse of paper, or a full image of a person’s computer. How do you get that evidence off the phone? 

One option is the long screenshot, but that's a pain to work with and doesn't look terribly professional. Another option would be spending upwards of $10,000 on a Cellebrite UFED or finding someone that's got one but you don't have to. Almost any tool that extracts and parses data from an iPhone will just as easily take an iTunes backup as the input. Taking an iTunes backup is easy

iPhones are generally quite secure but it’s fairly easy to extract data from them if you can get past the screen lock code. If you’re working with your client, they will just need to give you the passcode they use to unlock their phone and their iOS backup password (if they’ve set one before).

What you do with this iOS backup will vary depending on what resources you’ve got available. Just about anyone working in digital forensics will have a tool like Lantern from Katana Forensics or Internet Evidence Finder from JAD Software and they’ll be able to parse the backup and give you some reports. Both of these tools make some pretty easy to work with reports and can also spit the data out as a CSV file that can be reviewed in anything from Excel to Relativity.

To extract the data from an iOS device, you’re going to take a backup using iTunes.

### Things you will need:
* The iPhone or iPad you’re backing up
* A 30-pin or Lightning cable
* The passcode to unlock the phone (or your fingerprint if you’re backing up your own phone)
* If you have taken an encrypted backup of the phone in the past, you must have the password you used to create the encrypted backup[^1]
* A Mac or a Windows PC with the newest version of iTunes installed

### Backing Up the Phone
1. Open iTunes on the computer
2. Plug the iOS device into an open USB port
3. Unlock the phone
4. You will see a prompt asking you whether you want to trust the computer you’re plugged into. Choose “trust”
5. You will also see a prompt on the computer asking whether you want the computer to access the information on the phone. Choose “Continue”
6. If prompted to download new software for the device, click “Cancel”
7. In iTunes, look for an icon in the top left that looks like the device you are backing up and click on it
8. In the “Backups” section, make sure that “Encrypt iPhone backup” is not checked, then click the “Back Up Now” button. If you cannot unselect the encryption option, go ahead but choose a password for the backup that you will remember as it will be required for any future backups of this phone.[^2]
9. If a previous encrypted backup had been taken, you will need to enter the password used to create that backup at this time.
10. If you’re on Windows, Once the backup has completed, click the start button and then click in the search bar. In the search bar type %appdata% and press return. Double click on the folder called “Apple Computer” then the folder called “MobileSync” then “Backup”. If you’re on a Mac, open the finder, then click “Go” then “Go to Folder” and paste in “~/Library/Application Support/MobileSync/Backup/”.

Each folder you see represents an iOS device backup. Each backup is named with what seems like a random sequence of letters and numbers. Right click on the folder that has a modification date of the day you took the iOS backup and compress or zip it. This zip file can be sent for further analysis and review.

[^1]: This piece of the process is important. Modern iPhones create their backups on the device, then spit the backup out to the computer. This means that the password that you set to create a local backup will stay with the device forever. As of iOS 11.0 and above, you can now strip out the password if you've forgotten it by going to Settings –> General –> Reset and tapping "Reset All Settings." This will remove any linked Apple Pay accounts and will reset other customizations but will allow you to back the phone up again. 

[^2]: It may seem counter-intuitive that we want an unencrypted backup when we are so concerned with protecting sensitive client information. We want an unencrypted backup created by iTunes becasue that format is going to be easier for tools to parse the data. Not all backup parsers can handle an encrypted backup. When the process is complete consider encrypting the zip file containing the clear text backup. That way your client’s data is safe and you’ve got a versitle set of data to work with.
