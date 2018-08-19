---
layout: post
title: TextExpander for Lawyers - Sending Email to Clients
categories: []
tags: []
status: publish
type: post
published: true
meta: {}
---
It can be a challenge for people engaged in electronic discovery to identify privileged email communications. Filtering on domain names only goes so far, and because of the boilerplate language included in corporate and firm email searching for terms such as “privileged” or “confidential” can be ineffective.


One way to make this easier is to explicitly state that communications are intended to be privileged in an email. Adding this text is tedious at best, and I can’t tell you how many time’s I’ve typed the phrase “Privileged and Confidential Attorney Client Communication.”


[TextExpander](http://www.smilesoftware.com/TextExpander/index.html), of course, can make that less painful. The following snippet can be triggered from the subject line. It queries you for the actual subject, tabs into the body of the message and inserts the language one more time for good measure.


This may seem like overkill, but a few extra bytes and keystrokes are much better than having a privileged email be produced to opposing counsel.


Privileged and Confidential - %fill:Subject%%key:tab%
Privileged and Confidential Attorney Client Communication%key:return%%key:return%
