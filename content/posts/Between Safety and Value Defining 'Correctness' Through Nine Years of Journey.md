+++
created = "2025-11-03"
title = "Between Safety and Value: Defining 'Correctness' Through Nine Years of Journey"
author = "Takuya Niioka"
draft = false
tags = ["engineering-philosophy", "system-design", "decision-making", "safety", "product-development"]
slug = "defining-correctness-nine-years-journey"
categories = ["Engineering Philosophy", "System Design", "Decision Making"]
description = "Lessons on the essence of "safety" and "value" learned from nine years of system development experience. On the importance of defining "correctness" beyond technical accuracy."
canonical_url = "https://yourblog.com/en/posts/defining-correctness-nine-years-journey"
date = "2025-11-03T23:13:48+09:00"
+++

**[Disclaimer]**  
The content of this article represents the author's personal views and does not reflect the official position of any organization. It does not refer to any specific projects or products.

---


## Prologue: The "Why" I Almost Lost in Technology

For nine years as a professional, I've been involved in developing systems where safety is paramount. These were years spent constantly facing evolving technology while pondering what lies behind it: "What is safety?" and "What is the relationship between technology and people?"

When I first joined the company, I was eager to absorb as much knowledge as possible. I devoured specialized books on requirements engineering and system design, studied modeling techniques, and immersed myself in structuring and understanding complex requirements.

Every day was a struggle with new knowledge. I read through standards documents, tried to understand design methodologies, and wrestled with architectural thinking.

However, gradually through that learning, I came to feel that **"why we build it" is a far more difficult question than "what to build."**

For example, imagine a situation where you need to determine the operating range of a function. The specification says, "Under condition A, execute process B." That's understandable. But why that condition? Why not a different condition? What criteria is that decision based on?

When answering such questions, technical knowledge alone is insufficient.

---

## Period of Challenge and Exploration (Years 1-4)

In the early days, I was overwhelmed by the depth of technology, yet proceeded with projects through trial and error. I believed without question that accurately meeting each requirement was "good work."

**A Moment of Concrete Struggle:**

On one project, I needed to determine the timing of a warning system. Too early and it would be disliked as a false alarm; too late and it wouldn't serve its purpose.

- What's the system's detection accuracy?
- What's the user's reaction time?
- How do environmental conditions affect it?
- What do the requirements specify?

I gathered these data points, plugged them into formulas, and derived the "optimal solution." But during actual verification, I realized: **The mathematically optimal solution and the timing where people feel "secure" don't necessarily align**.

No matter how much I designed according to requirements, there were moments when I couldn't tell if it was "truly contributing to safety" or "creating a meaningful experience for users."

At this time, I realized: **The meaning of the word "safety" is not merely risk avoidance**. It's directly connected to whether people and systems can build a trusting relationship—that is, whether people feel they can "trust and rely on" the system.

**The Duality of Safety:**
1. **Objective Safety**: Statistical metrics, physical performance, system reliability
2. **Subjective Security**: The sense of trust users feel, understanding of the system, predictability

Development involving safety must satisfy both. No matter how statistically excellent, if users feel "anxious" and don't use the system, that technology might as well not exist.

Pursuing safety means not just removing people's anxiety but also creating security. This realization determined the direction of my subsequent career.

---

## Period of Reexamining Value (Years 5-7)

As I gained experience, I had more opportunities to observe industry trends and other companies' initiatives.

**Different Approaches Observed in the Industry:**
- Approaches prioritizing rapid market entry
- Approaches emphasizing thorough verification
- Approaches using phased releases for learning

When I first observed these differences, I felt anxious. "Is our approach correct?" "Wouldn't a different approach be better?"

However, I gradually came to understand: **Each approach has its own values**. And I realized that defining and embodying those "values" is the most important work as an engineer.

**Contrasting Values:**

```
Approach A:
"Launch to market first, improve with feedback"
→ Advantage: Fast market learning
→ Risk: Initial quality issues

Approach B:
"Launch only after thorough verification"
→ Advantage: High quality and reliability
→ Risk: Delayed market entry
```

Which is correct? The answer is "both are correct."

