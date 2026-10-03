---
title: "GRC for AI: A Beginner's Guide to Governance, Risk, and Compliance"
author: "Rishi Shukla"
date: "2026-09-30"
tags: [GRC, AI Governance, Cybersecurity, Compliance, ISO 42001, NIST AI RMF, DPDP Act]


A couple of months back I was helping a friend fill out a loan form, and watching the bank's process made me realize something I'd never really thought about: a bank is legally not allowed to just hand your salary details to some random company. Compare that to the free AI chatbot I had open in my other tab, where I'd just pasted in a document without a second thought. Nobody stops you from doing that. That gap is basically what this whole post is about.

<!-- truncate -->

# GRC for AI: A Beginner's Guide to Governance, Risk, and Compliance

## So what's GRC, actually?

GRC = Governance, Risk, and Compliance. Three words that sound boring until you realize they're the reason companies don't just do whatever they want with your data.

- **Governance** is who makes the rules and who's on the hook if those rules get broken.
- **Risk** is figuring out what could actually go wrong, and how bad it would be.
- **Compliance** is just... are we doing the thing we said we'd do, or is the policy a PDF that nobody's opened since it was written.

Put together, it's basically the system that stops "move fast and break things" from becoming "move fast and leak everyone's data."

## Why AI makes this messier

Here's the thing people don't think about enough: we paste *everything* into AI tools. Code, resumes, financial screenshots, half-written emails to our boss. And almost nobody checks what happens to that stuff afterward.

A good example that actually happened: back in 2023, engineers at Samsung's chip division pasted confidential source code into ChatGPT to debug it faster. Reasonable thing to want to do. Except now that code had left Samsung's systems and gone somewhere they had zero control over. Samsung ended up banning generative AI tools on company devices entirely after that. It's become one of those stories every security person brings up when they talk about AI risk, because it shows exactly how this goes wrong  not through some dramatic hack, just an engineer trying to save time.

And the "my data probably doesn't leave the country" assumption a lot of people have? It depends entirely on which tool, which plan, and what the terms of service actually say. OpenAI, for instance, has said in its own data controls documentation that regular ChatGPT conversations can be used to help train future models unless you turn that off yourself. That's disclosed, not sneaky  but almost nobody goes and checks the setting.

This is exactly why banks and similar companies lean toward private or enterprise-grade AI setups with actual contracts around data use, instead of just letting employees use whatever free tool is open in their browser.

### Banking is the clearest example

Banks (and insurance, NBFCs, all of BFSI really) are extra paranoid about this stuff for good reason. If customer financial data leaks because someone fed it into the wrong tool, that's not an "oops"  that's regulators, lawsuits, and a PR disaster all at once.

So GRC in this context is literally the thing standing between "AI tool helps us work faster" and "AI tool accidentally becomes a massive liability."

## The standards everyone keeps name-dropping

If you've been around any security or compliance conversation lately, you've probably heard these thrown around. Here's what they actually mean, stripped of jargon:

**ISO/IEC 27001** - the old-school standard for information security in general. Not AI-specific, but basically the foundation everything else sits on top of.

**ISO/IEC 42001** - came out in December 2023, and it's the first international standard built specifically for managing AI systems. Unlike the NIST one below, this one you can actually get certified against  companies like AWS, Microsoft, and Anthropic have gone through the certification.

**NIST AI RMF** - a framework from the US (NIST), released January 2023. It's built around four functions: **Govern** (set up the policies and culture), **Map** (understand what you're actually building and who it affects), **Measure** (test it — check for bias, security holes, reliability issues), and **Manage** (fix what you found, keep watching). It's not certifiable like ISO 42001 — think of it more as a shared vocabulary everyone in the industry uses. NIST also added a Generative-AI-specific profile in mid-2024 that covers stuff like hallucinations and misuse risks that didn't really apply before LLMs existed.

**RBI / SEBI**  our own regulators here in India. The big recent one is RBI's **FREE-AI Framework**, released August 2025, built by a committee led by an IIT Bombay professor. It lays out 7 guiding principles and 26 recommendations for how Indian banks and fintechs should handle AI  bias, explainability, cybersecurity, the works.

## A rough mental model I use

Standards are great, but day to day I think about it more simply, in four steps:

1. **Govern** - decide the rules before you need them, not after something breaks
2. **Identify** - go looking for problems on purpose. Classic one: your model quietly treats one group's loan applications worse than another's because of skewed training data
3. **Control** - once you know the risk, actually put something in place to stop it (access limits, human review for big decisions, blocking certain uploads)
4. **Monitor** - don't stop watching once it's live. Most real incidents  Samsung included  happen after deployment, in day-to-day usage, not during some big launch event

This isn't an official framework name, just a simple way to think through the lifecycle without needing to memorize NIST's exact terminology.

## The actual laws, if you're in India

- **DPDP Act, 2023** — India's data protection law, passed August 2023
- **RBI Master Directions / FREE-AI** — financial sector specific
- **ISO/IEC standards** — 27001 and 42001 from above

### What the DPDP Act actually requires

A few things worth knowing if you're anywhere near an AI team:

- Consent has to be specific. Old consent from years ago doesn't automatically cover some new AI use case you just rolled out.
- Kids' data gets extra protection  you need actual parental consent, and you can't target ads or track behavior for minors.
- People have a right to know how their data's being used, and to get it corrected or deleted.
- There's now a dedicated body  the Data Protection Board of India  that handles complaints and enforcement.
- The penalties aren't small. Up to ₹250 crore for failing to secure data properly if that leads to a breach, with other categories going up to ₹200 crore or ₹50 crore depending on what went wrong. Even individuals can get fined (smaller amounts, up to ₹10,000) for things like lying on a form.

## Whoever holds the data, holds the responsibility

Under the Act, whoever decides *why* and *how* your data gets processed is called a "Data Fiduciary," and that's a legal responsibility, not optional. Your bank is one for your loan data. If a company builds its own internal AI tool that touches customer info, that company just became a Data Fiduciary for whatever that tool does with the data too.

If something leaks, they're supposed to tell the Data Protection Board and the people affected without sitting on it. And yeah  penalties apply, which is the whole reason this isn't just a documentation exercise.

## The risk nobody talks about enough: Shadow AI

This one deserves its own mention. "Shadow AI" is when people in an org use AI tools nobody approved or even knows about  browser extensions, personal ChatGPT accounts, random free-tier signups. Samsung's incident is basically the textbook case of this: nobody was being malicious, people were just trying to get their work done faster, and it slipped past whatever controls existed.

The fix isn't banning AI outright (that usually just pushes it further underground). It's actually going and finding out where AI is already being used across the org, and bringing it under some kind of governance instead of pretending it isn't happening.

## If you're starting from zero, do these five things

1. Make an actual list of every AI tool being used in the org  shadow usage included
2. Put one specific person in charge of AI risk, not "the team" in general
3. Check whether proper DPDP consent actually exists for how AI tools are using data
4. Try out ISO 42001 controls in one small team before rolling it out everywhere
5. Tell the board what's going on  don't let leadership find out about an AI risk after it's already a problem

## Last thought

GRC people used to get a reputation for just being the ones who slow everything down with paperwork. That's changing fast. With AI, they're increasingly the only thing standing between "we moved fast" and "we moved fast and now we're in the news for the wrong reason."

The line between a bank that protects your data properly and a tool that quietly trains on it isn't really about the technology at all. It comes down to whether anyone bothered to govern it.
