+++
date = "2025-10-30T09:08:14+09:00"
publishDate = "2025-10-30T09:08:14+09:00"
type = "out-article"
title = "Why Safety During Manual Driving Matters More Than During Autonomous Driving"
slug = "why-l0-more-important-than-l2"
lang = "en"
draft = false
tags = ["ADAS", "Autonomous-Driving", "Level-3", "Traffic-Safety", "Automotive-Technology"]
categories = ["technology", "adas"]
description = "ADAS automation isn't just about self-driving cars. Explore why the value of autonomous driving depends on what, how, and why we automate."
+++

## The ADAS Paradox ― "Essense" Beyond Automation

It has been over five years since autonomous driving became a hot topic. Autonomous taxi trials are underway in various countries, advanced driver assistance on highways continues to evolve, and news outlets increasingly report that "the era of autonomous driving is near."

However, I'd like to revisit a crucial question:  
**Do we really want "autonomous driving"?**

- If your car could drive itself, how much would you be willing to pay for it?
- If that autonomous driving were overly cautious, prioritizing safety above all, or frequently required manual intervention, would you still want to use it?

The truth is, the value of "automation" varies greatly depending on **what is automated, to what extent, and for what purpose**.  
And regardless of the level of automation, we cannot avoid the challenges of cost and responsibility allocation.

In this article, as an engineer with eight years of experience in ADAS development, I'll explore from a field perspective why improving the safety of "Level 0 (manual driving)" is crucial for society as a whole.

---

## SAE Automation Level Framework

First, let's briefly review the automation levels based on the international standard **SAE J3016**.

| Level | Name | Description |
|:--|:--|:--|
| Level 0 | No Driving Automation | Driver performs all tasks. May include warnings and momentary interventions. |
| Level 1 | Driver Assistance | Assists with either steering OR acceleration/deceleration. Example: ACC. |
| Level 2 | Partial Driving Automation | Controls both, but driver retains monitoring responsibility. |
| Level 3 | Conditional Driving Automation | System performs all tasks under specific conditions. Human intervenes when requested. |
| Level 4 | High Driving Automation | Full automation under specific conditions (no human intervention required). |
| Level 5 | Full Driving Automation | System drives under all conditions. Steering wheel unnecessary. |

Reference: [SAE J3016 Automated Driving Levels](https://www.sae.org/standards/content/j3016_202104/)

Critically, **responsibility first shifts to the system at Level 3**.  
This boundary dramatically increases the difficulty across development, regulation, and social acceptance.

---

## Reality: Technical and Institutional Barriers Facing Level 3

### 1. ODD (Operational Design Domain) Constraints

Level 3 systems must strictly define "under what conditions they function (ODD)".  
Outside this domain, the system cannot guarantee safety.

For example, conditions like "highway only," "low-speed only," or "good weather" are set to clearly define the range where safety can be reliably ensured.

However, since real-world traffic conditions change frequently, **designing and managing ODD boundaries becomes the most challenging issue**.

### 2. Legal and Social Challenges

Autonomous driving legislation varies by country and region, with most nations having laws premised on "human driving."

Since Level 3 places responsibility on the manufacturer during system operation, careful institutional design is required for legal liability in accidents, take-over design, and risk mitigation when drivers don't intervene.

### 3. Cost and Scalability

Level 3 systems combining high-reliability sensors, redundant control ECUs, and high-precision maps incur **additional costs of hundreds of thousands of yen per vehicle**.

Consequently, deployment in mass-production vehicles remains limited, and cost recovery is challenging.

In contrast, Level 0-2 driver assistance technologies can be widely deployed, offering **high cost-effectiveness from a societal safety improvement perspective**.

---

## Level 0 Safety Is Also Steadily Evolving

Recent "Level 0" technologies—**safety assistance functions premised on driver responsibility**—have been steadily advancing.

### AEB (Automatic Emergency Braking)

- Detection of pedestrians and cyclists, nighttime capability
- Collision avoidance assistance at intersections during turns
- Early warnings linked with DMS (Driver Monitoring Systems)

These advances have led to approximately **50% reduction in frontal collision accidents**, according to US IIHS research.

### Lane Keep Assist / Blind Spot Detection / Cross Traffic Alert

- Prevention of lane departure, side collisions, and intersection accidents
- Automatic intervention during drowsiness or distraction via DMS integration
- Detection of approaching vehicles when exiting, and other safety measures rooted in daily scenarios

These features are already becoming standard equipment in many new vehicles.

---

## Global Regulatory Trends

- **EU GSR (General Safety Regulation) Phase 2**: Mandates AEB, LKA, DMS, etc. from 2024
- **China C-NCAP 2024**: Introduces pedestrian/cyclist detection AEB and DMS evaluation
- **US NHTSA Proposal**: Phased mandatory AEB implementation for all vehicles by 2029

These trends demonstrate that **"safety technology in every vehicle"** has become an international consensus.

---

## Reflections from Nine Years in Development

Early in my career, I held a strong aspiration for achieving "fully autonomous driving."  
However, working in mass production development revealed realities such as:

- "Automation doesn't necessarily mean safety": It can create new risks like driver overreliance and reduced attention
- Rather than technical sophistication, "safety technology accessible to everyone" has greater societal impact

Ultimately, I realized the obvious truth: **saving as many lives as possible comes from the steady accumulation of modest, solid technology**.

---

## Manual Driving Safety Is What Changes Society

While "autonomous driving" is an attractive concept, from the perspective of reducing accidents across society, **Level 0-2 safety technologies** are currently delivering the greatest impact.

| Comparison Axis | Level 0~2 | Level 3 |
|:---|:---|:---|
| Adoption Rate | Tens of millions/year | Thousands/year |
| Additional Cost | Tens of thousands of yen | Hundreds of thousands of yen |
| Societal Impact | ◎ Widely adopted with significant accident reduction | △ Expensive, operates only under limited conditions |

Looking toward "the future of autonomous driving" is important.  
But right now, at this very moment, what's saving lives around the world is **Level 0 safety technology**.

---

## What I Want to Convey as an Engineer

Behind the glamorous headlines, there are people making steady improvements every day.  
To prevent even one more accident, to save even one more life, they continue refining each sensor, each line of control logic.

The true value of the automotive industry lies not in flashy demos or headlines, but in **"the power to make society as a whole safer"**.  
Improving Level 0 safety is at the forefront of that mission.

## References

### Key Literature

1. SAE International, "J3016: Taxonomy and Definitions for Terms Related to Driving Automation Systems for On-Road Motor Vehicles" (2021)
2. Euro NCAP, "2024 Test Protocol – Safety Assist"
3. IIHS, "Real-world benefits of crash avoidance technologies" (2024)
4. UNECE, "UN Regulation No. 157 - Automated Lane Keeping Systems (ALKS)" (2021)
5. European Commission, "General Safety Regulation (EU) 2019/2144"
6. NHTSA, "Automatic Emergency Braking Systems" (2024)
7. AAA Foundation for Traffic Safety, "Advanced Driver Assistance Technology Names" (2023)

### Related Links

- [Euro NCAP Official Site](https://www.euroncap.com/)
- [IIHS Highway Loss Data Institute](https://www.iihs.org/)
- [SAE International Standards](https://www.sae.org/)
- [UNECE Vehicle Regulations](https://unece.org/transport/vehicle-regulations)
- [Mercedes-Benz Drive Pilot](https://www.mercedes-benz.com/en/innovation/autonomous/drive-pilot/)
- [Honda Traffic Jam Pilot](https://global.honda/newsroom/news/2021/4210311eng.html)

---