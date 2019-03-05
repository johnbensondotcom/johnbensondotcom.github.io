---
layout: page
title: How Do I Mount and view a Forensic Image?
headline: Understanding what forensic images are and how they are created
permalink: /forensicimages02/
---

You’ve received a forensic image from an investigator that’s stored on an external hard drive. Your client has let you know that he thinks that a file stored on his Desktop at the time the image was taken could be helpful to the case. You plug the drive in and see a number of files that looks like this:

    Rogers-001-HDD.e01
    Rogers-001-HDD.e02
    Rogers-001-HDD.e03
    Rogers-001-HDD.e04
    Rogers-001-HDD.e05
    Rogers-001-HDD.e06
    Rogers-001-HDD.e07

What you’ve got is a multi-part forensic image stored in Expert Witness format…more typically called an EnCase image. To get into this data you don’t need to go out and buy a copy of EnCase, you just need a tool that will mount an EnCase image. Think of mounting like you would plugging in a thumb drive. All of the files are the thumb drive and the image mounting software is the port you’re going to plug it in to. When you’re done, you’ll have a drive letter show up on your computer just like would happen if you plugged in a thumb drive.

There are a few different tools out there for mounting forensic images. The most common and easiest to use is FTK Imager from AccessData. FTK Imager can be downloaded from AccessData’s website for free. Another good option is the free Arsenal Image Mounter from Arsenal Recon. Arsenal is particularly helpful if you’re working with Volume Shadow Copies, which is outside the scope of this post.