+++
created = "2025-12-04"
date = "2025-12-04T23:42:21+09:00"
title = "Defining Vision: Strategic Choice from Past Success & Failure"
author = "Takuya Niioka"
draft = false
portfolio = ["[[Portfolio_Blog]]"]
tags = ["decision-making", "strategy", "vision-definition", "system-architecture", "business-strategy"]
slug = "how-to-define-vision-strategic-choice"
categories = ["Strategy", "Decision Making", "Engineering Leadership"]
description = "Japanese companies' ADAS strategy: Learn from past failures and successes to define winning vision using three key principles, not just follow competitors."
lang = "en"
publishDate = "2025-12-04T23:44:44+09:00"
+++

## 3-Line Summary

- **Vision (decision criteria) is decisive, but how to define that vision is the greatest challenge**
- **Japanese companies' failure patterns (smartphones, TVs, solar panels) and success patterns (Daikin, FANUC, Murata, Shin-Etsu) follow clear laws**
- **Three principles for defining vision: 1. Don't compete on competitors' turf, 2. "Essential value" over "ease of appeal", 3. Leverage past success patterns**

---

## Where Should Japanese ADAS Be Heading?

Are these conversations happening in your development team?

- "Tesla is doing it, so we should go in the same direction"
- "Chinese companies are attacking with data volume, so let's strengthen data collection"
- "Once regulations are decided, we'll develop accordingly"

**All of these decisions are signs of "vision absence."**

Many Japanese companies that have succeeded until now have been defeated by **choosing the wrong vision**. They lost 90% market share in smartphones, fell from world leadership in LCD TVs, and had 50% share stolen in solar panels.

There's **no need to repeat** the same mistakes in the automotive industry.

This article organizes **the differences between "winning visions" and "losing visions"** extracted from past success and failure patterns. It will help you reexamine your project's "current decisions" and present vision design techniques that will determine victory or defeat 10 years from now.

### Why Vision Definition Is Difficult

Throughout the decision-making series—[Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain](/posts/beyond-frameworks-adas-strategy-under-uncertainty/), [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/), [Decision-Making Under Uncertainty: The 70% Rule](/posts/decision-making-under-uncertainty-70-percent-rule/), and [Proactive vs Reactive Decisions: 4 Quadrants Framework](/posts/four-quadrants-of-decision-making/)—I've consistently stated one thing:

**Vision (decision criteria) is decisive.**

With clear decision criteria, you can take initiative; without them, you're reactive. With decision criteria, you become strategic; without them, you become ad hoc. In other words, **vision determines everything**.

However, the most important question remains:

**How do you define that vision?**

What should you aim for? Which direction should you choose? This article will answer these questions.

### Three Temptations

Vision definition is difficult because we're constantly exposed to three temptations:

**Temptation 1: Competitor Comparison and Following**

> "Because competitors are doing it, we should too" "Because it's trending in the market"

This temptation is the most powerful. In 2007, when Apple announced the iPhone, Japanese mobile phone manufacturers had overwhelming market share domestically[^1]. Their technology and quality were world-class. But what did Japanese companies do? They adopted touchscreens, created app stores, refined designs, and competed on Apple and Samsung's turf—UX and ecosystems.

The result was devastating defeat. From 2015 onward, Japanese manufacturers lost significant share in both domestic and international smartphone markets to Apple and Samsung[^2].

**Temptation 2: Market Voice**

>"Investors are demanding it" "There's media buzz" "We need features with appeal"

Around 2004, Japan held approximately 70% of the Chinese LCD TV market and high global market share[^3]. When Korean and Taiwanese competitors caught up, what did Japanese companies do? Thinner, higher quality, cheaper. They competed on the same turf as Korea and Taiwan—thinness and price.

As a result, they were caught in price competition in a commoditized, standardized market. By around 2012, Korean companies Samsung and LG monopolized top market shares, Japanese companies lost significant share, and TV divisions alone became unprofitable[^4].

**Temptation 3: Technological Possibility**