What matters is **clearly defining "which values we choose" as an organization**. And maintaining consistency in that choice.

---

```text
+----------------------+------------------------------+
|  Technical Focus     |      Meaning Focus           |
+----------------------+------------------------------+
| How does it work?    | Why realize it?              |
| (Function)           | (Value)                      |
+----------------------+------------------------------+
| Define development   | Define value criteria        |
| goals                |                              |
| "Specification"      | "Correctness"                |
+----------------------+------------------------------+
```

This diagram represents the contrast I became most acutely aware of during this period.

The left side, "Technical Focus," is the domain most engineers excel in. Reading specifications, writing design documents, implementing, and executing tests. These have clear procedures and relatively clear criteria for good or bad.

However, the right side, "Meaning Focus," is different. "Why is this function necessary?" "What value does it deliver to users?" "What do we really want to achieve?"—These questions have no single correct answer.

**For Example: Decisions About a Control Function**

Technical Perspective:
- At what timing should it operate?
- What level of detection accuracy is needed?
- Within how many milliseconds should processing delay be kept?

Value Perspective:
- Is this function to prevent users' "carelessness"?
- To what extent should the system intervene so it doesn't feel "overprotective"?
- How do we balance false positives with user experience?

The former is measurable, but the latter is a value judgment. And without clarifying the latter, you cannot determine the numbers for the former.

---

## Stage of Integration (Years 8-9)

Around my eighth year, I finally understood where my interests lie. It's **"the structure of value judgment" more than technology itself**.

Any development has multiple "correct answers." If you prioritize cost, one design becomes correct; if you prioritize comfort, a different answer emerges. In other words, **technology is always subordinate to value judgment**[^1].

[^1]: Value judgment is the act of articulating what results an organization or individual considers good. Design philosophy and product philosophy are its concrete forms.

**Example of Value Judgment: Settings for a Function**

| Values | Setting | Reason | Trade-off |
|--------|---------|---------|-----------|
| Safety First | Conservative | Allows for operational margin | Users may feel inconvenience |
| Convenience Focus | Aggressive | Emphasizes user experience | Smaller safety margin |
| Balanced | Variable | Adjusts to situations | Complex logic, harder to predict |

Which to choose? That's nothing other than **defining "our correctness."**

What I felt in this process was that those who can clearly articulate "what is our correctness" are the ones who can truly lead engineering.

**The Importance of Verbalization:**

Engineers often tend to think "they'll understand without words." However, when operating as an organization, ambiguity is fatal.

- Even if you say "prioritize safety," interpretations differ among people
- Even saying "value user experience," there are countless priorities
- Saying "don't compromise quality," it's unclear what's acceptable

Therefore, **verbalizing values, sharing them within the organization, and making them function as decision criteria** is necessary.

Even with technology to protect safety, you'll lose direction if you misidentify what to protect. That's why defining values—articulating as an organization "what safety means"—becomes the starting point of everything.

**What I Learned:**

Excellent engineering leaders are not just proficient in technology but are **people who continuously ask "why" and can define "correctness."**

They ask "what are we really trying to achieve?" in the midst of technical discussions. Before diving into specification details, they confirm "what value does this function deliver to users?"

And above all, **they maintain consistency in decisions**. They verbalize, share, and practice values so that decision criteria don't change between today and tomorrow.

---

## Three Lessons Learned

### 1. Not "Searching for Correctness" but "Defining Correctness"

In real development, there's no single correct answer. Therefore, we need to clarify what values we prioritize and make decisions based on those criteria.

**Concrete Approach:**

**Step 1: Verbalize Values**
```
Example values in development:
1. Safety: Prioritize protecting human life
2. Reliability: Provide systems users can use with confidence
3. Transparency: Enable users to understand system behavior
4. Continuous Improvement: Constantly evolve through feedback
```

**Step 2: Translate into Decision Criteria**
```
Criteria for adding features:
- Does this feature enhance safety? (Value 1)
- Can users predict system behavior? (Value 3)
- Does it compromise reliability? (Value 2)
```

**Step 3: Maintain Consistency**

Don't easily change values once defined. When changing, discuss organization-wide and share clear reasons.

