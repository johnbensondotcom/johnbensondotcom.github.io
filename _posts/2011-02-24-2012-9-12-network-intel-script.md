---
layout: post
title: Network Intel Script
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
I’ve known about 
[GeekTool](http://projects.tynsoe.org/en/geektool/) and it’s open source cousin, 
[NerdTool](http://mutablecode.com/apps/nerdtool) since before I even switched from Windows to OS X. For some reason, I always stayed away. Perhaps it was terrible flashbacks to those desktop customization tools like 
[StarDock](http://www.stardock.com/products/windowblinds/) which takes a professionally designed interface and lets people with no design sense remake their user interface in ways which bog down the system. So far, NerdTool has shown no signs of this nasty behavior.


I started considering using this tool after seeing that this really is the easiest way to confirm that your nightly SuperDuper! backup completed successfully. Getting 
[this functionality](http://www.leancrew.com/all-this/2007/04/superduper-reports-with-geektool/) takes a little bit of work (including a little work in the terminal) but it’s worth it. It’s great to grab a cup of coffee in the morning and see whether or not your overnight backup successfully completed.


Since I’d taken the plunge to start running NerdTool, I figured why not throw some other stuff together? You can be as minimal as simply printing the date and time on your desktop, get dangerously close to teetering over the edge by adding an image that changes the weather, or go overly geeky and just run 
[top](http://linux.die.net/man/1/top) all the time.


###NetworkIntel.sh



Every time I connect to a network, I’d like to know a few things that are surprisingly difficult to display all at once in just about any operating system. Confirming my IP address is an obvious and anyone who has had to troubleshoot an internet connection can tell you that the address for the router is equally important. I take it one step further and like to know who else is sitting within striking distance of my computer.


The script below is pretty self evident but the script works by running a couple basic 
[terminal commands](http://linux.die.net/man/8/ifconfig), 
[grabbing content](http://curl.haxx.se/docs/manpage.html) from a static and predictable web page and 
[displaying](http://www.manpagez.com/man/1/awk/) only the information for which you’re looking. I grabbed the actual syntax from a couple of easily found websites (just look for geektool scripts and you’ll find a bunch).


This goes one step further and performs a quick 
[nmap](http://www.insecure.org) ping sweep and pulls out the results.


>echo “Network Intel”
  
  
myen0= ifconfig en0 | grep "inet " | grep -v 127.0.0.1 | awk '{print $2}'
if [ “$myen0” != “” ] 


  then 


  echo Hard Line : “$myen0” 


  else 


  echo “” 


  fi 


  myen1=ifconfig en1 | grep "inet " | grep -v 127.0.0.1 | awk '{print $2}'
if [ “$myen1” != “” ] 


  then 


  echo “Wireless : $myen1” 


  else 


  echo “Wireless : INACTIVE” 


  fi 


  myRouter=netstat -nr | grep '^default' | awk '{print $2}'
echo “AP :” “$myRouter” 


  wip=curl -s http://checkip.dyndns.org/ | sed 's/[a-zA-Z<>/ :]//g'` 


  echo “External : $wip” 


  echo “——————————-” 


  echo “Nearby Machines” 


  echo “——————————-” 


  nmap -sP 192.168.1.1/24 | awk ‘/report/ {print $5, $6}’ 


  echo “——————————-“
