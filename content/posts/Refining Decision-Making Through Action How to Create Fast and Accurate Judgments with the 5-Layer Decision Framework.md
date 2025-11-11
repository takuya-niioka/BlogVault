+++
created = "2025-11-07"
date = "2025-11-11T22:55:35+09:00"
title = "Refining Decision-Making Through Action: How to Create \"Fast and Accurate Judgments\" with the 5-Layer Decision Framework"
author = "Takuya Niioka"
draft = false
portfolio = ["[[Portfolio_Blog]]"]
tags = ["Decision-making", "System-Design", "Technology-Strategy", "Product-Strategy", "Engineering"]
slug = "5-layer-decision-for-fast-action"
categories = ["Engineering Philosophy", "Decision Making"]
description = "Learn how engineers can overcome decision paralysis and accelerate choices by moving beyond intuition to structured decision-making frameworks."
lang = "en"
publishDate = "2025-11-11T23:42:10+09:00"
+++
## Introduction: Accelerating Decision-Making Speed

Throughout my career as an engineer, I've witnessed countless decision-making scenarios.
When determining the direction of feature development, selecting new system architectures, or balancing safety requirements with costs—each situation appeared to have "one correct answer," yet in reality, they were all highly uncertain, and no amount of deliberation could provide complete confidence.

Overthinking leads to time slipping away, and eventually we decide with an uneasy "I guess this will do."
Looking back later, no one can explain "why we made that decision," forcing us to repeat the entire discussion.
I've experienced this pattern countless times.

At the root of such stagnation lies "relying on individual intuition and instinct for decision-making." However, decision-making should not be a person-dependent activity—it should be **a process that can be designed with reproducibility**.

Particularly in high-uncertainty domains like ADAS, waiting for perfect information will never yield the right answer. What's needed is **a structure that improves accuracy while moving forward through uncertainty**.

Having struggled with these challenges myself, I've arrived at a key insight:
**We need a thinking structure that refines strategy and decisions while in motion.**
In other words, **don't separate thinking from action—integrate them**.
To enable quick corrections even when mistakes occur, we must first clarify the "terrain" of decision-making.

In this article, I'll introduce the specific content of the "5-Layer Decision Framework" mentioned in my previous article ([Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain](/posts/beyond-frameworks-adas-strategy-under-uncertainty/)).

The key principle is this: **don't seek perfect answers from the start.** Instead, rapidly generate multiple options, then organize Layer 1 (constraints) and Layer 2 (value hypotheses) from there.
Following this sequence prevents decision-making discussions from diverging while improving both speed and quality.

---
## Creating Draft Proposals: First, Build a Foundation for Action

Many people spend excessive time on strategic planning and decision-making because **they start with abstract discussions**.
When you immediately jump into questions like "which direction is correct?" or "what should we prioritize?", your thinking inevitably goes in circles. You're discussing routes without having a "map" yet.

Therefore, the first step is **to generate proposals rapidly and improvisationally**—not just one, but **at least three (Options A, B, and C)**.

What matters at this stage isn't judging "which is correct," but gaining a bird's-eye view of "what directions are possible."

### Step 1: First, Generate "Roughly Three Options"

For example, suppose there's a theme in next-generation ADAS feature development: "How should we design so users comfortably accept automated steering?"
In this case, consider three directions:

- **Option A: Keep it simple with minimal control (eliminate discomfort)**
- **Option B: Actively intervene with control to demonstrate reliability (project dependability)**
- **Option C: Vary control according to driver personality (personalize)**

Simply writing these options down dramatically clarifies your thinking.
What's important is **not trying to generate perfect ideas**.
It's fine if the directions are somewhat extreme. The goal is creating a "foundation" for discussion—ideally, generate these in about 3-5 minutes.

### Step 2: Determine Decision "Accuracy" and "Risk Tolerance"

Next, confirm **what level of accuracy the decision requires**.
No matter how excellent your framework, judgments will waver if the required accuracy remains unclear.

I always ask myself these three questions:

1. **If this decision is wrong, what level of risk exists?**
   → Prototype-stage decisions are easy to recover from even if they fail
2. **Does this decision need to be explained to or approved by others?**
   → Organization-wide policies require more thorough justification
3. **Is it correctable, or irreversible once decided?**
   → The more irreversible, the more careful the initial hypothesis validation

Organizing these three points reveals what level of consideration is sufficient.
If risk is low, prioritize speed; if high, allocate more time for validation.
This is optimal allocation of "thinking time" versus "action time."

