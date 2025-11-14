+++
title = "The Essence of System Architecture: Building the Right Thing"
date = "2025-11-14T16:28:29+09:00"
draft = false
tags = ["System-Architecture", "Engineering-Philosophy", "Career-Development", "AI-Era", "Product-Strategy"]
slug = "what-systems-architects-actually-do"
description = "Discover what a System Architect truly does beyond common misconceptions and why their role focuses on \"building the right thing\" in ADAS development."
+++

## What is a System Architect?

The title "System Architect" is becoming increasingly common. However, few people can clearly explain its definition.

Software Architect? A senior position above System Engineer? Technical Leader?

I've grappled with this question for nine years in ADAS development.

In my fifth year, when I was promoted to Staff Engineer, I said:

> "I want to become an engineer who can contribute to 'building the right thing.'"

At the time, I didn't fully understand what those words meant. But through four years of subsequent experience, I realized something: **these words captured the essential role of a System Architect**.

## Common Misconceptions

When you search for "System Architect" online, you often find definitions like:

- Senior engineer
- Possesses advanced expertise

In other words, it's often portrayed as someone with strong implementation skills who deliberately steps back to oversee the bigger picture.

However, I believe **this is a one-dimensional understanding**.

Technical depth is certainly necessary. But that alone doesn't capture the essence of an architect. Strong implementation skills are a "necessary condition" but not a "sufficient condition."

The excellent architects I've observed weren't necessarily the fastest coders. Rather, they excelled in a different capability: **the ability to define "what should be built."**

## The Essential Role: "Building the Right Thing"

### Engineer vs Architect

| Perspective | Engineer | Architect |
|------------|----------|-----------|
| **Focus** | How to build | What and why to build |
| **Time horizon** | Sprint | Product lifecycle |
| **Deliverables** | Working code | Strategy and decision criteria |
| **Uncertainty** | Avoid | Handle |

**Importantly, this isn't about superiority—it's about different roles**. **Both are necessary in an organization and complement each other**.

If engineers provide value by "building efficiently," architects provide value by "building the right thing."

For example, in ADAS development:
- Engineers "optimally implement this control algorithm"
- Architects question "whether this control is necessary in the first place, whether it provides value to users"

Only when both exist can you create systems that are technically excellent and provide value to users.

### Systems Engineer vs System Architect

At this point, you might wonder, "What's the difference from a Systems Engineer?"

Actually, these two roles overlap significantly, but their focus differs:

| Perspective | Systems Engineer | System Architect |
|------------|------------------|------------------|
| **Primary focus** | System-wide consistency | Strategy and value definition |
| **Scope** | Technical integration and verification | Bridge between business value and technology |
| **Deliverables** | System requirements specs, verification plans | Architecture strategy, decision criteria |
| **Question** | "Does this system function correctly?" | "Is this system the right thing?" |

**Systems Engineers** integrate multiple subsystems to create a functioning system as a whole. Their main concerns are requirement specification validity, interface design, and verification methods.

**System Architects** define what should be built in the first place and why it has value. Their main concerns are technical strategy, business value, and long-term direction.

In practice, these two roles are often combined, and there's no clear boundary. Particularly in system research and concept exploration phases, both perspectives are necessary.

### Why "System Architect"?

This raises a question: "Should I identify as a 'Systems Engineer' or a 'System Architect'?"

I choose the term System Architect **to clarify my strengths and direction**.

This relates to **how language shapes thinking**:

- **When identifying as "Systems Engineer"**:
  - Attention focuses on system consistency, verification, and integration
  - "Does it work correctly?" becomes the primary concern
  - Technical optimization tends to be central

- **When identifying as "System Architect"**:
  - Attention focuses more on strategy, value, and direction
  - "Is it the right thing?" becomes the primary concern
  - Bridging business and technology becomes central

This isn't about superiority. **It's a choice about which perspective you want to develop yourself in**.

In my case:
- From system research and requirements definition experience, I have strengths in thinking about "what should be built"
- I'm interested in bridging business value and technical strategy

For these reasons, the term **System Architect** resonates with me. I believe this term guides my thinking and actions in the right direction.

### Defining "The Right Thing"

Everything I've discussed in previous articles connects here:

**1. Defining correctness** ([Between Safety and Value: Defining 'Correctness' Through Nine Years of Journey](/posts/defining-correctness-nine-years-journey/))
- Clarify assumptions
- Visualize trade-offs
- Establish "correctness" in context

