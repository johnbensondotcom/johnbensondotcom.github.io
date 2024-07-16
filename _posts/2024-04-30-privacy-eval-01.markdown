---
layout: single
title:  "Evaluating AI Tools for Privacy and Security - Plus the Spring 2024 AI Toolbox"
date:   2024-04-30 00:56:21 -0500
tags: 
  - ai
author: John Benson
---


The other day I found myself relegating an icon that had lived on my iPhone home screen for years to that very last page where apps go before being automatically uninstalled and it occurred to me how much the tools I use on both my phone and my computer have changed over the past few months. Gone are the portals to social media and standalone silos for tasks, notes, and calendar. Likewise my MacOS bears little resemblance to what was running there as late as Thanksgiving of last year. 

In this article I'm going to be running through how I evaluate an AI tool from a privacy perspective, whether it's a stand-alone model like [ChatGPT][1], a search engine like [Perplexity][4], or an integration of AI into an existing tool I use like [Raycast][5]. Then I'm going to run down the different tools that I've started using, how I've been using them, and generally let you know how its been going with each. It's going to seem like a lot of new stuff and frankly it is, but we'll finish by talking about which is my primary and most trusted AI Assistant which is also the best starting point for this whole excursion. 

### Privacy, Trust, and Security

Thanks to [ChatGPT][1] being unveiled to the world in a state which held user privacy in little to no regard, coupled with its clear description as an otherworldly briain that it was likely that if you posted something on the internet ever that you helped contribute to the initial training of it, privacy, trust and security are a big deal right out of the gate. We'll hopefully look back on this as a welcome shock to the system which ushers in a class of technology that has user privacy as a focus out of the gate instead of a boundary to the revenue model of the business. 

In any case, AI tools introduce two new facets for us to consider when we type things into any box on the internet. 

- Will what I type and then read be used to train a future model? 
- Under what circumstances would a person other than myself be able to read the input or the output? 

Ok so that sounds fairly technical, but let's talk about what my concerns are. First, I don't want my inputs or the outputs becoming part of a future pre-training set of someones model. This is primarily because after being worked over by platform after platform, I'm kind of over giving away my words and time to companies for free and you probably should be too. 

The other issue is a little more far fetched but just not the effort, in that if the data was part of the pre-training set of a future model someone might be able to get the model to spit out my content verbatim. That kind of thing has happened but the changes of doing that in a targeted way seem narrow. 

In either case, I'll always be choosing options that say they won't, or where I can control that as a user. A couple points of good news here, generally the options that check this box are plentiful enough that I don't think any service that wouldn't give you the option can just be skipped. Help the market decide. 

Second point of good news is that generally speaking if you're using a model through another tool, meaning it's just talking to a model through its API then model training is already off the table. 

The third piece of good news if you're looking to be privacy and security conscious that you just want to run these things locally that's actually pretty easy and not that costly. 

With training out of the way we need to cover one more layer of consideration which is whether there are any other ways in which someone could review my inputs and outputs. This is a new one to probably all of us, and that's the circumstance where if you trigger a content roadblock it might be reviewed or used in the future. Right now it's something I've seen both from [Anthropic][6] and [OpenAI][3]. [Anthropic][6] does it for all retail users, but not at all for API clients (your third parties using the models). [OpenAI][3] and Microsoft on the other hand require special paperwork to have that kind of thing sorted out. The largest of the API clients I've talked to had this in place before I asked so this is also likely not a very big deal. 

Everyone needs to make their own choice here, however it doesn't ruffle my feathers all that much. Some of my early research involved blindly trying to have Claude summarize the unsealed Jeffery Epstein documents which proved to be content that threw the content filter fairly frequently. I think the issue of if/where/who establishes those guardrails is important for a whole host of reasons, but beyond the scope of this piece for sure. If you are interested in doing research in areas where you think guardrails may hinder the work, running an uncensored version of Llama 3 is going to be your best bet. 

Other than that, if a service is going to be storing my conversation threads on the cloud then I'd like the same level of security and reliability both short (and hopefully) long term as a web hosted email service. Frankly, if a language model host came out that could give the same privacy protections as [Proton][8] I would be first in line. Given that most of us have been using web based email for perhaps multiple decades now that should be a familiar process. 

So really this is what it boils down to. Most companies have all of this outlined in some surprisingly clear privacy policies, some of them have clear and explicit statements that they will never train on your data. Others, not so much. I've seen some tools that look really interesting but have ideas about privacy that are gross. They won't make my list today, or ever. 

## The Spring 2024 AI Toolbox 

So with the kind of boring stuff out of the way now, let's start getting ready to dive into this. Oh and yes, I'm going to put some invite links in here. Certainly not my intention to come off as spammy but wow, everybody wants $20 in this racket and that's not going to slow down if you want more of these articles. 

