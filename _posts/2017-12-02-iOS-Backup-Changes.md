---
layout: post
title:  "You Can Now Reset an iOS iTunes Backup Encryption Password on an iOS device and That's Not Necessarily a Good Thing"
date:   2017-12-02 22:36:20 -0500
categories: forensics  
---


Apple has made a change to how encrypted iOS backups are handled in iOS 11 that makes it easier to deal with a forgotten backup password, but creates a cascading effect that makes your phone passcode the only thing standing between an attacker and access to all of the credentials iOS keychain.<!--more--> 

### History of iOS Backups

If you go way back, when you made a backup of an iPhone, you would plug it in, connect it to iTunes, initiate the backup and iTunes would copy the data to the drive and iTunes would then encrypt that backup on the computer's disc. The password you set for the backup was specific to the backup, meaning if you forgot the password to that backup it was no big deal. You could just blow the backup away, create a new backup with a new password you knew and you were off to the races. 

As iPhone became more powerful and device storage was easier to come by, Apple changed this. With a current phone, the process looks and feels similar but is different. Now when you create the backup, it's the phone that does all the work. It compiles the files on the device, encrypts those files on the device, then just spits the final encrypted data out to the computer.[^1] 

That change in where the work was happening coincided with a change in how and where the encryption portion was applied and stored. Now when you set an iOS backup password that backup password sticks with the device for future backups. 

### Here's the Problem Apple Was Trying to Solve

A couple years ago I dropped my iPhone and broke the screen. Knowing that there was a good possibility that Apple would just swap out devices, I created an encrypted backup on my laptop and just used some random password and didn't store it in my keychain or in my password manager thinking that I only needed to remember the password that afternoon. Well it turned out that Apple just swapped out the screen so I blew away the backup and moved along. 

Fast forward to the time the next iPhone comes out. When I went to back the phone up so I could transfer all my data I was prompted for a password. A password that I had absolutely could not remember. I was out of luck and mildly annoyed, but didn't loose any data in the long run because I also used iCloud to back my stuff up. I had to log into all my services again once I got the new phone but it was fine. But I'm a nerd, and have a much higher pain tolerance than your average iPhone user who would have likely been a little more upset. 

At no time did Apple make a big deal about this change. Nor did they include some kind of language to the user that it was really important that they not loose this backup password. To make matters even more confusing, once you set the backup password iOS and iTunes would let you make subsequent encrypted backups of the device to any number of computers without requiring you to input that password. 

This led to the following crazy-making scenario. While working with a client who needed me to retrieve some of their text messages, I walked them through how to back their phone up and explain the importance of remembering their backup password. When they went go to back up the phone, instead of being prompted to input their backup password, iOS would just created a new encrypted backup without asking for the password or saying "hey, this backup is encrypted with the password you set on 7/7/2017". I would receive their backup, call them up and say "hey, what's that password you entered this weekend when you backed this thing up?" Their truthful but confusing response was that they weren't prompted for a password. These days we don't back up phones locally a whole lot...maybe as little as once every two years. Since they never really interacted with that password requirement, it meant that the password was super easy to forget. 

Even more bizarre, there's no way within iOS itself to manage the backup password or even see whether one has been applied. 

### How Apple "Solved" the Problem

Apple's response to what I'm sure was a substantial amount of complaints is straight forward. [Now, as long as you've got the device unlocked][apple], you can simply dig into settings and reset the local backup settings.[^2] Easy? Yes. Is it a potential security problem? Absolutely. 

### The Cascading Effect of iCloud Keychain

So what's the problem here? If someone's got physical access to my device and they've got my passcode they've got total access to the information on the phone by just fiddling around, right? Well that's only part of the picture once you bring forensics tools into the mix.[^3] 

iCloud keychain is becoming more difficult to avoid. If you want to use HomeKit to control your home automation stuff, you've got to enable iCloud Keychain. If you also enable iCloud keychain on MacOS, the full keychain now resides on your iOS devices as well as your iOS devices. Your keychain is also included in an encrypted iOS backup, which was fine when your backup could have been protected by a long and strong passphrase, but now it's only protected by your iPhone passcode.  

### The Threat Model

Let's say you're all in with the Apple ecosystem and iCloud syncing. You've got a Mac, you've got an iPhone and you've got an iPad. You like iCloud keychain syncing because having a password keeper is a good idea and the syncing makes it much easier to use across devices. 

Your iPhone has a fairly unique six digit code to access and it's always with you, but the iPad is a much more casual device that gets passed around the family. You go ahead and make that passcode 111111 because it's easy for everyone to remember. You take the iPad out to a coffee shop one day, someone shoulder surfs your passcode and then snags the iPad when you're in the bathroom.

Now that person takes the iPad to their house, hops into your iPad, resets the iOS backup password on the iPad, and then feeds that backup to Elcomsoft Phone Breaker. Phone Breaker will allow them to access your full iCloud keychain. Now they can see your passwords and pivot to email, Amazon, and all of your other services. [The folks over at Elcomsoft have a detailed post on how far down the rabbit hole you can get under this scenario.][elcomsoft]

### What Should Happen Now?

My recommendation is to at least set the passcodes for your iOS devices to a long alphanumeric passphrase instead of the six digit passcode. That makes it less difficult for someone to guess, and much more difficult for someone to brute force.[^4] In prior versions, you needed to do this anyway so that the phone bumped up its internal security. My recommendation for Apple? Go back to the old model with some better user communication. Make it clear to users that their backup password is not something they should forget easily. Give users a way to see what settings they've applied for their backups. A backup password reset process from within iOS is probably a good thing, but it shouldn't be so readily available to anyone that's got an unlocked phone in their hand. 

In the meantime, those of us working in digital forensics have a way to deal with clients who may have forgotten their iOS backup passwords. Good news for the forensics investigator part of my brain, not good news for the security part of my brain. 

Finally, in light of these changes I've updated my [documentation on taking iOS backups][john-benson] over in the Forensics and E-Discovery section of the site. 

[^1]: This is observable by taking a look at the resulting backup on the computer. Even though the backup may have taken a couple hours, the modified and creation times for the backup files will be all within a few minutes of each other.

[^2]: Settings --> General --> Reset --> Reset all Settings. You'll notice that there is no indication in the UI that you are wiping out the backup encryption settings. 

[^3]: Wireless passwords are synced across devices as one example. Something I discovered when I took my new iPad to the office and it joined right up with the wireless network without me needing to type it in. 


[^4]: I also believe that a password or passphrase is going to be easier to keep track of. I'm staring at my old iPhone 6 that I'm about to reconfigure as a testing device and I have no clue what the unlock code was that I used the week that I got my 7 plus. I partially blame corporate policy that keeps making me cycle these six digit codes. 



[apple]: https://support.apple.com/en-us/HT205220#help
[john-benson]: https://john-benson.com/forensics-fundamentals-extracting-text-messages-and-other-data-from-an-iphone/
[elcomsoft]: https://blog.elcomsoft.com/2017/11/ios-11-horror-story-the-rise-and-fall-of-ios-security/