### Step 3: Clarify Premises Before Moving

Once you've generated Options A/B/C, write down in one sentence **"the premise required for this option to work"** for each. This corresponds to the "○○" in "If ○○, then Option A is good."
This becomes material for creating the assumption dependency map later.

For example—
- Option A stands on the premise that "users don't want active intervention."
- Option B is based on the hypothesis that "many people feel reassured by some degree of automatic operation."
- Option C involves the technical condition that "sufficient data can be collected for the system to recognize individual differences."

By explicitly stating premises, it becomes easier to explain "why we chose this option" later.
You can also identify early which parts of your hypothesis are fragile.

Simply generating three options and clarifying risks and premises—even loosely—makes **organizing Layer 1 (constraints) and Layer 2 (value hypotheses)** dramatically easier.
Draft proposals serve as both the "starting point" of thinking and the "trigger" for action.

---
## Structuring Layers 1, 2, and 3: Fixing the Order of Thinking

After generating three draft proposals, create a "structure" to organize them. The critical element here is **establishing a fixed order of thinking**.
Without a clear sequence, discussions become confused and conclusions remain ambiguous. I recommend thinking in three layers: "constraints → value hypotheses → future hypotheses."

### Layer 1: Identify Immovable Constraints (Hard Constraints)

First, identify **immovable constraints**.
These are like "terrain" that cannot be overcome regardless of strategy. By defining Layer 1, you avoid wasteful discussions and establish realistic decision criteria.

| Item | Content | Notes |
|------|---------|-------|
| Safety Constraints | Don't exceed driver responsibility scope | Based on safety standards and internal policies |
| Regulatory Constraints | UN/domestic regulations, UN-R79 compliance | Changes require years of lead time |
| Technical Constraints | Recognition range 100m, reaction within 100ms | Upper limits of current sensor specifications |
| Quality/Reliability | Maintain malfunction rate below 1% | Agreement conditions with quality assurance department |
| Emotional Constraints | Operations that users perceive as "moving on its own" are prohibited | Minimum condition for peace of mind |

Identifying Layer 1 clarifies both "what must not be done" and "conditions that must be met." Leaving ambiguity here causes correction costs to explode exponentially later. **Fixing constraints also clarifies the scope of thinking.**

### Layer 2: Consider Changeable Premises (Soft Assumptions)

Next, organize **what constitutes value**.

Value must be defined contextually: "for whom, in what moment, what is provided."

| Perspective | Content | Validation Method |
|------------|---------|-------------------|
| Pain (Dissatisfaction) | What users feel "I want this improved" | Interviews, hearings |
| Anti-pain (Rejection) | What they think "I don't want this done to me" | Real vehicle evaluation, simulation |
| Value (Value Hypothesis) | What makes them feel "I'd be happy if this were done" | Subject experiments, surveys |
| Target Users | Whose experience, in what context | Persona setting, usage context analysis |

In this layer, "what not to do" is as important as "what to solve." Resolving pain while avoiding user rejection builds trust.

### Layer 3: Write Unknown Elements (Unknowns)

After organizing Layers 1 and 2, consider **Layer 3: Future Hypotheses**.

This layer structures "what changes will occur in the future" and how to prepare for them. To keep strategy viable long-term, this future axis cannot be neglected.

| Item | Content | Consideration Example |
|------|---------|----------------------|
| Market Trends | Regulatory relaxation/popularization timing of autonomous driving levels | L3 expansion forecast from 2028 onward |
| Competitive Trends | Technology development status of major OEMs and emerging companies | Direction of Tesla, Waymo, domestic companies |
| Assessment | Changes in safety evaluation standards like NCAP/IIHS | Weighting of steering assistance and departure prevention |
| Technology Trends | Sensor performance enhancement, AI control sophistication | Within 5 years: 2x accuracy, half the cost |
| Social Acceptance | Trust level in autonomous driving, ethical concerns | Cultural differences by country/region |

Layer 3 is less about predicting the future than **preparing options for when premises change**.

For example: "if regulations are relaxed, adopt Option B" or "if user trust isn't sufficient, revert to Option A." This becomes the foundation for **conditional decision-making**.

### The Meaning of Three-Layer Structure

By organizing these three layers in sequence, discussions proceed logically.

1. **Define reality's limits with Layer 1** (fix immovable terrain)
2. **Identify human value with Layer 2** (in what moments does meaning emerge)
3. **Anticipate future changes with Layer 3** (prepare scenarios for when premises change)

