---
layout: post
title: Getting Into Keyboard Maestro
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
Recently I acquired a license to 
[Keyboard Maestro](http://www.keyboardmaestro.com/main/) through the Productive Macs bundle. I’ve really taken to TextExpander, and find myself missing it when I’m away from a computer that I can’t control. I’d read some stuff about KM, but even after a little time tinkering I didn’t see it becoming a real part of how I work. That changed this weekend.


I’ve been looking for a better path towards a unified writing platform, regardless of whether I’m writing a long form post like this one, or a link with some quick commentary. TextMate is, and will remain for quite some time, my tool of choice. What I wanted was a way to:


*Quickly jump into TextMate with the link I want to point to


*Write whatever I’d like to accompany the post in MultiMarkdown


*Make sure that I’ve got a copy saved as plain text for future reference and archival purposes


*Get the post on the web without having to rely on another program (MarsEdit) or spend much time fiddling in the WordPress control panel


Keyboard Maestro ended up solving almost all these issues.


I’ve got a screenshot below, but in about 20 minutes, I have taken almost all of the overhead clicking and typing from the process. Now when I highlight a link and mash CMD+F5, I’m asked what I want to title the post. After inputting the title, a text file containing my naming convention (blogx - YYYYMMDD - $title) is saved to DropBox and my link is added to the top with a period at the end to facilitate the whole rss-title-as-link thing that I like so much.


When I’m done, I hit Shift+CMD+F5 which converts the markdown to HTML, copies it to the clipboard and then opens up the PressThis window in my browser. The only thing left to do is remove an extra paragraph tag that gets inserted to my link at the top.


I think this is extremely slick, and see some more of these macros in my future.