For example, when designing a "safe lane change assist function," what is "correct"?
- Never causing an accident? (Technically impossible)
- Users feeling comfortable? (Trade-off with safety)
- Meeting regulations? (Minimum requirement)

Architects organize these constraints and values, defining "in this context, this is correct."

**2. Understanding safety as relationships** ([Why Safety During Manual Driving Matters More Than During Autonomous Driving](/posts/why-l0-more-important-than-l2/))
- Judge systems not in isolation but within context
- Understand interactions between system and environment

In Level 2 ADAS, not just system performance alone, but the cooperative relationship with the driver is crucial. "Technically possible" and "actually safe" are separate issues.

**3. Distinguishing knowledge from thinking** ([Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain](/posts/beyond-frameworks-adas-strategy-under-uncertainty/))
- Don't rely solely on frameworks
- Cultivate independent judgment
- See through to the essence

Existing best practices may not apply to your product. You need the ability to understand the essence and judge according to the situation.

**4. Drawing strategy amid uncertainty** ([Refining Decision-Making Through Action: How to Create "Fast and Accurate Judgments" with the 5-Layer Decision Framework](/posts/5-layer-decision-for-fast-action/))
- Create structures that can adapt when assumptions change
- Decision-making framework in uncertain environments

In ADAS development, uncertainty constantly exists—regulations change, technology evolves, user expectations shift. Drawing flexible strategies within this is the architect's role.

**These perspectives form the foundation for "building the right thing."**

## The Value of Architects in the AI Era

ChatGPT, Copilot, Cursor...
**Implementation automation is advancing rapidly.**

So will engineers' value disappear?
**No, rather the role is changing**.

Over the past year, I've started using AI tools daily. Code generation speed has definitely increased. But simultaneously, other challenges have become clear.

**AI excels at "how to build" but cannot judge "what should be built"**. The final decision authority on whether something is good or bad currently rests with humans.

### Changing Value

**Declining value:**
- Routine coding
- Boilerplate code generation
- Simple bug fixes
- Implementation from documentation

These are areas where AI can already respond adequately.

**Rising value:**
- Judging what should be built
- Defining value
- Making trade-off decisions
- Coordinating among stakeholders
- Overall system design
- Clarifying and verifying assumptions

These are areas requiring contextual understanding and strategic thinking, which are difficult for AI.

**This is why the role of System Architect is increasing in importance.**

The more AI substitutes implementation, the more valuable people who can define "what to build and what not to build" and "why to build it" become. Because while AI narrows the gap in implementation speed, the difference in judgment quality remains dependent on humans.

## Five Essential Capabilities for Architects

So what specific capabilities are required of System Architects? I believe these five are crucial:

### ① Ability to Abstract

The ability to structure complex problems and see through to the essence.

For example, articulating the essential constraints of Level 2 in ADAS development. The seemingly simple constraint "the driver is responsible" actually has broad implications:
- UI design principles
- Warning system behavior
- Marketing messages
- Scope of legal liability

Architects need to see through to the essential structure behind surface requirements and explain it to stakeholders.

### ② Ability to Integrate

The ability to connect technology, business, regulations, and users.

Like the "5-layer decision framework" introduced in [Refining Decision-Making Through Action: How to Create "Fast and Accurate Judgments" with the 5-Layer Decision Framework](/posts/5-layer-decision-for-fast-action/), integrate information from different layers to make globally optimal judgments.

In actual development:
- Engineers consider "is it technically feasible?"
- Business side considers "will it sell?"
- Quality assurance considers "is it safe?"
- User support considers "is it usable?"

The architect's role is to integrate these perspectives and find the optimal solution overall. A perspective that sees the entire system, not partial optimization, is required.

### ③ Ability to Define

The ability to create "correctness" ([Between Safety and Value: Defining 'Correctness' Through Nine Years of Journey](/posts/defining-correctness-nine-years-journey/)).

Clarify assumptions ([Refining Decision-Making Through Action: How to Create "Fast and Accurate Judgments" with the 5-Layer Decision Framework](/posts/5-layer-decision-for-fast-action/)) and make trade-offs explicit. The ability to define "in this context, this is correct" in situations without a single answer.

For example, suppose there's a requirement for "response time within 100ms." The architect asks:
- Why 100ms? (Verify the rationale)
- If we can't meet 100ms, what do we sacrifice? (Trade-offs)
- How do we measure 100ms? (Clarify definition)
- Who is this requirement for? (Confirm value)