More than technical correctness, **value consistency** generates trust.

This applies not only to user trust but also to trust within the organization. When a leader's decision criteria are consistent, team members can confidently delegate decisions.

### 2. Safety is Not a "Function" but a "Relationship"

Safety is not the completeness of a system but the result of a trusting relationship with people. No matter how sophisticated the control, if users cannot "believe in it," it's not safe.

**Case Study: When System Behavior Isn't Understood**

Even when technically operating correctly, situations occur where users feel "I don't understand why it acted that way."

System's Judgment:
- Detected situation
- Calculated risk
- Operated because threshold was exceeded

User's Perception:
- "I don't understand why it acted that way"
- "The system malfunctioned"
- "I'll turn it OFF because I can't trust it"

In this case, the system was operating "correctly." However, the **perception gap** with the user damaged trust.

**Solutions:**
1. Visualize the system's reasoning
2. Provide information at timing users can understand
3. Clearly communicate system limitations

Safety is the "quality of relationship" born at the intersection of design philosophy and human understanding.

**Importance of Human-Centered Design:**

In system development involving safety, we need to place **how humans feel** at the center of design, not just technical performance.

- Is system behavior predictable?
- Is information provision timing appropriate?
- Is there room for user intervention?
- Are system limitations clearly communicated?

These are domains not directly addressed by standards, yet they're essential elements for actual safety.

### 3. Knowledge is a Tool, Thinking is the Axis

Modeling techniques, requirements definition, design documents—these are all tools to structure thinking. What matters is using tools to clarify "the logic of thinking."

**Concrete Example: Utilizing Modeling**

Modeling is a technique to visualize system structure and behavior. However, being able to use modeling techniques and being able to do good system design are different things.

**Purpose of Using Modeling:**
- Visualize complex systems
- Facilitate communication among stakeholders
- Discover requirement gaps or contradictions early

However, judging **what should be modeled** is done by humans, not tools.

**Having an Axis of Thinking:**

```
What is good design?
↓
Not just meeting requirements, but flexibly responding to future changes
↓
Which parts are likely to change, which are stable?
↓
Abstract changeable parts and separate with interfaces
↓
Visualize structure with models and verify through reviews
```

Tools are the final step. The initial thought process is the essential work of engineers.

The ability to give form to thinking is what I now feel is an engineer's true fundamental strength.

**Importance of Mental Models:**

Experienced engineers have "patterns of good design" in their minds. These are mental models learned from past successes and failures.

- What structure is maintainable?
- What design has high extensibility?
- What decisions won't lead to regret later?

It's important to express these mental models using tools and share them with the team.

---

## Toward the Next Ten Years

What I learned over these nine years was an attitude of asking **"what is safety?"** beyond technology. Safety is not completion but a value that continues to be updated.

**Future of System Development:**

- Increased complexity from full-scale introduction of AI/machine learning
- Transition to advanced automation
- Growing importance of security
- Progress in coordinated control
- Implementation of ethical judgments

Technology continues to evolve. However, **the fundamental question of "how to build relationships between people and technology" remains unchanged**.

Over the next ten years, more than polishing technology, I want to explore "mechanisms where people and technology can grow together." In that process, I want to develop "the power to define correctness" to an even higher dimension.

**My Next Challenges:**

1. **Framework Value Judgment**: Systematize the process of defining "correctness" as an organization
2. **Acquire Global Perspective**: Learn how safety is perceived in different cultures
3. **Nurture Next Generation Engineers**: Root a culture of asking "why" in the organization
4. **Academic Exploration**: Organize practical experience theoretically and disseminate it

If this article can be a light for someone who continues thinking between safety and value while lost daily, that would be my "correctness."

---

## Finally: A Message to Readers

**What is the "question without an answer" you're facing now?**

In engineering fields, we're pressed for decisions every day. Many of them are questions not found in textbooks.

At that time, **what are your decision criteria?**

If you're not yet clear, I hope this article becomes a trigger for thinking.

And if you already have your own "correctness," please verbalize and share it. The engineering community evolves through such exchanges of knowledge.

**With gratitude for nine years.**