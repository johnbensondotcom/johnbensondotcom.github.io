---
layout: single
title: Hosting Your Website with GitHub Pages  
categories: [Jekyll]
tags: []
status: publish
type: post
published: true
meta: {}
---

Thanks to a new addition to the family I had the opportunity late last year to reevaluate the household expenses. One monthly charge that wasn't going to work anymore was the fairly hefty fee I was paying to [Squarespace][squarespace] each month. Don't get me wrong, Squarespace is a fine service for hosting a website but given the fairly meager amount of traffic I get it just wasn't worth the $10 per month. Pretty quickly I settled on GitHub Pages as the most viable and lowest cost alternative. After getting everything up and running, I think it provides a better writing experience too. 

You can host a site on [GitHub Pages][github] for free. It even supports SSL and handles all the BS that it can bring by simply checking a box. Putting all the pieces together takes a little bit of work, but I would say that if you're a person who used to be comfortable managing Wordpress on your own via a host like [Dreamhost][dreamhost] then you can figure out GitHub Pages. 

You can simply upload static HTML pages, but the more robust approach is to use a static site generator like [Jekyll][jekyllrb]. There are a number of [static site generators out there][staticgen] that run based on different languages, but since Jekyll is baked into GitHub Pages it's probably your best bet. 

Installing Jekyll on your local machine is fairly simple, although I find Ruby to be kind of clunky. At one point I took a break from this project and when I returned the whole thing seemed broken. A couple trips to Stack Overflow got things going again though and it's been smooth sailing ever since. You should also be careful to install the version of Jekyll that is [supported by Github Pages][supportedversions]...as of the date of this post GitHub doesn't support the current (4.0.0) version of Jekyll. 

Working with page templates and style sheets in Jekyll is fairly straight forward. I got out of the web development game before CSS frameworks became a thing, but I found the [Sass][sass-lang] framework to be pretty simple to work with. The only real hurdles I encountered related to [footnote styling][pablogonzalezalba] and how to create [linked list][github 2] (aka [Daring Fireball][daringfireball] style) posts but those were dealt with over the course of a couple evenings. 

Once I settled on a look and feel for the site, I started work migrating content from the old site to the new. There is a script that can help with this, but you'll want to QC everything that comes over. I also took that opportunity to prune out some posts that didn't really stand up over time and didn't have much archival value either. 

The final product is quite nice. The HTML that's generated is super clean, loads quickly, and supports unique styles for phones and iPads. If you're currently using Wordpress you'll also appreciate that since all the content is static you won't find yourself scrambling to patch some plugin before your site gets covered up in malicious garbage. 

I noodled around on this project for a couple months, but I'd say that with the appropriate amount of focus a person could have a fully customized and configured site up over a long weekend or over the course of a week working in the evenings. Hopefully this new setup will help me spend more time generating content instead of fiddling with the site or dealing with weird Markdown conversion issues. I'd like to give a special shout out to [Pablo Gonzalez Alba][pablogonzalezalba] whose series of posts about Jekyll proved to be just the documentation that I couldn't find in the official docs. 

[pablogonzalezalba]: https://pablogonzalezalba.com/tag/jekyll
[daringfireball]: https://daringfireball.net
[dreamhost]: https://dreamhost.com
[github]: https://pages.github.com
[github 2]: https://github.com/chfvoigt/jekyll-linkposts
[jekyllrb]: https://jekyllrb.com
[pablogonzalezalba]: https://pablogonzalezalba.com/2017/02/16/jekyll-footnotes.html
[sass-lang]: https://sass-lang.com
[squarespace]: https://squarespace.com
[staticgen]: https://www.staticgen.com
[supportedversions]: https://pages.github.com/versions