Through such questions, transform vague requirements into clear decision criteria.

### ④ Ability to Communicate

Communication ability is the foundation for architects. Particularly important is the ability to change language for each stakeholder.

Even for the same system, you need to change how you communicate depending on the audience:
- To engineers: Architecture diagrams, technical trade-offs, implementation difficulty
- To management: Cost, schedule, business risks
- To users: Experience, value, peace of mind

Excellent architects can explain at appropriate abstraction levels and in appropriate language for the audience while understanding technical details.

### ⑤ Ability to Judge

The ability to decide with incomplete information.

You can't wait until everything is clear. In actual development:
- Make 80% confidence judgments with 70% information
- Pivot quickly when you realize mistakes
- Take responsibility for those judgments

What's important is making "correctable judgments" rather than "perfect judgments." As stated in [Refining Decision-Making Through Action: How to Create "Fast and Accurate Judgments" with the 5-Layer Decision Framework](/posts/5-layer-decision-for-fast-action/), if you clarify assumptions, you can review judgments when assumptions collapse.

## My Evolution

Looking back, my own career has been a process of gradually acquiring an architect's perspective.

### Early Period (Years 1-3): Starting with System Research

My career actually didn't start as a typical implementation engineer, but with a **system research project**.

My main work was investigating technologies and functions needed to achieve advanced automation, and examining requirement specifications. Rather than writing code, my days were spent thinking about "what's needed" and "what should be."

My concerns at the time:
- Is this technology feasible?
- What should the requirement specifications be?
- Consistency with existing technology?
- Future extensibility?

Looking back, this was extremely valuable experience. Because **I could learn the perspective of "defining the right thing" early in my career**.

### Middle Period (Years 4-6): Being Drilled on "Why"

During this period, I was assigned to feature development projects. And **various senior engineers thoroughly drilled into me the importance of thinking about "why."**

Questions from seniors:
- "Can you explain why this feature is necessary?"
- "Does it really solve users' problems?"
- "What's the rationale for this implementation decision?"
- "Did you consider alternatives?"

Honestly, at first I sometimes found it tedious. But this attitude of continuously asking "why" became the foundation for later architect thinking.

What I realized during this period:
- Even if technically implementable, things without value shouldn't be built
- Clarifying who the feature is for is important
- Judgments always need rationale
- The seniors were trying to help me develop "thinking ability"

This period's experience became the foundation for later ability to "define the right thing."

### Recent Years (Years 7-9): Refined in Mass Production Development

During this period, I entered the mass production development phase. Unlike R&D, this was an environment that **strongly demanded rapid decision-making and accountability**.

What changed in mass production development:
- Decision speed is required (limited deliberation time)
- Need to clearly explain judgment rationale
- Stakeholders increase, coordination becomes complex
- Trade-off judgments occur daily

In this environment, I naturally developed thinking patterns like:
- Is this feature aligned with long-term strategy?
- How do we respond when assumptions change?
- How do we coordinate trade-offs among stakeholders?
- What's the balance between technical debt and new features?

The decision-making framework introduced in [Refining Decision-Making Through Action: How to Create "Fast and Accurate Judgments" with the 5-Layer Decision Framework](/posts/5-layer-decision-for-fast-action/) is something I organized in my own way to make "fast yet explainable judgments" in mass production development.

**Important realization:**
Architects don't "become"—rather, in trying to meet field demands, you "realize you've become one." There's no clear boundary.

## Global Perspective

In different cultures and organizations, technical roles also differ. This was an important discovery as I consider a global career.

### Product-Focused Organizations (Especially US Tech Companies)

Roles are clearly separated:
- **Product Manager (PM)**: Value definition, roadmap planning
- **Staff/Principal Engineer**: Technical strategy, architecture
- **Engineering Manager (EM)**: Team operations, talent development

Each role has specialization and collaborates to create products. Architect work is mainly handled by Staff-level and above engineers.

### Engineering-Focused Organizations (Common in Japanese Companies)

In contrast, Japanese companies have blurred boundaries, with engineers taking on broad roles:
- Handle both implementation and strategy
- May include PM-like work
- System Architect role is context-dependent

In this environment, there's both the risk of becoming a "jack of all trades" and the opportunity to gain "broad perspective."

### My Choice

**What's important is understanding which role you can provide value in.**

In my case:
- I realized I'm better at strategy and definition than implementation
- I want to contribute to "building the right thing"

This isn't "escape" from my current environment, but **a strategic choice to leverage my strengths**.

