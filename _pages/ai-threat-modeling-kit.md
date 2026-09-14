---
permalink: /projects/ai-threat-modeling-kit/
title: "AI Threat Modeling Workshop Kit"
excerpt: "A 2-hour workshop kit that adapts STRIDE for AI systems, with an OWASP LLM Top 10 and MITRE ATLAS overlay."
toc: true
toc_label: "On this page"
---

A ready-to-run kit for facilitating AI threat modeling sessions, built on STRIDE with an OWASP LLM Top 10 and MITRE ATLAS overlay. Includes a 20-card threat deck and a fully worked example.

[View on GitHub]((https://github.com/hela86/ai-threat-modeling-workshop-kit))

## Problem

Threat modeling frameworks predate AI. STRIDE was published in 1999, and neither it nor PASTA has a native category for prompt injection, training data poisoning, model inversion, membership inference, or the fairness harms that regulators now treat as high risk. The result is that most teams either skip threat modeling for their AI systems, or run a standard application security workshop that quietly misses every threat specific to a model. This kit closes that gap without discarding a method people already know.

## Approach

- **Kept STRIDE as the scaffold.** It is 25 years old, and teams adopt it quickly, so the workshop starts from familiar ground rather than a new taxonomy nobody has time to learn.
- **Layered OWASP Top 10 for LLM Applications (2025) and MITRE ATLAS on top.** OWASP provides the AI risk categories; ATLAS provides the attacker's tactics. Every card carries all three mappings, so each finding ties to a recognised reference an auditor can check rather than an opinion.
- **Anchored the worked example in consumer credit decisioning.** A regulated use case forces the threats that generic examples skip: disparate impact under ECOA and Regulation B, high-risk obligations under the EU AI Act, and the need for a decision that can be defended to a regulator.
- **Named the gaps instead of hiding them.** Three cards, hallucination, misinformation, and bias, are marked as STRIDE gaps, because STRIDE has no category for confidently wrong output or for fairness. That gap is the entire argument for the overlay, and pretending STRIDE covers it would weaken the case.

## Deliverable

A complete, ready-to-run kit published under CC BY 4.0.

| Artifact | What it is |
|---|---|
| Facilitator Guide | The 2-hour run sheet: agenda, facilitator notes, common objections, after-action items. |
| Participant Worksheet | What each attendee fills in during the session, including a 5x5 likelihood by impact grid. |
| Threat Card Deck | 20 cards, one AI threat each, mapped to STRIDE, OWASP LLM, and MITRE ATLAS. |
| Output Template | The client-facing write-up produced after the workshop. |
| Worked Example | A full threat model for a fictional AI credit-decision assistant, scored and prioritized. |

The worked example runs a fictional lender's LLM-assisted credit assistant through the whole method: a 10-threat register scored on a 5x5 matrix, the top five controls with named owners and framework citations, and a 90-day, 6-month, and 12-month roadmap. Disparate impact scored highest at 20; unbounded consumption lowest at 4.

<!-- Capture these screenshots and drop them in /assets/images/ before publishing:
     ttm-deck-cover.png   - the card deck cover with the STRIDE color key
     ttm-card-front-back.png - one card front and back side by side (Indirect Prompt Injection reads well)
     ttm-threat-register.png - the scored threat register from the worked example
     ttm-risk-grid.png    - the RAG-coloured likelihood by impact grid from the worksheet -->

![Threat card deck cover and STRIDE colour key](/assets/images/ttm-deck-cover.png)
![A threat card, front and back](/assets/images/ttm-card-front-back.png)
![Worked example: scored threat register](/assets/images/ttm-threat-register.png)

## Reflection

Building the deck taught me more than reading the frameworks did. Writing 20 concrete scenarios forced a distinction that the source documents blur: which AI risks actually apply to a decision-support system, and which are theoretical for this design. It also confirmed something facilitators say but rarely justify, that a card deck drives better discussion than an open brainstorm. People react to a specific scenario faster than they recall one. The most useful design decision was the least obvious one: marking where STRIDE runs out. A candidate who maps every AI risk cleanly onto six categories from 1999 is either not looking hard enough or not being honest about it.

For v2, the first change is discipline, not features. Mapping the OWASP and ATLAS identifiers by hand showed how quickly both frameworks move, so the next version opens with a verification pass against the live matrices and a dated note on every mapping. After that: pilot the workshop with a real product team to earn a testimonial and pressure-test the timings, add sectoral overlays for financial services and healthcare where the control set diverges, and rebuild the deck in a proper design tool so it reads as a product rather than a document.
