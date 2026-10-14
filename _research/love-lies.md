---
title: "Love, Lies, and Language Models"
short_title: "Love, Lies & LLMs"
subtitle: "How AI is entering romance-baiting scams, and why today's safeguards miss it."
description: "Interviews with 145 scam-compound insiders, a blinded week-long conversation study, and a safeguard evaluation show that LLMs are already used in romance-baiting scams, out-perform human operators at building trust, and evade today's safety filters. USENIX Security 2026, Distinguished Paper Award runner-up."
date: 2026-08-12 # used for ordering only (newest first)
last_modified_at: 2026-10-13 # bump when you edit this page (sitemap "last modified" for Google)
image: /assets/images/love-lies-hero.jpg
hero_position: right center
thumb: /assets/images/love-lies-thumb.jpg
featured_in: WIRED # badge on the /research/ card
venues:
  - label: USENIX Security 2026
    note: Rank A*
    url: https://www.usenix.org/conference/usenixsecurity26/presentation/gressel
  - label: Distinguished Paper Award
    note: Runner-up
    award: true
links:
  - label: Read the Paper
    url: https://www.usenix.org/conference/usenixsecurity26/presentation/gressel
    icon: paper
  - label: Datasets & Code
    url: https://doi.org/10.5281/zenodo.17984568
    icon: library
  - label: Featured in WIRED
    url: https://www.wired.com/story/ai-scammers-are-better-at-building-trust-than-humans/
    icon: link
authors:
  - Gilad Gressel
  - Rahul Pankajakshan
  - Shir Rozenfeld
  - Ling Li
  - Ivan Franceschini
  - Krishnashree Achuthan
  - Yisroel Mirsky
