---
title: "The Debug-First Collaborative Coding Pattern (aka Semi-vibe coding)"
date: 2025-07-16T12:00:00-04:00
draft: false
publish: true
tags:
  - ai-engineering
  - AI
categories: []
summary: "A coding pattern that eliminates guesswork by investigating library behavior first, then implementing based on ground truth"
slug: "debug-first-collaborative-coding"
aliases: []
---

## The Problem

LLMs often confidently use libraries without understanding their actual runtime behavior. They make assumptions about APIs that turn out to be wrong, leading to buggy code that's hard to debug.

The Solution: Debug Script → Code → Human-Guided Fixes

Instead of coding blind, we investigate first, then implement:

![Debug-first workflow diagram](/images/Pasted%20image%2020250716173836.png)

## Key Benefits of This Pattern

- Eliminates Guesswork: Instead of LLMs making assumptions about library behavior, we get ground truth

- Faster Debugging: When tests fail, humans can quickly identify the root cause because they understand the actual behavior
  
- Targeted Fixes: Debug output shows exactly where expectations diverge from reality
  
- Cost Effective: Saves tokens and time by avoiding blind iteration


## Today's SpaCy Example

**Traditional Approach (would have failed):**
❌ LLM: "I'll use spaCy to segment sentences and extract line breaks"
❌ Writes code based on assumptions
❌ Tests fail mysteriously
❌ Multiple rounds of blind fixes


**Our Debug-First Approach:**
✅ 1. Debug script revealed: "Spaces are between sentences, newlines are IN sentences"
✅ 2. Wrote segmenters based on this reality
✅ 3. Tests failed with specific assertion errors
✅ 4. Human: "I think it has to do with comparing two similar looking types of whitespace"
✅ 5. Targeted fix addressing the exact issue

## The "Semi-Vibe" Aspect

I call it "semi-vibe coding" because:

- Human intuition guides the debugging process
- AI handles the heavy lifting of code generation
- Tight feedback loop between human insight and AI implementation
- Collaborative exploration rather than blind AI generation
  
This pattern leverages the best of both:

- AI: Great at generating debug scripts and implementing fixes
- Human: Superior at pattern recognition and root cause analysis

> "measure twice, cut once" - someone in the world
