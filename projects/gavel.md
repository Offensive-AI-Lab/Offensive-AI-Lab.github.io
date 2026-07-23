---
layout: default
title: GAVEL
permalink: /projects/gavel/
---

<div style="position:relative; width:100vw; margin-left:calc(-50vw + 50%); margin-right:calc(-50vw + 50%); height:clamp(280px, 38vw, 480px); background-image:url('{{site.baseurl}}/assets/images/gavel-hero.webp'); background-size:cover; background-position:right center; display:flex; align-items:center; overflow:hidden;">
  <div style="position:absolute; inset:0; background:linear-gradient(90deg, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0.7) 30%, rgba(0,0,0,0.35) 55%, rgba(0,0,0,0.05) 75%);"></div>
  <div style="position:relative; z-index:1; padding: 0 clamp(20px, 6vw, 70px); max-width: 620px; text-shadow: 0 2px 10px rgba(0,0,0,0.85);">
    <h1 style="margin:0 0 10px 0; font-size:clamp(2em, 5vw, 3.2em); letter-spacing:1px;">GAVEL</h1>
    <p style="margin:0 0 18px 0; font-style:italic; opacity:0.9; font-size:clamp(0.9em, 2vw, 1.1em);">Rule-based safety for LLMs — bringing signature-based cyber defense to AI.</p>
    <p style="margin:0;">
      <a href="https://arxiv.org/pdf/2601.19768" style="text-decoration:none;">
        <span style="display:inline-block; margin:4px 4px 4px 0; padding:6px 14px; border:1px solid rgba(255,255,255,0.35); border-radius:16px; font-size:0.85em; white-space:nowrap; background:rgba(0,0,0,0.25);">📄 ICLR 2026 &middot; Rank A*</span>
      </a>
      <a href="https://blackhat.com/us-26/briefings/schedule/#rules-for-neural-traffic-a-new-defensive-layer-for-llms-53675" style="text-decoration:none;">
        <span style="display:inline-block; margin:4px; padding:6px 14px; border:1px solid rgba(255,255,255,0.35); border-radius:16px; font-size:0.85em; white-space:nowrap; background:rgba(0,0,0,0.25);">🎤 Black Hat USA 2026</span>
      </a>
      <a href="https://github.com/Offensive-AI-Lab/gavel" style="text-decoration:none;">
        <span style="display:inline-block; margin:4px; padding:6px 14px; border:1px solid rgba(255,255,255,0.35); border-radius:16px; font-size:0.85em; white-space:nowrap; background:rgba(0,0,0,0.25);">💻 Open Source</span>
      </a>
    </p>
  </div>
</div>

<p>&nbsp;</p>

## The Vision

For decades, the cybersecurity world has relied on **rules and signatures** — firewalls, antivirus, and intrusion detection systems that the community can write, share, and update the moment a new threat appears, without rebuilding the underlying system. We don't have this in AI safety. Today, keeping a model safe usually means retraining it or bolting on a black-box classifier that nobody can inspect, adjust, or trust.

**GAVEL brings rule-based, signature-style security from cyber into AI safety.** It is:

- **Robust** — rules operate on a model's internal *activations*, not the surface text it produces, so they can't be dodged by simply rewording a prompt.
- **Flexible** — safety rules can be written, tweaked, or removed on the fly, with **no retraining** of the model or its detectors.
- **Collaborative** — rules and the components they're built from are shareable, versionable, and auditable, so the community can pool threat intelligence the same way security researchers share signatures today.

<p>&nbsp;</p>

## How It Works

<p align="center">
  <video autoplay loop muted playsinline style="max-width:100%; width:700px; border-radius:8px;">
    <source src="{{site.baseurl}}/assets/videos/gavel-demo.mp4" type="video/mp4">
  </video>
</p>

Think of it as a security camera for a model's mind. As the LLM processes a prompt and drafts a response, GAVEL taps into its internal activations and checks them against a set of rules:

<p align="center" style="margin: 25px 0;">
  <span style="display:inline-flex; flex-wrap:wrap; align-items:center; justify-content:center; gap:8px; font-size:0.95em;">
    <span style="padding:10px 14px; border:1px solid rgba(255,255,255,0.25); border-radius:6px;">Model activations</span>
    <span>→</span>
    <span style="padding:10px 14px; border:1px solid rgba(255,255,255,0.25); border-radius:6px;">Cognitive Element probes<br><small style="opacity:0.7;">e.g. "making a threat", "payment processing"</small></span>
    <span>→</span>
    <span style="padding:10px 14px; border:1px solid rgba(255,255,255,0.25); border-radius:6px;">Logical rule engine<br><small style="opacity:0.7;">e.g. IF threat AND payment THEN block</small></span>
    <span>→</span>
    <span style="padding:10px 14px; border:1px solid rgba(255,255,255,0.25); border-radius:6px;">Remediation<br><small style="opacity:0.7;">Stop, Refuse, Disclose, Steer, ...</small></span>
  </span>
</p>

