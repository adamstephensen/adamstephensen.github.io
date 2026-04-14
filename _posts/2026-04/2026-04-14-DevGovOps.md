---
title: "DevGovOps: Building Trust in AI" 
permalink: /2026/04/14/devgovops-trusted-ai-at-scale/
layout: post
tags:
  - Azure
  - AI
---


# DevGovOps: Governance Belongs in the Loop


Let me start with a pattern I keep running into.

You're deep into delivery — maybe building an AI system, maybe scaling one — and the team is moving well. Then, right before you're ready to ship, the **governance checkpoint** arrives. A compliance review. A risk board. A stack of late-stage concerns that nobody surfaced earlier because nobody was in the room earlier.

Progress stalls. Trust between builders and gatekeepers frays. Timelines slip.

And here's the thing: this isn’t a one-off.

The problem isn't that governance people are difficult, and it isn't that delivery teams don't care about risk.

It’s that **governance is still treated as a gate** — something that lives outside the flow of work, applied after the fact, rather than woven into how we build and operate systems from the start.

---

<img src="/assets/images/posts/2026-04-14-DevGovOps-01.png" alt="Noosa beach" class="img-responsive">

## We’ve seen this movie before

The lineage matters here, because it shows we already know how to solve this kind of problem.

**DevOps** emerged because dev and operations/infra teams were at war. Devs threw code over the wall; ops threw it back. The fix was continuous delivery and shared ownership of the entire lifecycle. The outcome was faster, more reliable software.

**DevSecOps** emerged because security kept arriving too late. Teams would build for months and then hit a penetration test or security review that blew up their timeline. The fix was shifting security left — embedding it into the pipeline, making it part of everyday delivery. The outcome was safer software without killing velocity.

In both cases, the pattern was the same:

> A critical concern that was being treated as an external checkpoint got pulled into the continuous flow of delivery.

And in both cases, people worried it would slow teams down. In practice, the opposite happened. Automation and shared ownership reduced late-stage surprises — and accelerated delivery.

Now look at governance.

Same story. New decade.

**Governance is still being thrown over the fence.**

And with AI, that doesn’t work.

---


## DevGovOps — what I mean by it

Here’s the crisp version:

> **DevGovOps is the practice of embedding governance, risk, and compliance directly into the development and operational lifecycle of AI systems.**

Governance, in this framing, is:

- Not a review board  
- Not a checklist  
- Not a single control  

**It lives in the execution loop.**

The fix is to embed governance into the lifecycle.  
The outcome is **trusted AI at scale**.

Or put another way:

> **DevOps gave us speed.  
> DevSecOps gave us safety.  
> DevGovOps gives us trust.**

<img src="/assets/images/posts/2026-04-14-DevGovOps-02.png" alt="Noosa beach" class="img-responsive">

---

## Why AI makes this urgent

You might reasonably ask: governance has *always* existed — why does it need its own “‑Ops” moment now?

Because **AI systems fail differently**.

Traditional software systems are largely deterministic. You test them, you deploy them, and if the tests pass, you have reasonable confidence they’ll behave as expected.

AI systems are **probabilistic**.

- Behaviour evolves  
- Risk emerges at runtime  
- A system that “passed” pre‑deployment can drift out of acceptable bounds weeks or months later  

You can’t define exact expected outcomes. You have to define **acceptable ranges of behaviour** — and continuously verify that the system stays within them.

A governance model built around a single pre‑deployment review is structurally inadequate for this.

If your approach is _“pause everything for a big review before go‑live, then hope for the best”_, you’re not governing AI — you’re ignoring risk after day one.

The implication is uncomfortable but clear:

> **Governance for AI systems has to be continuous, automated, and embedded into runtime — not treated as a one‑off gate.**

If you don’t bring risk, governance, security, and infrastructure teams on the journey, you never get to production.

---

## What this might look like 

This is not a finished framework. It’s an early articulation, grounded in patterns I’ve seen work (and fail) in our project deliveries.

### Design‑time: shift‑left governance
- Threat modelling for AI systems  
- Explicitly defining acceptable behavioural ranges  
- Defining agent capabilities and boundaries before code exists  

### Build‑time: governance as code
- Policies embedded directly into prompts, system messages, and agent schemas  
- Infrastructure‑as‑code enforcing guardrails by default  
- CI/CD checks that validate governance constraints — not just unit tests  

### Test‑time: continuous evaluation
- Automated evaluation pipelines  
- Hallucination testing, safety testing, prompt‑injection scenarios  
- Regression testing for prompts, agents, and workflows (because prompts *are* code now)  

### Runtime: guardrails and enforcement
- Real‑time restrictions on outputs and actions  
- Human‑in‑the‑loop escalation enforced via the orchestrator — not left to the model  
- Controls that assume failure is inevitable, not exceptional  

### Identity & permissions: agents as identities
- Agents treated like first‑class identities  
- Least‑privilege by default  
- Every tool added increases the attack surface and must be justified  

### Observability & ops: continuous governance
- Monitoring drift, quality, and risk signals  
- Feeding those signals back into the system  
- Cost and usage anomalies treated as governance signals, not just ops metrics  

None of these ideas are radical on their own.

The argument for DevGovOps is that **they only work when treated as one coherent system** — enforced via architecture and automation rather than process and paperwork.

---

## What this is (and isn’t)

A few important boundaries.

- **This is early thinking**, not a finished methodology.
- It’s a pattern I keep seeing, a name I’m putting on it, and a hypothesis about where delivery needs to go.
- I’m certain there are blind spots.

The trade‑off I’m most wary of is bureaucracy‑by‑another‑name. If DevGovOps turns into more forms, more YAML, and more friction, it has failed. The goal is for **lightweight, automated, continuous governance to replace heavyweight, manual gates** — not to add more ceremony.

And yes, governance overlaps with security — but it’s broader:
- Regulatory compliance  
- Data sovereignty  
- Ethical use  
- Auditability  
- Trust and explainability  

DevSecOps brought security into the pipeline.  
DevGovOps is about bringing the *rest of governance* in as well.

---

## What’s next

My goal isn’t to convince everyone — it’s to see where this resonates, where it breaks down, and what I’m missing.

If this mirrors pain you’re feeling in delivery, I’d love to hear from you.  
If you think this is misguided, even better — tell me why.

DevGovOps only makes sense as a conversation **we start earlier**.

So let’s start it.

- Adam