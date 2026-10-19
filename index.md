---
#
# By default, content added below the "---" mark will appear in the home page
# between the top bar and the list of recent posts.
# To change the home page layout, edit the _layouts/home.html file.
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: home
title: "Offensive AI & LLM Security Research"
description: "Offensive AI Lab at Ben-Gurion University researches AI-powered cyberattacks, AI agent security, prompt injection, adversarial machine learning, and LLM safety."
---

<svg id="d3banner"></svg>
{% include datavis_d3banner.html %}



**`Offensive AI`** is the malicious use of artificial intelligence to power, automate, and scale cyberattacks, as well as attacks targeting AI systems themselves. It includes autonomous attack agents, AI-driven vulnerability discovery and exploitation, adaptive malware, deepfakes, and automated social engineering, alongside attacks on AI models and agents through prompt injection, adversarial machine learning, data poisoning, agent hijacking, tool misuse, and supply chain compromise.

The `Offensive AI Lab` (OAI Lab) studies how adversaries use AI to enhance their attacks and exploit AI systems. The objective of the lab is to protect society by improving AI safety and by identifying and mitigating AI threats before they become mainstream. We are located in the BGU Cyber Security Research Center in Be'er Sheva Israel.

## Featured Research

<p class="rhome-lead">Dedicated pages for selected projects from the lab, with papers, code, talks, and tools.</p>

{% include research-tiles.html show_all=true %}

## Our Supporters

<p class="supporters-lead">The lab is supported by the Zuckerman STEM Leadership Program and by research grants from the organizations below. Thank you for your support!</p>

<div class="logo-wall">
  <span class="logo-tile logo-feature"><img src="{{ '/assets/logos/erc.png' | relative_url }}" alt="European Research Council (ERC)" loading="lazy"></span>
  <span class="logo-tile logo-wide"><img class="logo-boost" src="{{ '/assets/logos/zuckerman.png' | relative_url }}" alt="Zuckerman STEM Leadership Program" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/MS.png' | relative_url }}" alt="Microsoft" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/H2020.png' | relative_url }}" alt="Horizon 2020, European Commission" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/DoE.png' | relative_url }}" alt="U.S. Department of Energy" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/MoE.png' | relative_url }}" alt="Israel Ministry of Energy" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/IIA.png' | relative_url }}" alt="Israel Innovation Authority" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/bird.png' | relative_url }}" alt="BIRD Foundation" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/CyberDir.png' | relative_url }}" alt="Israel National Cyber Directorate" loading="lazy"></span>
  <span class="logo-tile"><img src="{{ '/assets/logos/cclp.png' | relative_url }}" alt="CCLP" loading="lazy"></span>
  <span class="logo-tile"><img class="logo-boost" src="{{ '/assets/logos/MOST.png' | relative_url }}" alt="Israel Ministry of Innovation, Science and Technology" loading="lazy"></span>
</div>

## Join Our Community

{% include discord-banner.html %}
