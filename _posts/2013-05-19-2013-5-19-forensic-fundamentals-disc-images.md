---
layout: single
title: Forensic Fundamentals - Disc Images
categories:
- Forensics Fundamentals
- Technology
tags: []
status: publish
type: post
published: true
meta: {}
---
##What is a Forensic Image?

A forensic image is a bit-for-bit copy of a digital storage container. This copy includes both data that is accessible to the user (allocated space) and that may have been "deleted" by the user but not overwritten (unallocated space). Forensic images offer stability and flexibility to an investigator that can't be found with consumer like formats. Forensic images can be mounted so that a user can browse the contents of a hard drive as if they were the original user without changing volitile metadata. They can be used to recover lots of peices of evidence using specialized tools in conjunction with commerical or open source forensic utilities.


##File Formats



There are a few different file formats that one can use when acquiring a forensic image. Some formats have additional features than others, but may not be as flexible for certain tasks like recovering data from Volume Shadow Copies.


###The DD or RAW format



While it may be more precise to refer to these images as RAW images, it's very common to hear them referred to as DD images. Why DD? 
[DD is the tried and true Unix utility](http://www.forensicswiki.org/wiki/Dd) which has been used to make bit for bit copies of discs or volumes since the mid 1980s.


Generally, the file format is not compressed and contains no metadata about the image itself, but it can be split into multi part files. Personally, I preferred the use of more modern formats because of the compression availability but recent experience with some Volume Shadow Copy utilities that work only with DD are making me question this preference.


DD images can have a number of extensions including .dd, .raw, .00 or .IMG.


###The Encase or Expert Witness Format



Generally if you're not getting a DD image from a forensic analysist then they'll likely give you an EnCase image. I think it's important to understand that while this format's common name implies the requirement of a specific piece of software, 
[the EnCase format](http://www.forensicswiki.org/wiki/Encase_image_file_format) is supported by many different peices of software.


Encase Images can be compressed, which is a big advantage if you've got a case involving multiple computers and large quantities of data. With the price of 2TB drives coming way down, you can carry and entire office worth of compressed disc images on something that would fit into your pocket.


Encase Images can also carry user defined metadata about the image such as the name of the examiner who took the image, date of acquisition, client-matter (or case) number and some acqusition notes. Encase images ususally carry an extension of .E01.


Even if you initially acquire a disc in Encase format, but need a DD image for analysis with a specific tool, you can blow back a DD image from an Encase image using FTK Imager.


##Image Acquisition



Forensic images can be acquired using a number of hardware and software tools using a wide range of techniquies. Depending on the requirements of a case, one or more techniques may be employed. The end result is the same, though. You'll get a mathematically verifiable bit for bit copy of a particular storage container.


###Hardware Based Acquisition



Perhaps the easiest acquisition method for a lay person to conceptualize is acquisition with a hardware device. This disc cloner will have plugs for drives on both sides of a box, one for the original and one for the copy. Once everything is plugged in, the analyst will choose from some basic menu options and start the copy. The hardware device will only write in one direction, which protects the original evidence. When the copy is complete, the hardware verifies mathematically that the contents of the copy match the contents of the original.


Hardware imagers can either just mirror a hard drive or output to common formats like Encase or RAW.


These hardware imagers are great because they are fast and easy to use. The imager that I use will output to two drives simultaneuously which is a big time saver.


###Software Based Acquisition



A similar process is acquisition using a tool like 
[FTK Imager](http://www.forensicswiki.org/wiki/FTK_Imager) (FTKi). In this scenario, an examiner attaches the original drive to his computer through a write blocker of some kind. Software on his computer will then create the image on the local drive or on another external that's not write-blocked.


Software based acquisition is also used when a machine is being acquired while still turned on. This is common when there are storage arrays attached to the computer or in situations where it's important to preserve all data that resides in RAM or the investigator needs to document open network connections.


Once again, the software makes the copy and then mathematically verifies that the copy is an exact match to the original.


###Network Based Acquisition



Images can also be acquired over the network using either commercial tools, or some elementary Unix commands like netcat and DD. Network based acquisition is experiencing some growing demand, although to be efficient some serious bandwidth is required. Think about how long it would take you to copy 250GB of data over the internet or across your corporate network.


##Practical Use



The easiest way to work with a forensic image is to grab a copy of FTK Imager from Access Data. It's free, and incredibly powerful. If you're an attorney who merely wants to get into the data to look at some of your client documents or mount a PST for some cursory review it's image mounting feature is top notch.


Of course an analyst will use many other tools such as Encase, FTK Lab or Internet Evidence Finder but for some quick and dirty analysis FTKi can't be beat.
