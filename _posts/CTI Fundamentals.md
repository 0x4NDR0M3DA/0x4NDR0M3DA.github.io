| title  | time |  categories | tags | 
|-------|-----|--------------|-----|
| Test | 2026-01-17 05:00  | derp | cti |

**Relevance of CTI** - align the relevance of intelligence to our scope in organization. 

**Timeliness** - swift CTI communication to relevant parties, such as SOC or Threat Hunters. Old intelligence is not worth it - it diminishes with time.

**Actionability** - intelligence must be actionable - we must know what we need to do with the intel provided. **It must yield relevance, timeliness and actionable insights**.

**Accuracy** - correct indicators, proper attributions, correct TTPs. Providing flawed or incorrect data is waste of time. They must have **confidence indicator.**

```
- Gain insights into potential adversary operations and campaigns that might be targeting our organization.
- Enrich our data pool through analysis by CTI analysts and other network defenders.
- Uncover adversary TTPs, enabling the development of effective mitigation measures and enhancing our understanding of adversary behavior.
- Provide decision-makers within our organization with pertinent information for informed, impactful decision-making related to business operations.
```

![[Pasted image 20250128203532.png]]

--------
# Levels of CTI

- **Strategic Intelligence**
- **Operational Intelligence**
- **Tactical Intelligence**

![[Pasted image 20250128203621.png]]
# Strategic Intelligence

- Consumed by C-level executives, VPs and senior management.
- Align company risks.
- Overview of adversaries.
- Mapping TTPs.
- **Who? and Why?**
```
A report containing strategic intelligence might outline the threat posed by APT28 (also known as Fancy Bear), a nation-state actor linked to the Russian government. This report could cover the group's past campaigns, its motivations (such as political espionage), targets (like governments, military, and security organizations), and long-term strategies. The report might also explore how the group adapts its tactics and tools over time, based on historical data and the geopolitical context.
```

# Operational Intelligence

- Mapping TTPs.
- Information on adversary campaigns.
- More details than in strategic reporting.
- Produced for mid-level management.
- **How and Where?**
```
A report containing operational intelligence can provide detailed analysis of a ransomware campaign conducted by the REvil group. It would include how the group gains initial access (like through phishing or exploiting vulnerabilities), its lateral movement tactics (such as credential dumping and exploiting Windows admin tools), and its methods of executing the ransomware payload (maybe after hours to maximize damage and encrypt as many systems as possible).
```

# Tactical Intelligence

- Delivering immediate, actionable information for operational level.
- Technical details on attacks.

```
A report containing tactical intelligence could include specific IP addresses, URLs, or domains linked to the REvil command and control servers, hashes of known REvil ransomware samples, specific file paths, registry keys, or mutexes associated with REvil, or even distinctive strings within the ransomware code. This type of information can be directly used by security technologies and incident responders to detect, prevent, and respond to specific threats.
```

-----
### How To Go Through A Tactical Threat Intelligence Report

- **Get the idea of the narrative** - for example a report that affects businesses in our sector. Macro level insights about the objectives - we can assess the relevance to our organization.
- **Spotting and classifying IOCs.**
- **Comprehending the Attack's Lifecycle** - TTPs to forecast the attacker's moves.
- **Analysis and Validation of IOCs** - cross - reference the IOCs in various sources. Check if they are old or new. Check accuracy - IP pointing to CDN or cloud provider?
- **Import IOCs to our detection infrastructure.**
- **Proactive Threat Hunting** - we can form a threat hunt from the relevant reporting. Prepare, form hypothesis, assess tooling and log sources, perform data collection and analysis and refine hypothesis.
