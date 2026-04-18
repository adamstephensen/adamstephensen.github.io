---
title: "Is the Microsoft IQ Layer just another layer?" 
permalink: /2026/04/18/positioning-the-iq-layer/
layout: post
tags:
  - Azure
  - AI
---

## Microsoft AI Ecosystem: Rethinking the Diagram After Ignite

After Build 2025—and the flood of announcements across Copilot, Copilot Studio, Foundry, and Fabric—I found myself stepping back and trying to make sense of what was actually happening.

What struck me was that we were moving beyond the days of picking a single tool and trying to use it for everything. Instead, we were starting to see a more mature ecosystem emerge—one where you could choose the right tool for the job, and more importantly, start connecting them together.

With emerging protocols like MCP and A2A, it felt like these previously separate parts of the Microsoft AI ecosystem were beginning to integrate into something more cohesive.

A high-level map started to form in my head.

And I managed to get down what I thought was a pretty solid representation of the Microsoft AI ecosystem.


![The Microsoft AI Ecosystem - Build 2025](/assets/images/2026-04/MS-AI-Ecosystem.png)

At the time, the model made sense:

- Experiences at the top  
- Agents emerging as a new application layer  
- Data and integration underneath  
- Platform capabilities powering everything  

It reflected what we were building.

---

## Then Ignite happened

And with it, something that I think is genuinely significant:

**The introduction of the “IQ Layer”**

- Work IQ  
- Fabric IQ  
- Foundry IQ  

Microsoft is formalising something many of us have been feeling for a while:

> Intelligence is becoming a *first-class architectural concept*.


A set of **cross-cutting intelligence capabilities** that span:

- **Human context** (Work IQ) — people, meetings, emails, conversations  
- **Data context** (Fabric IQ) — structured, semantic, and real-time enterprise data  
- **Execution intelligence** (Foundry IQ) — models, tools, memory, and orchestration  

---

## So now I’m rethinking the diagram

The question I’ve been wrestling with is this:

**Where does the IQ layer actually sit?**

Is it:

### Option 1 — A layer in the stack?

Something that sits between data and agents?

![The Microsoft Enterprise Ecosystem - Ignite 2025](/assets/images/2026-04/MS-EI-Architecture.png)

This is intuitive, clean and familiar... using layers as we have done for many years. 

It makes sense when calling out all the components in a smaller piece of architecture.

But… it also undersells what IQ is trying to be.

It makes intelligence look like just another capability in the stack.

---

### Option 2 — A cross-cutting layer over the entire Microsoft Cloud?

Something that *wraps* the ecosystem?
![The Microsoft Enterprise Ecosystem - Ignite 2025](/assets/images/2026-04/MS-EI-Ecosystem.png)

This feels closer to the intent.

It positions the IQ layer as the thing that turns all the other layers into something smarter.

It reflects: 

- Agents are becoming orchestrators, not the intelligence itself  
- Data platforms are becoming semantic, not just storage  
- Applications are becoming entry points into intelligence, not logic containers  

---

## Why this matters

How this is represented shapes how people think about how their solutions hang together.

If IQ is “just another layer”, you’ll build differently  
than if IQ is “the thing that powers everything”.

---

## My current leaning

Right now, for the workshop I'm running this week... I’m using both.

- The IQ layer at the top to introduce the concepts and focus on the new capabilities
- IQ Layer sitting over integration and knowledge when I start looking at subsets of the ecosystem as they ralate in individual projects and more directly in application architecture diagrams.

---

I’m keen for feedback (the reason for this post):

**How are you thinking about the IQ layer?**  
**Where would you place it in the architecture?**  
**What have I missed that should be included ?**
