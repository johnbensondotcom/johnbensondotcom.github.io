---
layout: single
title: Dealing With and Avoiding Drive Failure
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
It’s a scenario that can happen to anyone, at any time and without warning. One moment you’re working away, enjoying a nice cup of coffee and the next your Mac hangs.


As you try to figure out what’s going on, you notice that 
nothing is working. Placing some faith in the traditional OS X voodoo, you reset the PRAM (no help) and pop in the installation disc to repair permissions. Red text everywhere. Maybe repair will work! Nope.


Frantically you try to figure out what data is stored offsite while plugging in your Time Machine drive to another box.


Ah ha! I have a Disk Warrior DMG, maybe this will solve all my problems! Nope…Disc Warrior only serves to give you the bad news. The internal drive is beyond recovery and it’s time to replace it.


Successful recovery from one of the worst case scenarios requires a little bit of preparation and foresight on your part. It’s all about multiple redundant backups.


##Firewire to the Rescue



Believe it or not, I’m writing this on the Mac which bonked on me a little over 24 hours ago, and I’ve yet to crack open the case to replace the internal drive, which I’ll get around to eventually. How’s this possible? OS X can be installed on an external drive. From what I’ve read, this can be done with drives connected through USB 2.0 if you have an Intel based Mac, but I’m using the more traditional FireWire connection. I’m using a 
[SATA dock](http://www.google.com/products/catalog?client=safari&rls=en&q=vantec+nexstar&oe=UTF-8&um=1&ie=UTF-8&cid=14170732738834434539&ei=lHM8TeSMMc_1gAeT7_WHCQ&sa=X&oi=product_catalog_result&ct=image&resnum=5&ved=0CDsQ8gIwBA#) made by Vantec that supports USB, ESATA and FireWire 400 connections that I found at Microcenter when I was buying my new backup drives.


Installing OS X on an external drive is surprisingly simple. Even with a bonked internal drive, you can still boot to the Snow Leopard installer disc and simply run the installer on your external drive after formatting it. It took the installer about 30 minutes to run…not too bad.


Booting to the external drive is as simple as holding down the Option key when you start the Mac. At this time, the EFI firmware doesn’t even recognize my internal drive.


##Building Your Image



Recovering from a recent Time Machine backup is an option, but the problem with that is that there may be no way to tell when things started getting wonky on your system. Restoring broken files really won’t help things out so I’m taking this opportunity to build a new base image for OS X at this point. On top of that, almost everyone I know did a “dirty” install of Snow Leopard which worked like a charm. Starting from scratch can be a nice thing depending on how old your system is though. I guess that’s the former Windows user in me.


After running through the OS registration, check your user and computer names to make sure they match your preferences. Changing these after you install certain software like 
[Textmate](http://macromates.com/) can cause some problems. Start setting your system preferences back to what you had them before and kick off Software Update. OS X will download the combo update, which will be quite large.


My image is going to be pretty sparse, containing only the stuff that I use all the time.


The last thing I’ll do is move over my data, and I’ll probably do it only a little at a time. This is a good opportunity to clean up that documents folder which can become a mess over time.


##Installing the Drive



If I end up having Microcenter or the Mac repair place down the street pull my old drive, I’ll probably have them install the drive I’m building out now. If you take your Mac to Apple to be worked on, they definitely won’t give you the option to show up with your own drive. From my experience, you’ll get the machine back with whatever OS was installed when you bought the machine…in this case Leopard. Bringing over your image from the external isn’t very tough. You’ll just boot to the Snow Leopard DVD, reformat the internal drive and restore from the SATA drive you built out.


##Preventing Disaster



So what can you do to avoid this scenario? Probably not a lot. As long as drives continue to have moving parts, mechanical failure is always a possibility. To mitigate the damage to your data, you need to have plenty of backups and keep as much data offsite as possible.


###DropBox



Even if you only have one computer, Dropbox is a great way to keep offsite backups of your current working files. Unless you’re doing photography, music or video editing the 2GB which is free should be more than ample. Take advantage of baked in Dropbox sync for programs which support it like 
[1password](http://agilewebsolutions.com/onepassword)


###Time Machine and Bootable Disc Backups



Even though your documents are pretty critical, the most precious data you have probably won’t work well with Dropbox because of the size. iPhoto libraries and all your media files would overwhelm the free storage pretty quickly. Time Machine is the obvious choice to take care of most of your data. It’s easy to set up and only minimally intrusive. You can always detach the Time Machine drive and plug it into another machine to browse through files…this was extremely handy during the freak-out phase when you think about your photo library.


Backing up external storage that houses media is pretty important too. My media is stored on an external drive, and I cloned it to another one of these internal drives last night using Disk Utility off the installation CD. It didn’t matter to Disc Utility that I was copying from a USB drive to a FireWire drive. Pretty handy really. I’m planning on setting a chron job which will copy my iPhoto library to this drive on a weekly basis so that it can be included in more than one off-site backup disc.


Finally is the operating system backup. This drive will serve as a lifeboat if/when this happens again. I’ll be using 
[SuperDuper](http://www.shirt-pocket.com/SuperDuper/SuperDuperDescription.html) to create these bootable images of the OS. I’ll run backups once a week and once a month (or when OS updates come out) I’ll cycle the drives. One drive will live at my office in a safe, and the other will just live at the house.


##Ready for Anything



Backup schemes like this protect you and your data from hardware failures, theft and fire. With bootable backups of your machine, even if it’s stolen you’ll be able to plug the drive into another Mac (any Mac) and be back and running in no time.


Update:


It’s really kind of amazing how much of a hassle it is to try to recover even a 
small amount of work lost during a hard drive failure. When the dust finally settled, I’d lost the additions to my iPhoto library since my last Time Machine backup, and any changes I made to my iTunes library since the same time. For some reason, the iTunes Library.xml file wasn’t being backed up. I’m not sure if that’s something that Apple builds in (unlikely) or I’d followed a bit of bad advice in setting up Time Machine while excluding certain areas such as the virtual machines I run in VMWare Fusion.


Currently I’m running the 
[Super Remove Tracks](http://dougscripts.com/itunes/scripts/ss.php?sp=removedeadsuper) script to pull out those files which woefully now have the exclamation point next to them. I was able to figure out which files I’d changed by creating a 
[Smart Folder](http://docs.info.apple.com/article.html?path=Mac/10.5/en/8923.html) searching for all music files modified after my last backup. The worst news here, was that I’d fixed a lot of metadata using 
[beaTunes](http://www.beatunes.com/) which included some stuff I’d added (and listened to) ages ago. When this finishes I’ll simply have to eat the loss of play counts and ratings for a lot of Grateful Dead shows. iTunes is great when it works, and will drive you completely insane when it doesn’t. Do yourself a favor and email yourself a copy of this little XML file now and every time that you upgrade iTunes.
