---
layout: post
title: TextMate and MultiMarkdown - The Definitive Guide
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
I’ve really fallen in love with the killer combination of 
[TextMate](http://macromates.com/) and 
[MultiMarkdown](http://fletcherpenney.net/multimarkdown/) in the past few months. Once you pair these two tools with 
[Marked](http://markedapp.com/) you might not even need a full blown word processor anymore.


The challenge in getting this all together is that the resources for getting everthing set up are spread out and a little confusing. Since I write on as many as three computers, I’ve had to get all this going as many as five times in the past few months so I thought I’d pull the steps together into one unified set of instructions.


I take no credit for developing any of these, that credit goes to 
[Fletcher Penny](http://fletcherpenney.net/), the mysterious 
[Dr. Drang](http://www.leancrew.com/all-this/), 
[Brett Terpstra](http://brettterpstra.com/about/) and 
[Ethan Schoonover](http://ethanschoonover.com/).


Needless to say, you should download TextMate before getting started.


##Setup



This should take about 30 minutes. Hopefully less with this step by step tutorial.


###MultiMarkdown



*Download and install the MultiMarkdown package from 
[GitHub](https://github.com/fletcher/peg-multimarkdown/downloads/)


*Download and install the MultiMarkdown Support package from the 
[same page](https://github.com/fletcher/peg-multimarkdown/downloads/)


*Download and install the MultiMarkdown 
[MultiMarkdown TextMate bundle](https://github.com/fletcher/markdown.tmbundle) from a slightly different page at GitHub


*Make sure that everything is good by firing up the terminal and typing “which mmd” to confirm that everything is there.


###TextMate Magic



This is where things can get a little confusing as Dr. Drang has made some changes over time to his snippets and has added additional posts instead of creating one canonical set of instructions. Hopefully this will alleviate some of the confusion that I’ve suffered while doing this a few times.


Reference Links on the Fly


Use this when you’re typing along and want to immediately insert a link.


*Go to 
[this page](http://www.leancrew.com/all-this/2006/03/new-and-improved-textmate-and-markdown-links/) and copy the little perl script to your clipboard


*Follow the instructions on 
[this page](http://www.leancrew.com/all-this/2006/02/textmate-and-links-again/) using the perl script that’s on your clipboard 
instead of the perl script that’s there


*For the macro, use the key combination of CTL+L instead of what’s listed (this is my preference…you can use whatever you like)


Reference Links for Selections


Use this when you’re editing a piece and want to add links to existing text without having to retype anything.


*Follow the instructions on 
[this page](http://www.leancrew.com/all-this/2006/03/markdown-links-in-textmate-the-final-frontier/) without any changes.


*For the macro, use the key combination of CTL+OPT+L (you’ll notice that the more fancy the fu, the more keys you mash)


Footnotes


Dr. Drang actually posted a footnotes bundle in 2010, but I find that the original instructions from 2006 are a little more effective. By now you’re getting into the swing of creating the command and recording the macro so why not do this one by hand too?


*Follow the instructions on 
[this page](http://www.leancrew.com/all-this/2006/05/multimarkdown-footnotes-in-textmate/) and set the key combination to Ctl+F.


###Cleaning Up the TextMate Menus



If you’re relatively new to TextMate that Bundles menu can be overwhelming and cluttered. I like to clean it up a little bit.


*Open the Bundle Editor and click the “Filter List” button. This lets you hide the bundles from view without deleting them. Uncheck the bundles that you don’t need. Click “Done” when you’re finished.


*Now that we’ve got macros recorded for links and footnotes, we don’t need to see the behind the scenes commands in the menu. Click on MultiMarkdown and drag the Brackets, Reference Link Selection, Footnote and My Link commands to the Excluded Items section. They’ll still do their jobs, you just don’t have to see them in the bundles menu.


###Setting up Solarized (Optional)



[I’ve written about](http://bitninja.org/blog/2011/04/23/thing-of-the-week-the-solarized-color-scheme/) Solarized before and still love it. I’m hoping for some better MultiMarkdown syntax highlighting but it’s still pretty decent out of the box.


*Go grab the full 
[Solarized](http://ethanschoonover.com/solarized) package from Ethan’s site.


*Find the TextMate Colors folder and just double click on both the light and the dark themes.


*I also like to install the terminal color schemes as well as the Solarized color palette found in the apple-colorpalette folder. That one’s a little tricky, so be sure to check out the readme.md file.


###Install Marked



This one’s easy. Go to the Mac App store and buy Marked.


##Usage



Now that you’re all set, you’re free to start writing. Obviously you use the regular MultiMarkdown syntax as you’re writing and use the keyboard to insert links and footnotes. Just use the Tab button to move between your display text, the reference or footnote number and the link or footnote text. As you keep hitting Tab, you’ll get right back into the main body of your text.


The key combinations are laid out below:


Key Combo

    
Result

  
Ctl+L

    
Insert a reference link

  
Ctl+Opt+L

    
Turn selected text into a reference link

  
Ctl+F

    
Insert a footnote


As you work, you can get quasi real time preview of the output by dragging the icon in the title bar of TextMate to Marked in the dock. This is especially handy if you want to do some MultiMarkdown tables as shown above.


When you’re satisfied with your draft, use Marked to copy and paste rich text into another word processor, export to PDF or copy the HTML by hitting Command+Shift+C.