By combining the broad perspective cultivated in Japanese organizations with the clarity of global role separation, there's potential to create even greater value.

## Advice for Aspiring Architects

If you're interested in "building the right thing," the following advice might help:

### 1. Have "Depth" in a Specific Domain

Before broadening, first acquire "depth" in some domain. However, this "depth" doesn't necessarily mean only implementation experience.

**Depth comes in multiple forms:**
- **Implementation depth**: Coding experience in specific technologies
- **System understanding depth**: Experience in requirement specifications and overall design
- **Domain knowledge depth**: Expertise in specific fields (ADAS, finance, healthcare, etc.)
- **Problem-solving depth**: Experience facing complex challenges

What's important is **having "non-superficial understanding" in some domain**.

In my case:
- Through system research and development in early and middle career, I deepened understanding of overall AD/ADAS architecture
- Implementation experience was limited, but I developed a sense of "what's feasible and what's difficult"
- This "system understanding depth" became the foundation for later judgment ability

**It's okay without extensive implementation experience.** What's important is deeply understanding "why things are the way they are" in some domain.

### 2. Keep Asking "Why"

Develop the habit of constantly asking "why?":
- Why choose this technology?
- Why this timing?
- Why is this feature necessary?

This habit cultivates an architect's perspective. It's fine if you don't find answers initially. What's important is continuing to ask.

### 3. Take Interest in Adjacent Domains

Look beyond just technology to surrounding areas:
- **Business strategy**: How technical decisions affect business
- **User psychology**: Even technically excellent solutions are meaningless if not used
- **Regulatory environment**: Essential especially in fields like ADAS
- **Organizational culture**: The same technology may be adopted or rejected depending on the organization

Understanding these enables better judgments.

### 4. Develop Writing and Speaking Habits

Practice articulating your thoughts. I recommend creating a system like the one introduced in [Building an Automated Bilingual Blog System with Obsidian: Going Global in Two Languages](/posts/automated-bilingual-blog-system/) for continuous output.

Effects of writing:
- Notice ambiguities in your understanding
- Organize your thinking
- Receive feedback
- Create lasting records

I'm clarifying my own thinking through this blog article series.

### 5. Build Your Own Framework

Don't avoid problems without answers. Rather, **building your own judgment framework** within that uncertainty is important.

**Why do you need your own framework?**

Existing frameworks (e.g., TOGAF, C4 model, ADR) are useful, but insufficient alone. Reasons:

1. **Context dependency**: Your organization, product, and domain are unique. Existing frameworks may not apply directly.

2. **Deepening thinking**: Through building frameworks yourself, you deeply understand "why these decision criteria are necessary."

3. **Reproducibility**: With your own framework, you can make consistent judgments in similar situations. It also becomes easier to explain to others.

4. **Evolvability**: Frameworks you create can be improved through experience. You can learn from failures and refine them into better judgment structures.

The decision-making framework introduced in [Refining Decision-Making Through Action: How to Create "Fast and Accurate Judgments" with the 5-Layer Decision Framework](/posts/5-layer-decision-for-fast-action/) is also something I built from my development experience. While referencing existing frameworks, I customized it for the ADAS development context.

Practical tips:
- Start small: First articulate one judgment pattern
- Record failures: Reflect on judgments that didn't work
- Continuously improve: Frameworks are living things

The ability to judge amid uncertainty is an architect's true value. And that ability is honed by having your own framework.

## What I Believe

In the modern era where technology becomes more complex and uncertainty increases, **the value of System Architects is rising ever more**.

The more AI substitutes implementation, the more value rises for judgment of what should be built, value definition, and strategic thinking.

**Every perspective I've discussed in previous articles is actually a System Architect's perspective.**

And importantly, anyone can acquire this perspective. What's needed is continuous learning and practice.

I didn't have special talent. I just kept asking "why?" for nine years, learned from failures, and gradually broadened my perspective.

---

**Engineers skilled at implementation are needed. But equally, architects who define value are needed.**

Both have equal value.

What's important is understanding your strengths and finding where you can leverage them.

I want to contribute to "building the right thing." That's why I understand I'm suited to be a System Architect.

And through this blog, I want to connect with and learn from people who think similarly.

**What about you?**

Are you an engineer passionate about "how to build"?
Or an architect who wants to define "what to build"?

Whichever you choose, by mastering that path, you can create great value.

**Choose what suits you and what you're good at.**

I hope this article serves as an opportunity to think about your own strengths and direction.