### Web Browser - [Arc][9] 
Wait, a web browser? Yes actually and for a few reasons. First of all it's got some really neat AI features that just make using it easier. Second it's got some incredible ways of organizing browser tabs in a way that I now find indispensable. Third, this companies message and marketing is kind of amazing and infectious. Let's hope they don't go out of business. 

### Search Engine and Multi-model Interface - [Perplexity][4] Pro

I heard about [Perplexity][4] from Chris Kovac before I was part of the ethics panel at the KC AI club a couple months ago. [Perplexity][4] is on its face a search engine but does more than that. Without getting technical it searches for webpages that have information related to your search, has a language model read your question and the search results, then answer the question for you. Send the result link to someone and they'll get their own fork of the whole conversation where they can ask follow up questions of their own. If you thought "let me Google that for you" was bad, this is that on steroids. 

[Perplexity][4]'s got the added bonus of having a writing mode where you can just interact with the major models (GPT~4, Claude, Mistral Large) all at the same time. An even cooler move is to swap between models mid-conversation to see if one model gives you more of what you wanted than another. 

Other nice features are the image generation, although you don't have as much control as you would going direct to an image generating platform directly, and a labs feature where you can just play with some of the open source models. 

I pay for [Perplexity][4] Pro and really like it. The one hitch here is to remember to shut off the training option once you set up an account, then turn off the training option under your user profile. 

Even if you don't use all the other language model stuff, once you start using it you may never use Google again. I know I haven't used Google for anything other than looking for gifs since signing up for [Perplexity][4] snd it feels great. 

### Personal Knowledge, Tasks, Journals - Notion AI

Notion is a real beast of a tool right now and might just be what the future of how a lot of us work, both in terms of how things are built and what AI can do with a knowledge base at its fingertips. 

I'll be covering a lot more about the amazing stuff that I've made Notion do, but among other things it can tell bedtime stories that explain both the concept of civil asset forfeiture but also explains how ridiculous it is to a five year old. Yes, my task manager does this now. 

### Transcription - MacWhisper 

So the concept of recording your conference calls was creepy and weird until I fed a transcription into a language model. Still maybe is, not going to lie, but transcripts can also be of things like instructional videos from YouTube, podcasts, recorded lectures, etc. 

MacWhisper runs transcription models locally on your machine so no data goes to anyone else, 

### App Launcher - [Raycast][5] Pro

Ok so this ones kind of nerdy, but if you've used spotlight on your Mac by just hitting command+space then you know generally how it works. It's great for one off questions when I don't need to save anything and don't need a follow up. If you do, you can pop it out to a very spartan but pretty functional interface for long chats with a few different models. There are even controls for tuning the behavior of each, which are out there in a way that are easy for people to find. 

This is one that's on the bubble for me right now. Getting access to multiple models requires an additional fee and I'm not sure I need all that power in that context. That said it may be a better starting point for someone who wants something a little different than [Perplexity][4] Pro. 

## Direct Models - [Claude][7] Pro and [ChatGPT][1] Pro 

### [ChatGPT][1] Pro
No, it's not exactly and earth shattering surprise but after you flip the model training off, [ChatGPT][1] Pro is pretty nice. GPT-4 doesn't have the style that I prefer in the writing or engagement I see from Claude but it's got some advanced features that haven't come to Claude and for image generation Dall-E is just fine. 

Prior to the release of Claude 3, GPT4 was the best coding copilot and my python needs all the help it can get. This is one that will likely come and go based on my needs at the time and whether a better option to Dall-E comes around that isn't $20/mo just for image generation. 

Again, make sure to go turn the model training off. 

I think the best thing about [ChatGPT][1] is the way it's implemented on your phone. You'll hear me say a lot soon that the best way to work with a language model is to talk to it, and firing up Miss Clippy for the ride home or while cooking is a lot of fun. 

### [Claude][7] Pro

Ok here we are here at the end of my tool chest with what what should be the first in your toolbox as it was mine. While my read on this technology is that people and companies need to be thinking about being model agnostic and using the right tool for the job, Claude still is the most impressive to me. From the way the leaders comport themselves in public to their clear philosophies of privacy and human involvement over replacement it's the big non-open model i turn to first. 

More than that, it just has a better way with words. Work with Claude for long and you'll realize that language models don't just spit out paragraphs of text that make you question whether you're having a seizure. Overall between the privacy, its performance in terms of language, and the things I've had it do with massive quantities of data already if I've got some work that matters, I'm firing up Claude directly.

[1]: https://chatgpt.com
[2]: https://openai.com/chatgpt/
[3]: https://openai.com
[4]: https://www.perplexity.ai
[5]: https://www.raycast.com
[6]: https://www.anthropic.com
[7]: https://claude.ai
[8]: https://proton.me/mail
[9]: https://arc.net
