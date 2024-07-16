---
layout: single
title: Using Grep to Work With Text
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
Grep is one of the more powerful tools in the *nix toolkit.  Any person who works with large amounts of text should have at least a basic understanding of how to apply grep and export its output to a smaller file for future use.


I have used grep in two contexts recently to great success.  First, in searching through directory listings for certain key terms as part of the electronic discovery process and second in parsing output from nmap as part of the confucker script which I threw together to analyze networks for conficker infection and vulnerability.


**Preparing Your System**


If you're already using a *nix based system, you're already set up.  If you're on Windows you'll need to install cygwin which will allow some level of *nix functionality.  As an aside, the default shell is ugly as hell.  When installing, consider adding the wintty package under shells.


**Planning for the Output**


Take a look at the file you'll be searching.  If you're wanting to extract a number of lines surrounding the term, count the lines.  Grep works by searching for terms, then spitting out the line which contains the term plus lines on either side.  This is controlled by the -B and -A switches.


Next, you'll want to figure out how to organize the data when it's spit out.  If you have multiple files you'll be examining, but only want one file full of results you can choose to append using >>.  


**Structure of the Querry**


The grep command itself will be structured like this: 



grep -B <lines to copy before term> -A <lines to copy after term> <search term> $target.txt >> $results.txt 


$target.txt is the file which you are searching and $results.txt is the output.