Simply following this order allows you to focus on decision criteria without being swayed by abstract idealism or intuitive opinions. Structuring strategy and decision-making means **designing the order of thinking**.

Based on insights gained through these three layers, **redesign the initial Options A/B/C**. This connects to the next phase: **refining options and running validation cycles**.

---
## Refining Options and Running Validation Cycles

Now comes the critical question: **"which hypothesis should we activate first?"**

Strategy and decision-making are merely assumptions while on paper. Hypotheses only gain meaning when put into motion.

### Step 1: Determine the Balance of Accuracy and Risk

First, consider: "what level of accuracy does this decision require?"

Spending too much time increasing accuracy allows the environment to change and premises to collapse.
Conversely, neglecting accuracy risks losing trust.

For this reason, I consider the following three axes:

| Axis | Content | Perspective to Be Conscious Of |
|------|---------|-------------------------------|
| Risk Tolerance | Magnitude of impact if wrong | "Can we recover even if we fail?" |
| Deadline | By when must we decide | "What should we verify before time runs out?" |
| Accountability | To whom and to what extent must we explain | "What level of evidence is required?" |

By organizing these three axes, which option to try first and which hypothesis to validate first becomes clear. Rather than deciding everything at once, **"in what order to verify" is the core of decision-making**.

### Step 2: Lightweight Validation for Refining Options

Once you've selected a candidate from Options A/B/C, conduct **lightweight validation**.

While "validation" evokes thoughts of time and cost, the validation I'm referring to is much simpler.

For example, methods like these:

- **Simulation validation**: Confirm control logic behavior in virtual space
- **Scenario review meetings**: Brief discussions between assumed users and developers
- **Provisional user testing**: Confirm real reactions through small-scale observation
- **Paper/slide-based visualization**: Get reactions before actually building anything

The key point: "the purpose of validation is not to prove correctness, but to **find errors quickly**." Rather than worrying about whether something is correct, it's easier to move forward by **identifying what's wrong**.

### Step 3: Support Decisions with an Assumption Dependency Map

As validation progresses, relationships become visible: "this option works if ○○ holds true" or "it fails if △△ collapses."

The **Assumption Dependency Map** helps organize these relationships.

Simply put, it's a relationship diagram connecting lines showing "which premises are depended upon."

```
Premise A (Users trust automatic operation)
　↓depends on
Option B (Active intervention type)
　↑depends on
Constraint C (Manual intervention priority for safety)
```

By visualizing dependencies, you can instantly judge which conditions, if collapsed, invalidate an option.
When sharing with others, it's easier to explain "this option stands on these premises." This map serves as both "log" and "navigation" for decision-making.

### Step 4: Set Validation Deadlines

As hypothesis validation continues, the temptation to "let's look a bit more before deciding" inevitably appears.
Without setting an end to validation, decisions are postponed forever.
Always make it explicit: "by when, with what level of confidence will we decide?"

For example—
- By next week, collect reactions from 5 users regarding Option A's behavior
- By two weeks from now, confirm Option B's implementation feasibility and make a Go/No-Go decision

By setting concrete deadlines like this, **a rhythm of "moving and thinking" emerges**.

### Step 5: Repeat Correction and Redesign

Even if validation shows your hypothesis was wrong, that's not failure.
It's a discovery that brings you closer to the right decision.
What's important is "having a structure that allows errors to be corrected."

Rather than treating strategy as absolute, update it gracefully when premises change.
This flexibility ultimately supports the most robust long-term decision-making.

---
## Conclusion: From Static Thinking to Thinking While Moving

The greatest factor that stops decision-making is getting stuck trying to "find the right answer." While we worry about which hypothesis is correct, situations change and premises become outdated. In uncertain times, "refining hypotheses by putting them into motion" is far more important than "searching for the right answer."

First establish three options, structure them with Layers 1-3, and validate while moving. This process connects thinking and action continuously rather than separating them.

In other words, **treat decision-making not as "static judgment" but as "dynamic design"**.

> Not "think then move," but "think while moving."
> Even if wrong, just update those premises.
> What's important is not stopping, continuing to update.

---

Strategy is a structure that guides action; without action, it's not strategy. Deciding conditionally and correcting as needed—accumulating "provisional decisions"—is realistic and strong decision-making.

People and organizations that can cycle through this quickly learn fastest and evolve fastest. From "static thinking" to "thinking while moving"—this is the most essential attitude required of engineers navigating uncertain times.