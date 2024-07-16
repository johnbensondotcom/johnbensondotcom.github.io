---
layout: single
title: Scrivener and MultiMarkdown - Mostly a One Way Street
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
Last week I had the pleasure of delivering a short talk on Markdown at CCCKC. One of the reasons cited as a big benefit of the format is that it can be manipulated and output through 
[Scrivener](http://www.literatureandlatte.com) to just about anything. As I worked in Scrivener with some prior writings, I started to run into some frustrating problems, primarily with links and footnotes. This led me to find the edges of support for MultiMarkdown within Scrivener.


The developers of Scrivener do a nice job of touting its support for MultiMarkdown. While this is warranted, they don’t do enough to explain the limits of this support.


As nice as Scrivener for drafting is, TextMate is still my favorite MultiMarkdown editor. I have some considerable muscle memory dedicated to the shortcuts I built which let me to fly though text, adding reference links and footnotes. Scrivener’s document compilation features are nearly perfect. Scrivener also will sync projects to text files and folders which seems like the perfect match for this kind of workflow.


When you read about writers using Scrivener and MultiMarkdown together, it appears that they are:


*Primarily using scrivener as their main writing program


*Using MultiMarkdown as an export format only…not as a format for working files


Here’s my problem. I want to


*Use Scrivener primarily as a document manager and other tools for my actual writing


*Use MultiMarkdown as a working and archival format, with other formats like RTF or PDF as the distributed format for my final product


The problem is that while Scrivener can convert its own link and footnote formats to MMD during a compile, it can’t go both ways. Once you sync the Scrivener document to text, you’re stuck with only adding things like text formatting to the document. If you want to add things like footnotes and links, you’re out of luck since Scrivener just sees them as plain text. It doesn’t mess up the formatting when you export to MultiMarkdown, but that’s not really the point.


When I write in Scrivener, it’s a big document which is most probably destined to end up in PDF. This means footnotes should go at the bottom of the current page and not at the end of the document which is what happens when you export to MMD. This is fine for HTML output but not for PDF.


There are two possible workarounds for this. First is to export from Scrivener as MultiMarkdown then to 
[LaTeX](http://http://www.latex-project.org/). The second is to go from MultiMarkdown to OpenDoc then to PDF. Neither of these options is great at this point.


LaTeX shows some real promise, but holy crap it appears to be very complex. The approach is the right one in that it it formats based on my markup and a style sheet outputting to a beautiful PDF. Great in theory. However there is a reason that students outside the physics and match departments of universities never hear about this. The syntax is really tough to pick up quickly. As much as I want to set up templates that conform with the styles I’ve developed based on 
[Typography for Lawyers](http://www.typographyforlawyers.com) it looks like it would take a considerable amount of time or effort.


Round tripping through ODF brings its own set of headaches. LibreOffice and OpenOffice are crazy ugly and their support for styles is confusing and bizarre. Most importantly there is no way to apply a set of styles to the entire document once it’s been imported. If you’re only tweaking the typeface and font size it’s no big deal but I’m way to particular about the typesetting to view this as a good option.


While I hope to update this post, crossing out all that I’ve said about Scrivener’s handling of incoming MMD syntax, I’m not optimistic. For now, I’m sticking to using Scrivener as my primary editor when I’m looking to publish to PDF and TextMate for everything else.


Hopefully they will open the other side of the street soon.
