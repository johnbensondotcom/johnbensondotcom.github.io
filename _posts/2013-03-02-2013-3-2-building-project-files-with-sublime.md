---
layout: post
title: Building Project Files with Sublime
categories:
- Technology
tags:
- forensics
- workflows
- sublime
- markdown
status: publish
type: post
published: true
meta: {}
---
After a few months living with Sublime as my primary editor it's become an invaluable tool to how I get all kinds of work done. One of the most powerful aspects of Sublime is it's find and replace tools. This article will discuss how you can create consistent project files using a template and the find in folders feature of Sublime.


##Where this Workflow Fits



When I perform a forensic exam of a computer, I like to keep notes and tool output in plain text format where I can. I've come up with a folder structure that has worked in most situations and scales from an examination of a single computer to many. The key to keeping all the information organized is to distribute information about the case amongst all of the individual files. For example, I want every text file to contain the client and matter name. I want every file related to a specific machine to contain information about the disc image.


##Building The Structure



First you'll want to build out a template folder structure. My structure looks something like this:


z-CaseTemplate
    \Reports
    \Notes
    \Databases
        \IEF
        \FTK
        \Nuix
    \Analysis
        \NAME-HDD-001
            \Registry
                \AcquiredHives
                \ToolOutput
                    \RegRipper
            \Web History


You get the picture. From there, start by creating a single README.txt file and type out some sample information. Mine looks something like this:


Client Name:    $$ClientName
Matter Name:    $$MatterName
C/M Number:     $$BillingNumber

------------

## Case Contacts

## Scope and Objectives

## Deliverables and Timeline


I am using a double dollar signs without spaces as the target for my find-replace move using the editor. This header information shows up in all the text files that I use throughout the project. Once I get to the media level, I'll add some additional information. At that level the text file headers look something like this:


Client Name:    $$ClientName
Matter Name:    $$MatterName
C/M Number:     $$BillingNumber

------------

Media Identifier:   $$MediaID
Image Acquired By:  $$ImageMaker
Date of Image:      $$ImageDate
MD5:                $$ImageMD5
SHA1:               $$ImageSHA1

-------------