>"Because it's technically possible, let's do it" "Because it's cutting-edge technology, it has value"

Around 2005, Japan held approximately 50% world share in solar panels[^5]. When Chinese competitors attacked with overwhelming capital and production scale, Japanese companies tried to maintain technological superiority. However, they lost in mass production cost competition and fell outside the global top 10 by 2015[^6].

### Why We Succumb to These Temptations

One factor in succumbing to these temptations is trying to meet short-term market expectations. Overreacting to "ease of appeal" and "buzz," and underestimating one's own strengths. There are understandable reasons as management decisions. Investors demand short-term results, media seeks stories with buzz.

However, there's a trap here.

### What Happens When Vision Definition Goes Wrong

Recall Intel's example analyzed in [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/). Intel's vision was "vertical integration is our competitive advantage." However, the environment shifted to the fabless + foundry division era. Intel didn't update its vision, resulting in decline.

When vision is wrong, all decisions may be wrong. No matter how much effort you make, that effort may head in the wrong direction. And when you realize it, it may be too late.

That's why vision definition is one of the most important decisions. So how can you define vision?

---
## Japanese Companies' Failure Patterns

Japanese companies have repeatedly made the same mistakes. However, these failures follow clear patterns.

### Smartphones: Fall from Overwhelming Share

In 2007, Japanese mobile phone manufacturers had overwhelming domestic market share[^1]. Technology and quality were world-class. "Garakei" (feature phones) were technological crystallizations Japan could be proud of.

Then the iPhone appeared.

Japanese companies' response was swift. They adopted touchscreens, created app stores, refined designs. They launched smartphones with no technical inferiority one after another. However, the result was devastating defeat. From 2015 onward, Japanese manufacturers lost significant share in both domestic and international smartphone markets[^2].

**Why did they lose?**

Let's compare competitive elements:

| Competitive Element | Japan | Apple/Samsung |
| ---------- | ----- | ------------- |
| UX Design | △ | ◎ |
| Ecosystem | △ | ◎ |
| Development Speed | △ | ◎ |
| Brand Power | ○ | ◎ |
| **Reliability/Quality** | **◎** | **○** |

Japan's strength in reliability and quality didn't become a differentiating factor in UX competition. They competed on Apple and Samsung's turf and were devastated.

**This structure applies directly to ADAS.** If you fight on the same turf while Tesla defines the competitive axis as "data volume" and "development speed," the same outcome awaits.

### LCD TVs: Rapid Fall from High Share

Around 2004, Japan held approximately 70% of the Chinese LCD TV market and high global market share[^3]. Sharp's AQUOS, Sony's BRAVIA, Panasonic's VIERA—these were symbols of technological prowess.

Korean and Taiwanese competitors caught up. What did Japanese companies do? Thinner, higher quality, cheaper. They competed on the same turf as Korea and Taiwan—thinness and price.

As a result, they were caught in price competition in a commoditized, standardized market. By around 2012, Korean companies Samsung and LG monopolized top market shares, Japanese companies lost significant share, and TV divisions alone became unprofitable[^4].

Japan's quality difference was "invisible" to consumers. The difference between a TV that doesn't break for 5 years versus 10 years can't be judged at purchase. If prices are the same, people choose cheaper. They were caught in price competition in a market where quality differentiation was meaningless.

**This structure applies directly to ADAS.** Even if you appeal "advanced automation levels," consumers can't see it. If value isn't conveyed, you'll be caught in price competition.

### Solar Panels: From 50% to Outside Top 10

Around 2005, Japan held approximately 50% world share in solar panels[^5]. Sharp, Kyocera, Mitsubishi Electric—they led the world as environmental technology pioneers.

Chinese competitors attacked with overwhelming capital and production scale. Japanese companies tried to maintain technological superiority and focused on efficiency improvements. However, they lost in mass production cost competition and fell outside the global top 10 by 2015[^6].

Panels with 20% versus 22% conversion efficiency—technically a large difference. However, if installation space is sufficient, installing more cheap 20% panels is more economical. Technological superiority alone wasn't enough to win.