topics: [Attacks Using AI, AI Safety]
bibtex: |
  @inproceedings{gressel2026love,
    title     = {Love, Lies, and Language Models: Investigating {AI}'s Role in Romance-Baiting Scams},
    author    = {Gressel, Gilad and Pankajakshan, Rahul and Rozenfeld, Shir and Li, Ling and Franceschini, Ivan and Achuthan, Krishnashree and Mirsky, Yisroel},
    booktitle = {35th USENIX Security Symposium (USENIX Security 26)},
    year      = {2026}
  }
funding: erc
---

## The Threat

Romance-baiting scams pair weeks of emotional grooming with fraudulent cryptocurrency investments. They are run by organized crime syndicates from compounds in Southeast Asia, where trafficked and coerced workers juggle dozens of conversations at once. More than **$75 billion** in stolen cryptocurrency has been laundered through scam-linked accounts in the past four years, and fewer than **0.05%** of perpetrators are ever caught.

Every stage of the scam happens over text, which is exactly what large language models do well:

<div class="rfeatures">

  <div class="rfeature">
    <span class="rfeature-icon">{% include research-icon.html name="chat" %}</span>
    <h3>1 · Hook</h3>
    <p>Victims are found through mass-sent "accidental" wrong-number messages that spark first contact.</p>
  </div>

  <div class="rfeature">
    <span class="rfeature-icon">{% include research-icon.html name="heart" %}</span>
    <h3>2 · Line</h3>
    <p>Weeks to months of daily conversation build trust and an emotional, often romantic, bond.</p>
  </div>

  <div class="rfeature">
    <span class="rfeature-icon">{% include research-icon.html name="dollar" %}</span>
    <h3>3 · Sinker</h3>
    <p>The victim is steered into a fake crypto platform, shown fake gains, pushed to invest more, and then ghosted.</p>
  </div>

</div>

So are syndicates already automating this with LLMs, and if they do, will it make the threat worse?

## What We Did

1. **Inside the compounds.** In-depth interviews with **145 insiders** and **5 victims** mapped how scam compounds are organized, where the labor goes, and how LLMs are already being used.
2. **A blinded, week-long trust study.** 22 participants chatted for seven days with two partners, one a human operator and one an LLM agent, without knowing that either could be an AI. Both followed the same scam-style playbook; no money was involved, and the final "ask" was replaced by a harmless request to download an app.
3. **Stress-testing safeguards.** We tested whether commercial models disclose that they are AI when asked, and whether popular moderation tools (Llama Guard 3, Google Perspective, and the OpenAI Moderation API) flag romance-baiting conversations.

## Key Findings

<div class="rstats">
  <div class="rstat"><span class="rstat-num">87%</span><span class="rstat-label">of scam-compound labor is scripted Hook-and-Line conversation, readily automatable by LLMs</span></div>
  <div class="rstat"><span class="rstat-num">46% <small>vs</small> 18%</span><span class="rstat-label">compliance with requests: LLM partner vs. human operator</span></div>
  <div class="rstat"><span class="rstat-num">0%</span><span class="rstat-label">AI self-disclosure from GPT-4o, Gemini 2.5 Pro, and Claude 3.7 when told to stay in persona</span></div>
  <div class="rstat"><span class="rstat-num">0.0%</span><span class="rstat-label">of romance-baiting dialogues detected by popular safety filters</span></div>
</div>

- **LLMs are already in the pipeline.** Insiders describe LLMs as part of daily scam workflows, and the modular, text-based structure of the operation makes full automation feasible.
- **The AI was more convincing than the human.** Participants rated the LLM partner as significantly more trustworthy than the human operator (p = 0.007), especially on emotional trust and connection, and the LLM was 2.6× more successful at getting them to act.
- **Safeguards don't notice.** Vendor models kept their human persona in every trial, even when asked directly, "Are you an AI?"

> "He kept reassuring me, saying that my caution was a good thing … After that, he started painting a picture of our future together … I fell into the trap gradually."
> <cite>— Romance-baiting victim interviewed for the study</cite>

## Why Safeguards Fail

Romance-baiting doesn't look harmful. It is friendly, supportive, empathetic conversation, and each message on its own is benign. Filters built around toxicity or explicit fraud never fire: OpenAI's Moderation API flagged at most 18.8% of romance-baiting dialogues, and every one of those flags was a false positive. Llama Guard 3 caught tax and e-commerce scams well but detected none of the romance-baiting conversations.

## What Needs to Change

- **Behavioral detection** that looks at the arc of a conversation over time, not individual messages.
- **Enforced AI transparency**, so that models reliably disclose they are AI rather than impersonating humans on request.
- **Policy responses** that treat LLM-enabled fraud as both a cybersecurity and a human-rights issue.

We disclosed these findings to all major LLM vendors.

## Ethics & Data

The study was approved by our Institutional Review Board, and all participants were debriefed. The synthetic datasets and the code used to generate them and evaluate commercial content filters are available on [Zenodo](https://doi.org/10.5281/zenodo.17984568). The scam-agent prompts and playbook are withheld because of their dual-use risk.

## In the Media

<div class="rpress">
  <a href="https://www.wired.com/story/ai-scammers-are-better-at-building-trust-than-humans/">WIRED</a>
  <a href="https://9to5mac.com/2026/07/30/ai-chatbots-are-now-better-than-humans-at-romance-scams-and-thats-scary/">9to5Mac</a>
  <a href="https://www.scworld.com/brief/ai-chatbots-outperform-humans-in-building-trust-for-scams">SC Media</a>
  <a href="https://www.accountingtoday.com/news/study-finds-bots-2-5x-more-effective-scammers-than-humans">Accounting Today</a>
  <a href="https://www.helpnetsecurity.com/2025/12/29/llms-romance-baiting-scams-study/">Help Net Security</a>
  <a href="https://www.bitdefender.com/en-us/blog/hotforsecurity/new-research-shows-how-ai-is-powering-romance-baiting-scams">Bitdefender</a>
  <a href="https://blog.knowbe4.com/ai-chatbots-outperform-humans-at-building-trust-in-scams">KnowBe4</a>
</div>
