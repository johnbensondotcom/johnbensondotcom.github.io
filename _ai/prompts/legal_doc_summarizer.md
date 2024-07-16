---
title: "Court Filing Summarizer"
layout: single
author: John Benson
date_published: 2023-06-15
prompt_type: "Legal"
ai_model: "Claude, ChatGPT"
tier: "Intermediate"
use_case: "Summmarizes a document like a pleading, motion, filing, letter etc. to extract and summarize key information"
tags: 
    - ai
    - prompts
classes: wide
---

## What the Prompt Does

This prompt is designed for an AI to analyze a legal pleading or letter. The AI is expected to extract key information from the document, summarize the main points, and identify relevant legal issues. 

## How to Use It

This is great for populating a project management system with key information and dates and can be a great way to bring people up to speed on a case when they're added. Start out with this prompt, review the ouptut and then continue to work in the thread over time. 

It makes more sense to have this saved as a snippet or prompt to inject as the first part of a thread for the project instead of using it as a stand-alone system instruction. 

## Why it Works 
First off, don't be scared by the XML. That's there to help the model keep track of everything as it does its work. Claude in particular, as stated in their documentation, reacts espcially well to XML. You can literally make it up as you go, it's just brackets and a forward slash...nothing too crazy. 

We start by clearly telling the model what we're doing, then define it's output by giving examples. Note that examples instead of specific requirements go in brackets. 

It extracts key information and puts it into a table, then walks through a farily standard analysis. 


```xml
<LegalPadPrompt>
<task>
Your task is to carefully review the provided legal pleading or letter and extract key information, summarize the main points, and identify relevant legal issues. Tailor your analysis to the specific document, only including sections that are applicable. Do not fabricate details or discuss irrelevant matters.
</task>

Use the following modular structure for your analysis, omitting any sections that do not apply:

📝 <Key_Information>
Present essential document details in a table format:
| Item  | Details |  
|------|---------|
| Parties Involved | [List parties] |
| Jurisdiction and Venue | [Specify jurisdiction and venue] |
| Case Number and Judge | [Case number and judge, if applicable] | 
| Date of Document | [Date] |
| Type of Document | [e.g., complaint, answer, motion] |
</Key_Information>

📝 <Summary>
Provide a concise summary covering factual background, legal claims or defenses raised, and relief sought (if applicable). Aim for a clear, high-level overview of the document's content and purpose.
</Summary>

📝 <Causes_of_Action_and_Claims>  
Enumerate the specific causes of action and claims presented in a numbered list. Help quickly identify the legal bases.
</Causes_of_Action_and_Claims>

📝 <Damages_and_Relief_Sought>
Outline the damages or relief requested by the filing party in a numbered list. Clearly specify what they are seeking from the court.  
</Damages_and_Relief_Sought>

📝 <Defenses_and_Counterclaims>
List any affirmative defenses, counterclaims, or cross-claims raised. Anticipate potential challenges or additional issues that may arise.
</Defenses_and_Counterclaims>

📝 <Legal_Issues> 
Itemize the main legal questions or problems implicated in the document that will need to be addressed.
</Legal_Issues>

📝 <Relevant_Facts>
Extract pertinent facts and allegations, presenting them chronologically in a table format:
| Date | Event |
|------|-------|
| [Date 1] | [Event 1] |  
| [Date 2] | [Event 2] |
| [Date 3] | [Event 3] |
</Relevant_Facts>

📝 <Relevant_Authorities>
Identify legal authorities cited or implicated: 
- [Statute 1]
- [Case Law 1]
- [Rule 1]
</Relevant_Authorities>

📝 <eDiscovery_Considerations>  
Highlight issues related to electronically stored information (ESI):
1. [Potential ESI sources]
2. [Preservation and collection steps] 
3. [Required formats and production specifications]
4. [Privilege or confidentiality concerns]
</eDiscovery_Considerations>

📝 <Jury_Demand>
Note if a jury trial has been requested and by which party. This is crucial for case management.
</Jury_Demand>  

📝 <Questions_and_Clarifications>
Identify gaps in information or areas needing further investigation. List specific questions to resolve.
</Questions_and_Clarifications>

📝 <Technical_and_Administrative_Details>
Present deadlines, filing requirements, service of process matters, and anticipated discovery needs in a table.
</Technical_and_Administrative_Details>

As you conduct your analysis:
- Discern true objectives by examining language and tone 
- Seek clarification to understand context and goals
- Consider audience and craft a bespoke response
- Employ clear logic to distill complex issues
- Demonstrate desired format with examples
- Continually refine based on feedback 
- Draw upon legal knowledge to address all angles
- Vet outputs for accuracy and appropriateness
- Empathetically engage and build rapport
- Address explicit and implicit needs
- Exceed expectations with perceptive, substantiated insights

To inform your analysis, conduct targeted research from authoritative sources, such as:  

"venue requirements federal diversity jurisdiction site:law.cornell.edu" 
"complaint alleging breach of contract site:dockets.justia.com"
"techniques for analyzing complaints filetype:pdf site:apps.americanbar.org"  

Evaluate research based on relevance, authority, objectivity, depth, and freshness. Extract salient points and examples to weave into your response. Synthesize findings to construct persuasive arguments.

Append a list of your search queries, categorized by subtopic. Pair precise keywords with resource types to yield illuminating information.

Deliver astute, contextually aware analyses supported by thorough research. Provide meaningful insights that demonstrate understanding and exceed expectations. Empower the human with critical knowledge and strategic thinking to deftly handle their legal matter.
</LegalPadPrompt>
```