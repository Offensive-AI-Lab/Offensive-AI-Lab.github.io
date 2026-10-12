---
title: GAVEL
short_title: GAVEL
subtitle: "Rule-based safety for LLMs — bringing signature-based cyber defense to AI."
description: "GAVEL brings rule-based, signature-style cyber defense to AI safety: robust, auditable rules that monitor an LLM's internal activations and block unsafe behavior without retraining the model. ICLR 2026 (Rank A*), presented at Black Hat USA 2026."
date: 2026-01-01 # used for ordering only (newest first)
image: /assets/images/gavel-hero.webp
hero_position: right center
thumb_position: 93% 50%
venues:
  - label: ICLR 2026
    note: Rank A*
    url: https://arxiv.org/pdf/2601.19768
  - label: Black Hat USA 2026
    url: https://blackhat.com/us-26/briefings/schedule/#rules-for-neural-traffic-a-new-defensive-layer-for-llms-53675
links:
  - label: Read the Paper
    url: https://arxiv.org/pdf/2601.19768
    icon: paper
  - label: Code
    url: https://github.com/Offensive-AI-Lab/gavel-rules
    icon: code
  - label: Watch the Talk
    url: "#talks"
    icon: video
authors:
  - Shir Rozenfeld
  - Rahul Pankajakshan
  - Itay Zloczower
  - Eyal Lenga
  - Gilad Gressel
  - Yisroel Mirsky
topics: [AI Safety, LLM Security, Activation Monitoring]
bibtex: |
  @inproceedings{rozenfeld2026gavel,
    title     = {{GAVEL}: Towards Rule-Based Safety Through Activation Monitoring},
    author    = {Rozenfeld, Shir and Pankajakshan, Rahul and Zloczower, Itay and Lenga, Eyal and Gressel, Gilad and Mirsky, Yisroel},
    booktitle = {International Conference on Learning Representations (ICLR)},
    year      = {2026}
  }
funding: erc
redirect_from: /projects/gavel/
---

## The Vision

For decades, the cybersecurity world has relied on **rules and signatures** — firewalls, antivirus, and intrusion detection systems that the community can write, share, and update the moment a new threat appears, without rebuilding the underlying system. We don't have this in AI safety. Today, keeping a model safe usually means retraining it or bolting on a black-box classifier that nobody can inspect, adjust, or trust.

**GAVEL brings rule-based, signature-style security from cyber into AI safety.** It is:

- **Robust** — rules operate on a model's internal *activations*, not the surface text it produces, so they can't be dodged by simply rewording a prompt.
- **Flexible** — safety rules can be written, tweaked, or removed on the fly, with **no retraining** of the model or its detectors.
- **Collaborative** — rules and the components they're built from are shareable, versionable, and auditable, so the community can pool threat intelligence the same way security researchers share signatures today.

## How It Works

<video class="rmedia" autoplay loop muted playsinline>
  <source src="{{ '/assets/videos/gavel-demo.mp4' | relative_url }}" type="video/mp4">
</video>

Think of it as a security camera for a model's mind. As the LLM processes a prompt and drafts a response, GAVEL taps into its internal activations and checks them against a set of rules:

<div class="rflow">
  <div class="rflow-step">Model activations</div>
  <span class="rflow-arrow">{% include research-icon.html name="arrow-right" %}</span>
  <div class="rflow-step">Cognitive Element probes<small>e.g. "making a threat", "payment processing"</small></div>
  <span class="rflow-arrow">{% include research-icon.html name="arrow-right" %}</span>
  <div class="rflow-step">Logical rule engine<small>e.g. IF threat AND payment THEN block</small></div>
  <span class="rflow-arrow">{% include research-icon.html name="arrow-right" %}</span>
  <div class="rflow-step">Remediation<small>Stop, Refuse, Disclose, Steer, ...</small></div>
</div>

