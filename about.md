---
layout: page
title: About
permalink: /about/
---

## What is Offensive AI?

`Offensive AI` is the malicious use of artificial intelligence to power, automate, and scale cyberattacks, as well as attacks that target AI systems themselves. It takes two forms:

- **Attacks using AI:** AI makes the attacker faster, cheaper, and more convincing, from automated reconnaissance, intrusion, and vulnerability discovery to adaptive malware, deepfakes, and social engineering at scale.
- **Attacks against AI:** the adversary exploits the AI that people and organizations rely on, through prompt injection, agent hijacking, jailbreaks, data poisoning, model theft, and adversarial examples that evade AI-based defenses.

## From Prediction to Reality

When we founded the lab in 2020, offensive AI was largely a prediction, with a handful of early incidents such as the poisoning of Microsoft's Tay chatbot[^tay] and adversarial evasion of an AI-based antivirus.[^cylance] Since then, large language models (LLMs) and AI agents have made it part of the everyday threat landscape:

- **Deepfakes and impersonation.** In 2024, a finance worker at the engineering firm Arup transferred about $25 million after a video call in which every other participant was a deepfake of the company's executives.[^arup] In 2025, the FBI warned of an ongoing campaign using AI-generated voice messages to impersonate senior US officials.[^fbi]
- **AI in the attacker's toolkit.** Microsoft and OpenAI reported state-affiliated groups from Russia, North Korea, Iran, and China using LLMs to support their operations,[^msft] and Google has since found malware that queries an LLM while it runs to rewrite itself and evade detection.[^gtig]
- **AI agents carrying out attacks.** In 2025, Anthropic reported a criminal using its Claude Code agent to automate a data-theft and extortion campaign against at least 17 organizations.[^vibe] Months later, it disrupted what it called the first reported AI-orchestrated cyber-espionage campaign, attributed to a state-sponsored group, in which AI performed 80–90% of the work.[^espionage]
- **Fraud at scale.** Our own interviews with 145 scam-compound insiders found that LLMs are already used in romance-baiting scams, and in a blinded study an LLM agent out-performed human scammers at building trust.[^lovelies]
- **Attacks on AI systems.** As LLMs become agents with access to email, files, and tools, prompt injection is ranked the top risk for LLM applications.[^owasp] In 2025, researchers disclosed EchoLeak, a since-patched zero-click prompt injection that could make Microsoft 365 Copilot leak internal data through a single email.[^echoleak]

## Are We Prepared?

Security agencies expect the threat to keep growing. In its 2024 assessment, the UK's National Cyber Security Centre concluded:

> "Artificial intelligence (AI) will almost certainly increase the volume and heighten the impact of cyber attacks over the next two years."[^ncsc]

Defenses are struggling to keep up. Our recent work shows that popular safety filters miss AI-driven romance scams,[^lovelies] that AI agents can be hijacked through the content they read,[^kya] and that LLMs reviewing code can be fooled into misreading what it does.[^trustme] To counter offensive AI, we need to anticipate the adversary's next move and build countermeasures before new attacks become mainstream, rather than racing to patch them afterward.

## Our Lab

![image]({{site.baseurl}}/assets/images/gavyam.jpg){: style="float: left; margin-right:10px" width="300px"}

The `Offensive AI Research Lab` was founded in 2020 at Ben-Gurion University of the Negev with the goal of producing research that helps the world prepare for offensive AI. Instead of just "patching" the problem, we work on ways to give defenders the upper hand by putting the adversary at a disadvantage.

Today our research spans AI agent security, LLM safety and monitoring, AI-driven fraud and deepfakes, and adversarial machine learning. Our work appears at top venues such as USENIX Security, NDSS, ICLR, EMNLP, and ACSAC, has been presented at Black Hat and DEF CON, and has been covered by outlets including WIRED and The Washington Post. In 2025, the lab was awarded an ERC Starting Grant (AGI-Safety). Explore our [featured research]({{site.baseurl}}/research/) and full list of [publications]({{site.baseurl}}/publications/).

We are a friendly group of researchers and hackers with a passion for AI and cyber security. We strongly believe that AI should never be used to cause physical, financial, or psychological harm. However, cyber criminals do not hold by the same code of ethics. It is therefore our mission to identify, counter, and mitigate the threat of offensive AI to help protect society.

## Join Us!

We are currently seeking excellent students and post-docs who are eager to research offensive AI. Whether you are drawn to AI agent security, LLM safety, deepfakes, or breaking machine learning models, we would love to work with you! You can make a difference in the world, and we'd be honored to make that difference with you. Generous stipends are available for suitable candidates.

If you are interested in joining or have any questions, please reach out to Dr. Mirsky by email: {% include email.html %}

#### References

[^tay]: Microsoft, ["Learning from Tay's introduction"](https://blogs.microsoft.com/blog/2016/03/25/learning-tays-introduction/), March 2016.
[^cylance]: Skylight Cyber, ["Cylance, I Kill You!"](https://skylightcyber.com/2019/07/18/cylance-i-kill-you/), July 2019.
[^arup]: CNN, ["British engineering giant Arup revealed as $25 million deepfake scam victim"](https://edition.cnn.com/2024/05/16/tech/arup-deepfake-scam-loss-hong-kong-intl-hnk), May 2024.
[^fbi]: FBI IC3, ["Senior US Officials Impersonated in Malicious Messaging Campaign"](https://www.ic3.gov/PSA/2025/PSA250515), Public Service Announcement I-051525-PSA, May 2025.
[^msft]: Microsoft Threat Intelligence, ["Staying ahead of threat actors in the age of AI"](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/), February 2024.
[^gtig]: Google Threat Intelligence Group, ["GTIG AI Threat Tracker: Advances in Threat Actor Usage of AI Tools"](https://cloud.google.com/blog/topics/threat-intelligence/threat-actor-usage-of-ai-tools), November 2025.
[^vibe]: Anthropic, ["Detecting and countering misuse of AI: August 2025"](https://www.anthropic.com/news/detecting-countering-misuse-aug-2025), August 2025.
[^espionage]: Anthropic, ["Disrupting the first reported AI-orchestrated cyber espionage campaign"](https://www.anthropic.com/news/disrupting-AI-espionage), November 2025.
[^lovelies]: Gressel et al., ["Love, Lies, and Language Models: Investigating AI's Role in Romance-Baiting Scams"]({{site.baseurl}}/research/love-lies/), USENIX Security 2026.
[^owasp]: OWASP Gen AI Security Project, ["LLM01:2025 Prompt Injection"](https://genai.owasp.org/llmrisk/llm01-prompt-injection/), OWASP Top 10 for LLM Applications 2025.
[^echoleak]: Reddy and Gujral, ["EchoLeak: The First Real-World Zero-Click Prompt Injection Exploit in a Production LLM System"](https://arxiv.org/abs/2509.10540), 2025 (CVE-2025-32711).
[^ncsc]: UK National Cyber Security Centre, ["The near-term impact of AI on the cyber threat"](https://www.ncsc.gov.uk/report/impact-of-ai-on-cyber-threat), January 2024.
[^kya]: Eliav et al., ["Know Your Agent: Reconnaissance-Driven Pentesting of AI Agents"]({{site.baseurl}}/research/know-your-agent/), ACSAC 2026.
[^trustme]: Bernstein et al., ["Trust Me, I Know This Function: Hijacking LLM Static Analysis using Bias"]({{site.baseurl}}/research/trust-me/), NDSS 2026.