**This structure applies directly to ADAS.** Even if the technical difference between "99% recognition accuracy" and "99.5%" is large, it's meaningless if it doesn't translate to customer value.

### Common Points in Failure Patterns

These three failures share clear commonalities:

**1. Competed on competitors' strong turf**
- Smartphones: UX/Ecosystem (Apple's strength)
- TVs: Price/Scale (Korea/Taiwan's strength)
- Solar: Capital/Production volume (China's strength)

**2. Attempted differentiation with "easy-to-appeal features" and "visible performance"**
- Touchscreens, thinness, production volume
- These are certainly "easy to understand" and "easy to convey appeal"
- However, competitors can do the same

**3. Japan's strengths (reliability, quality depth) didn't come alive**
- In commoditized markets, quality doesn't differentiate
- "Doesn't break for 10 years" loses to "cheap now"

**4. Result: Share loss, profit margin plunge**
- Every market: 90%→10%, 70%→10%, 50%→5%
- Following the same trajectory

This isn't coincidence but a structural problem.

### The Essence of These Defeats

**All these defeats were errors in "vision design"**:

1. **Fought on opponents' turf** - Competed in areas where competitors excel (UX, price, capital)
2. **Misjudged the center of customer value** - Pursued ease of appeal, neglected essential value
3. **Made decision criteria dependent on others** - Followed competitors, markets, technology trends

**This structure is actually the same in current automotive (ADAS) development.**

While Tesla and Chinese companies define competition as "data volume" and "development speed," will you fight on the same turf? Or choose a turf where Japan's strengths (extreme safety verification, zero-failure quality culture) come alive?

Vision design errors determine defeat 10 years from now.

---

## Japanese Companies' Success Patterns

However, Japanese companies haven't only been defeated. There are companies that compete with their own strengths and continue winning.

### Daikin Industries (Air Conditioning): World Top Share

**"Don't compete on performance, be chosen for trust and local optimization"
That was Daikin's vision**

Daikin Industries has established the No.1 position globally in air conditioning equipment sales[^7]. In markets where Western competitors tried to sell "high-performance air conditioners," Daikin did something different.

**What did they win with?**

They thoroughly understood China and Southeast Asia's climate and living environments, providing products and services optimized for local conditions. Most importantly, they competed on invisible quality—"doesn't break," "doesn't stop." They built a global after-service network supporting customers with 24-hour response.

In other words, they competed not on "ease of performance appeal" but on "reliability and local optimization."

Operating profit margin is maintained around 10%[^8]. Daikin's vision can be expressed as "the most trusted air conditioning partner." Not easy to appeal, but clear and sustainable.

### FANUC (Industrial Robots): World Leader

**"Compete not on cutting-edge technology but on absolute reliability that never stops"
That was FANUC's vision**

FANUC holds world leadership with approximately 18.5% market share in industrial robots[^9]. They won not with "cutting-edge robots" (ease of technology appeal) but with "robots that don't break" (reliability).

**What did they win with?**

They thoroughly understood manufacturing's "downtime costs." When a production line stops for one hour, losses range from millions to tens of millions of yen. FANUC's robots provide absolute reliability of "never stopping," with a global service network achieving 24-hour response.

Clear ROI: The economic value of downtime reduction justifies FANUC robots' premium pricing. Even when Chinese manufacturers introduce cheap robots, FANUC continues to be chosen for critical processes.

Operating profit margin exceeds 30%, among the highest in manufacturing[^10]. FANUC's vision can be expressed as "production lines that absolutely never stop." Customer value is clear.

### Murata Manufacturing (Electronic Components): ~40% Share

**"Become inconspicuous but indispensable"
That was Murata's vision**

Murata Manufacturing holds approximately 40% world share in multilayer ceramic capacitors (MLCC)[^11]. They won not with "easy-to-appeal products" but with "plain but essential components."

**What did they win with?**

"Invisible presence" with hundreds used per smartphone. Even as China and Korea chase, they differentiate with quality barriers. "Troublesome without it" yet "inconspicuous"—this is the strongest positioning.

Operating profit margin is maintained around 16%[^12]. Murata's vision can be expressed as "the unsung hero supporting electronic devices worldwide." Plain, but indispensable.

### Shin-Etsu Chemical (Silicon Wafers): World Leader

**"Be chosen not for cutting-edge nature but for 99.999% extreme quality"
That was Shin-Etsu's vision**

Shin-Etsu Chemical maintains world leadership with approximately 24% market share in silicon wafers[^13]. They won not with "cutting-edge processes" (ease of technology appeal) but with "extreme quality" (99.999% quality).

**What did they win with?**

Even as Korea, Taiwan, and China chase, Shin-Etsu continues to be chosen for cutting-edge processes. Because semiconductor manufacturing requires 99.999% quality. A 0.001% defect rate difference significantly impacts yield.

Operating profit margin is maintained at an astonishing level around 32%[^14]. Shin-Etsu's vision can be expressed as "extreme quality base material supporting the semiconductor industry." Competing in areas where failure is unacceptable.

### Common Points in Success Patterns

These four successful companies share clear commonalities:

**1. Chose turf where competitors are weak**
- Reliability, extreme quality, invisible value
- These are Japanese companies' strong areas

**2. Competed in "plain but essential," "failure-intolerant" domains**
- Air conditioning, robots, components, wafers
- All are "troublesome if stopped," "troublesome if broken"

**3. Japan's strengths (verification depth, quality culture) directly come alive**
- Can maintain premium pricing
- Continuous revenue (service, subscription)

**4. Result: High share, high profit margin maintenance**
- 20-40% share
- 10-25% operating profit margin
- Sustainable business model

Most importantly, these companies had clear visions. "What to win with" was clear, "how to differ from competitors" was clear.

---

**💭 Which pattern is your project following?**

Try self-diagnosis with these questions:

- Are your development goals the same as competitors' (Tesla, Chinese companies) goals?
- Are your differentiation points visible to customers and measurable?
- Do your organization's strengths (quality, verification capability) come alive in your current strategy?

If even one answer is "No," you may be **approaching the failure pattern**.

Conversely, how to approach the success pattern? The next section explains that technique.

---

## 📌 Three Principles of Vision Definition

We've seen failure and success patterns. From these, we can extract three principles of vision definition.

**In your project, are you trying to ride someone else's success pattern? Or are you trying to define a new turf where your own strengths come alive?**

### Principle 1: Don't Compete on Competitors' Turf

**Failure pattern lesson: You lose when competing on competitors' strong turf**

**Success pattern lesson: Choose turf where competitors are weak**

How specifically? Think in three steps.

**Step 1: Analyze competitors' strengths**

First, calmly analyze what competitors are good at. What are competitors investing capital in? What is their organizational culture optimized for?

For example, Apple? UX design culture, ecosystem building capability, brand power. These are assets built over decades. Tesla? Data collection and AI development speed, software-first culture, vertical integration execution. Chinese companies? Overwhelming capital, development speed, domestic market scale.

These strengths can't be imitated overnight.

**Step 2: Analyze your own strengths**

Next, truly objectively analyze what you're good at. What assets have you accumulated over years? What is your organizational culture optimized for?

For Japanese companies: Extreme quality verification capability, mass production track record at tens of millions scale, failure-intolerant culture, long-term perspective, trust relationships with customers. These are assets built over decades.

Importantly, don't underestimate your own strengths. "Quality is standard" is wrong. 99.999% quality is not standard.

**Step 3: Turf selection**

Compare competitors' and your own strengths, choosing the domain where "competitors' strengths ≠ your strengths."

Thinking as a systems architect:

✗ Compete on "cutting-edge AI technology" and "development speed"
→ This is Tesla and Chinese companies' strong domain

✓ Compete on "extreme safety verification" and "zero-failure quality"
→ This is Japan's strong domain

Turf selection determines vision direction.

### Principle 2: "Essential Value" Over "Ease of Appeal"

**Failure pattern lesson: Easy-to-appeal features don't differentiate**

**Success pattern lesson: Plain but essential is strongest**

How specifically?

**Step 1: Distinguish "easy-to-appeal value" from "essential value"**

Easy-to-appeal value:
- Has buzz
- Gets media coverage
- Attracts investor attention
- Easy to demonstrate
- Evaluated short-term

Essential value:
- Solves customers' real problems
- Evaluated long-term
- Failure-intolerant domain
- ROI calculable
- "Troublesome without it" existence

**Step 2: Define essential value**

What are customers really troubled by? What would they pay for if solved? If it fails, how much cost occurs?

For example, in manufacturing: When robots stop, losses are millions of yen per hour. That's why they pay premium for FANUC's "robots that don't stop."

In semiconductor manufacturing: If wafer defect rate rises 0.01%, losses are hundreds of millions of yen. That's why they pay premium for Shin-Etsu's "99.999% quality."

Domains where this "cost of failure" is clear are where essential value is demonstrated.

**Step 3: Align vision with essential value**

Thinking as a systems architect:

✗ Pursue "automation level" and "advanced features"
→ Easy to appeal, but what's the essential value? ROI?

✓ Pursue "accident reduction" and "protecting lives"
→ Plain, but clear ROI (accident cost reduction)

I'm not denying easy-to-appeal value. However, the core of vision should be essential value.

### Principle 3: Leverage Past Success Patterns

**Success pattern lesson: Japanese companies have winning patterns**

How specifically?

**Step 1: Study your company's and country's success examples**

Daikin, FANUC, Murata, Shin-Etsu. What did these companies win with? What are the commonalities?

Commonalities:
- Competed on reliability and extreme quality
- Chose failure-intolerant domains
- Became plain but essential existence
- Maintained premium pricing and high profit margins
- Invested with long-term perspective

This isn't coincidence but a way of fighting where Japanese companies' strengths come alive.

**Step 2: Extract success patterns**

Success patterns:
- Choose domains that are "troublesome if stopped" or "troublesome if broken"
- Aim for 99.999% quality
- Differentiate with invisible value
- Build long-term trust relationships
- Target customers where failure costs are high

These patterns apply across different industries.

**Step 3: Apply to your domain**

As a systems architect, applying to ADAS development:

FANUC's "robots that don't stop"
→ ADAS version: "cars that don't cause accidents"

Shin-Etsu's "99.999% quality wafers"
→ ADAS version: "99.999% safe systems"

Murata's "invisible essential components"
→ ADAS version: "protected without noticing"

Daikin's "local optimization and reliability"
→ ADAS version: "reliability protecting all drivers"

The same structure emerges.

---

## Systems Architect Practice: How to Apply to ADAS Development

We've seen the three principles of vision definition. So how do you practice as a systems architect in ADAS development?

### If You Define Vision in Your ADAS Development

If you define vision in ADAS development, you can apply the three principles like this:

**Applying Principle 1: Avoid competitors' turf**

Competitor analysis:
- Tesla: Data volume (millions of vehicles × hundreds of millions of miles), development speed, software-first culture
- Chinese companies: Capital, AI talent, domestic market scale

You can't win competing on these turfs.

Turf to choose:
- Extreme safety verification (99.999% reliability)
- Zero-failure quality culture
- Long-term track record (tens of millions scale mass production experience)

These are Japanese companies' strong domains.

**Applying Principle 2: Essential value**

Easy-to-appeal value: "Automation level," "advanced features," "buzz"

Essential value: "Accident reduction," "protecting lives," "driving with peace of mind"

The social cost of traffic accidents is trillions of yen annually. If you can reduce accidents by 30%, that economic value is clearly calculable. This is essential value.

**Applying Principle 3: Success patterns**

Learning from FANUC's "robots that don't stop":
- Manufacturing downtime costs → Traffic accident social costs
- "Doesn't stop" reliability → "Doesn't cause accidents" reliability
- 24-hour support → Safety in all situations

Learning from Shin-Etsu's "99.999% quality":
- Semiconductor defect rate → ADAS malfunction rate
- Extreme quality verification → Extreme safety verification
- Zero failure tolerance → Zero accident tolerance

Learning from Murata's "invisible essential components":
- Capacitors are inconspicuous → ADAS is also inconspicuous
- But troublesome without them → Protects from accidents
- Installed in all products → All drivers are targets

**Integrated vision:**

"ADAS that absolutely never fails, protecting all drivers invisibly and continuously"

This is:
- Plain but indispensable
- Essential value is clear (accident reduction)
- Japan's strengths come alive 100% (extreme quality)
- Not competitors' turf (differentiate with reliability)
- Same structure as success patterns

### Pitfalls in Vision Definition

When defining vision, beware of four pitfalls.

**Are these words flying around in your project?**
- "Let's move when regulations are decided" "Waiting for boss's decision" → This is a sign of **vision absence**
- "Because customers are saying this" → Is that really the **essence of customer value**?

**Pitfall 1: Copying others' visions**

✗ "ADAS like Tesla's"
✓ "Japan-like ADAS"

Tesla's vision is based on Tesla's strengths. Copying it won't work because strengths differ.

**Pitfall 2: Too abstract**

✗ "Best ADAS"
✓ "ADAS chosen for accident reduction"

Abstract visions don't become decision criteria. Must be specific and measurable.

**Pitfall 3: Swayed by short-term market voice**

✗ "Because investors demand it"
✓ "Will it have value 10 years from now?"

Market voice is important. But it's not all of vision. Ask yourself if it will have value 10 years from now.

**Pitfall 4: Underestimating your own strengths**

✗ "Quality is standard"
✓ "Extreme quality is differentiation"

Japanese companies' biggest problem is thinking their strengths are "standard." 99.999% quality is not standard. It's overwhelming competitive advantage.

---
## Summary: Vision Determines Strategy

### Conclusion of Decision-Making Series

Let's review the decision-making series so far.

[Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain](/posts/beyond-frameworks-adas-strategy-under-uncertainty/) presented the 5-Layer Decision Framework for strategizing amid uncertainty. [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/) taught us that companies (Intel) that don't update vision decline. [Decision-Making Under Uncertainty: The 70% Rule](/posts/decision-making-under-uncertainty-70-percent-rule/) explained techniques for deciding with 70% information, and [Proactive vs Reactive Decisions: 4 Quadrants Framework](/posts/four-quadrants-of-decision-making/) explained techniques for designing decisions.

And now, in this article, I've attempted to answer the most fundamental question:

**How do you define vision?**

The truth running through everything is "vision (decision criteria) is decisive." And this time, I've provided the answer: "Vision quality can be learned from past success and failure patterns."

### Vision Definition Checklist You Can Use Today

| Evaluation Item | Check Content | Example (ADAS Development) |
| ------------ | --------------------- | ----------------------------- |
| **Competitive Advantage** | Domain where competitors' strengths ≠ your strengths? | Compete on extreme safety verification, not data volume |
| **Customer Value** | Is ROI/failure cost clear? | Social cost reduction through accident reduction (trillions of yen annually) |
| **Sustainability** | Valid 10 years from now? | Even in AI era, humans must ultimately guarantee safety |
| **Differentiation** | Won't commoditize? | 99.999% reliability isn't easily imitated |
| **Measurability** | Can progress be measured numerically? | Measurable by accident rate reduction, ODD (Operational Design Domain) expansion range |
| **Success Pattern Application** | Leveraging your company's/country's winning patterns? | Applying FANUC (doesn't stop), Shin-Etsu (extreme quality) patterns |

**Does your vision meet these six criteria?** If even one is "No," it's worth reconsidering your vision.

### Message to Systems Architects

As stated in [The Essence of System Architecture: Building the Right Thing](/posts/what-systems-architects-actually-do/), the essence of systems architects is defining "building the right thing."

What is "the right thing"? It's what aligns with vision.

That's why the ability to define vision is the most important skill for systems architects.

Technical knowledge can be replaced by AI in the coming era. Implementation details will also be automated. However, the power to define vision can only be done by humans.

And that power isn't talent. It can be acquired through learning from past success and failure patterns.

History teaches us answers. Patterns where Japanese companies were defeated, patterns where they won. Extracting commonalities and applying them to your domain—this is the essentially important process.

### Next Preview

Next time, I plan to explain "techniques for implementing vision."

Even if you define vision, it's meaningless if you can't implement it. So how do you:
- Permeate vision throughout the organization
- Break down vision into specific decision timing
- Measure vision progress
- Regularly update vision

Integrating with [Proactive vs Reactive Decisions: 4 Quadrants Framework](/posts/four-quadrants-of-decision-making/), I'll explain vision implementation techniques.

From vision definition to implementation. The decision-making series approaches completion.

---

## Related Articles

- [Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain](/posts/beyond-frameworks-adas-strategy-under-uncertainty/)
- [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/)
- [Decision-Making Under Uncertainty: The 70% Rule](/posts/decision-making-under-uncertainty-70-percent-rule/)
- [Proactive vs Reactive Decisions: 4 Quadrants Framework](/posts/four-quadrants-of-decision-making/)

---

**【Disclaimer】**
The content of this article represents the author's personal views and does not represent the official views of any affiliated organization. Company case studies in the article are analyses based on public information and are not intended to criticize specific companies or strategies. Vision definition has different optimal solutions for each organization, and this article presents one way of thinking.

---

## References

[^1]: [Truly rise and fall, looking back at mobile phone manufacturers' market share from 2001 | Buzzap!](https://buzzap.jp/news/20120513-mobile-market-share-2001-2011/)
[^2]: [Smartphone OS and Device Share Survey in 40 Countries/Regions Worldwide [July 2025 Edition] - Global Marketing (Overseas SEO/Overseas Advertising) | Aun Consulting](https://www.auncon.co.jp/press/research/2025-07-17/)
[^3]: [3 Innovation and Decline of Japanese Companies in LCD TV Industry - Business History](https://www.jstage.jst.go.jp/article/bhsj/49/2/49_2_3/_pdf)
[^4]: [Management Sensor 2008.12 Trends and Prospects of Flat Panel TV Industry - TBR](https://www.tbr.co.jp/report/sensor/pdf/sensor_20081201_03.pdf)
[^5]: [Solar Power Market Trends - Wikipedia](https://ja.wikipedia.org/wiki/太陽光発電の市場動向)
[^6]: [Review of Solar Cell Industry and Future Direction of Next-Generation Solar Cells - Agency for Natural Resources and Energy](https://www.meti.go.jp/shingikai/energy_environment/perovskite_solar_cell/pdf/001_02_00.pdf)
[^7]: [Global No.1 in Sales: Approaching Daikin's Global Strategy as a 4 Trillion Yen "Air" Company | Job Hunting Site [ONE CAREER]](https://www.onecareer.jp/articles/2323)
[^8]: [Daikin 1Q Results Hit Record High Despite Economic Downturn - Nikkei XTECH](https://xtech.nikkei.com/atcl/nxt/column/18/00001/08297/)
[^9]: [Global Market Share Analysis of Industrial Robot Industry | deallab](https://deallab.info/industrial-robot/)
[^10]: [FANUC - Wikipedia](https://ja.wikipedia.org/wiki/ファナック)
[^11]: [Global Market Share Analysis of Capacitor Industry | deallab](https://deallab.info/capacitor/)
[^12]: [Company Analysis: Murata Manufacturing - kabuya66](https://note.com/kabuya66/n/n20e437b8c121)
[^13]: [Global Market Share Analysis of Silicon Wafer Industry | deallab](https://deallab.info/siliconwafer/)
[^14]: [Semiconductor-Related Company Research: Thorough Explanation of Performance and Salary of World's Leading Silicon Wafer Company Shin-Etsu Chemical](https://www.semiconductor-industry.com/shinetsu/)