1. **Cognitive Elements (CEs)** are small, interpretable concepts — like *"making a threat"* or *"processing a payment"* — each detected by a lightweight probe trained on the model's own internal activations.
2. **Rules** combine CEs with simple logic ("IF this CE AND NOT that CE, THEN flag") to capture nuanced, domain-specific behavior with much higher precision than a single end-to-end classifier.
3. Because CEs and rules are separate, modular pieces, anyone can compose a new rule from existing CEs — or contribute a new CE — without retraining anything.

**Rules and CEs are model-agnostic** — they describe *behaviors*, not any one model's internals, so the community can write, share, and reuse them freely across different LLMs. A rule only becomes *model-specific* the moment a model owner sets up their own GAVEL instance and trains CE probes on that particular model's activations to classify against it.

<p>&nbsp;</p>

## What We Offer the Community

<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 20px; margin: 20px 0;">

  <div style="flex: 1 1 280px; max-width: 320px; padding: 20px; border: 1px solid rgba(255,255,255,0.2); border-radius: 10px;">
    <h3 style="margin-top:0;">⚙️ GAVEL</h3>
    <p style="opacity:0.85; font-size:0.95em;">The open-source core engine: extract activations, train Cognitive Element probes, calibrate thresholds, and evaluate rule-based safety policies.</p>
    <a href="https://github.com/Offensive-AI-Lab/gavel">github.com/Offensive-AI-Lab/gavel →</a>
  </div>

  <div style="flex: 1 1 280px; max-width: 320px; padding: 20px; border: 1px solid rgba(255,255,255,0.2); border-radius: 10px;">
    <h3 style="margin-top:0;">🖥️ GAVEL Studio</h3>
    <p style="opacity:0.85; font-size:0.95em;">A web GUI for authoring rules in plain English, AI-assisted ("agentic") rule and CE generation, live monitoring, and one-click access to the community rule registry.</p>
    <a href="https://github.com/Offensive-AI-Lab/gavel-studio-v2.0">github.com/Offensive-AI-Lab/gavel-studio-v2.0 →</a>
  </div>

  <div style="flex: 1 1 280px; max-width: 320px; padding: 20px; border: 1px solid rgba(255,255,255,0.2); border-radius: 10px;">
    <h3 style="margin-top:0;">📚 Rule Registry</h3>
    <p style="opacity:0.85; font-size:0.95em;">A public, community-contributed library of Cognitive Elements and rules — the AI-safety equivalent of a shared signature feed. Browse every rule, CE, and dataset in the live viewer.</p>
    <a href="{{site.baseurl}}/gavel/viewer/">Browse the library →</a>
    <span style="display:inline-block; margin-left:8px; padding: 3px 10px; border:1px solid rgba(255,255,255,0.3); border-radius:12px; font-size:0.8em;">Opens at launch</span>
  </div>

</div>

<p>&nbsp;</p>

## Publications & Talks

**[GAVEL: Towards Rule-Based Safety Through Activation Monitoring](https://arxiv.org/pdf/2601.19768)**<br>
Shir Rozenfeld, Rahul Pankajakshan, Itay Zloczower, Eyal Lenga, Gilad Gressel, Yisroel Mirsky. ICLR 2026. `Rank A*`

**[Rules for Neural Traffic: A New Defensive Layer for LLMs](https://blackhat.com/us-26/briefings/schedule/#rules-for-neural-traffic-a-new-defensive-layer-for-llms-53675)**<br>
Black Hat USA 2026 Briefing.

**[GAVEL: Rule-Based Security over LLM Activations](https://seclab.stanford.edu/RealWorldAIsec/)**<br>
Stanford University, Real World AI Security (USA 2026)

<p align="center" style="margin: 20px 0;">
  <iframe width="700" height="394" src="https://www.youtube.com/embed/IUnmtDoyBvk" title="Yisroel Mirsky" style="max-width:100%;" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</p>

<p>&nbsp;</p>

## Contributors

- **PI:** Yisroel Mirsky
- **Researchers:** Shir Rozenfeld, Rahul Pankajakshan, Gilad Gressel
- **Research Assistants:** Itay Zloczower, Eyal Lenga
- **GAVEL Studio (base):** Sean Shuhman, Ofek Avigezer, Shahaf Har-Tsvi, Shahar Navian

<p>&nbsp;</p>

## Get Involved

GAVEL is built to grow with its community. Explore the code, try GAVEL Studio, or reach out if you'd like to contribute a rule, a Cognitive Element, or an integration.

<p align="center">
  <a href="https://github.com/Offensive-AI-Lab">Offensive AI Lab on GitHub</a> &middot; <a href="{{site.baseurl}}/contact/">Contact Us</a>
</p>

<p>&nbsp;</p>

<hr>

<p align="center" style="margin-top:20px;">
  <img src="{{site.baseurl}}/assets/logos/erc.png" alt="Funded by the European Union - ERC" width="300">
</p>

<p align="center" style="font-size:0.9em; opacity:0.85;">
  Funded by the European Union, ERC Starting Grant AGI-Safety (GA 101222135)
</p>

<p align="center" style="font-size:0.75em; opacity:0.6; max-width:650px; margin-left:auto; margin-right:auto;">
  Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or the European Research Council Executive Agency. Neither the European Union nor the granting authority can be held responsible for them.
</p>