1. **Cognitive Elements (CEs)** are small, interpretable concepts — like *"making a threat"* or *"processing a payment"* — each detected by a lightweight probe trained on the model's own internal activations.
2. **Rules** combine CEs with simple logic ("IF this CE AND NOT that CE, THEN flag") to capture nuanced, domain-specific behavior with much higher precision than a single end-to-end classifier.
3. Because CEs and rules are separate, modular pieces, anyone can compose a new rule from existing CEs — or contribute a new CE — without retraining anything.

**Rules and CEs are model-agnostic** — they describe *behaviors*, not any one model's internals, so the community can write, share, and reuse them freely across different LLMs. A rule only becomes *model-specific* the moment a model owner sets up their own GAVEL instance and trains CE probes on that particular model's activations to classify against it.

## What We Offer the Community

<div class="rfeatures">

  <div class="rfeature">
    <span class="rfeature-icon">{% include research-icon.html name="engine" %}</span>
    <h3>GAVEL</h3>
    <p>The open-source core engine: extract activations, train Cognitive Element probes, calibrate thresholds, and evaluate rule-based safety policies.</p>
    <a href="https://github.com/Offensive-AI-Lab/gavel-rules">github.com/Offensive-AI-Lab/gavel-rules →</a>
  </div>

  <div class="rfeature">
    <span class="rfeature-icon">{% include research-icon.html name="monitor" %}</span>
    <h3>GAVEL Studio</h3>
    <p>A web GUI for authoring rules in plain English, AI-assisted ("agentic") rule and CE generation, live monitoring, and one-click access to the community rule registry.</p>
    <a href="https://github.com/Offensive-AI-Lab/gavel-studio">github.com/Offensive-AI-Lab/gavel-studio →</a>
  </div>

  <div class="rfeature">
    <span class="rfeature-icon">{% include research-icon.html name="library" %}</span>
    <h3>Rule Registry</h3>
    <p>A public, community-contributed library of Cognitive Elements and rules — the AI-safety equivalent of a shared signature feed. Browse every rule, CE, and dataset in the live viewer.</p>
    <a href="{{ '/gavel/viewer/' | relative_url }}">Browse the library →</a>
    <span class="rbadge">Opens at launch</span>
  </div>

</div>

## Publications & Talks {#talks}

**[GAVEL: Towards Rule-Based Safety Through Activation Monitoring](https://arxiv.org/pdf/2601.19768)**<br>
Shir Rozenfeld, Rahul Pankajakshan, Itay Zloczower, Eyal Lenga, Gilad Gressel, Yisroel Mirsky. ICLR 2026. `Rank A*`

**[Rules for Neural Traffic: A New Defensive Layer for LLMs](https://blackhat.com/us-26/briefings/schedule/#rules-for-neural-traffic-a-new-defensive-layer-for-llms-53675)**<br>
Black Hat USA 2026 Briefing.

**[GAVEL: Rule-Based Security over LLM Activations](https://seclab.stanford.edu/RealWorldAIsec/)**<br>
Stanford University, Real World AI Security (USA 2026)

<div class="rvideo">
  <iframe src="https://www.youtube.com/embed/IUnmtDoyBvk" title="GAVEL talk by Yisroel Mirsky" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen loading="lazy"></iframe>
</div>

## Contributors

- **PI:** Yisroel Mirsky
- **Researchers:** Shir Rozenfeld, Rahul Pankajakshan, Gilad Gressel
- **Research Assistants:** Itay Zloczower, Eyal Lenga
- **GAVEL Studio (base):** Sean Shuhman, Ofek Avigezer, Shahaf Har-Tsvi, Shahar Navian

## Get Involved

GAVEL is built to grow with its community. Explore the code, try GAVEL Studio, or reach out if you'd like to contribute a rule, a Cognitive Element, or an integration. Join the discussion in the **#gavel-community** channel on our Discord:

<p align="center"><iframe src="https://discord.com/widget?id=1013392970290045011&theme=dark" width="350" height="500" allowtransparency="true" frameborder="0" sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"></iframe></p>

<p align="center">
  <a href="https://github.com/Offensive-AI-Lab">Offensive AI Lab on GitHub</a> &middot; <a href="{{ '/contact/' | relative_url }}">Contact Us</a>
</p>
