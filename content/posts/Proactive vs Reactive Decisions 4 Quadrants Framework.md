+++
created = "2025-11-28"
date = "2025-11-29T01:02:00+09:00"
title = "Proactive vs Reactive Decisions: 4 Quadrants Framework"
author = "Takuya Niioka"
draft = false
portfolio = ["[[Portfolio_Blog]]"]
tags = ["decision-making", "strategy", "system-design", "autonomous-driving-systems", "initiative"]
slug = "four-quadrants-of-decision-making"
categories = ["Engineering", "Decision Making", "Strategy"]
description = "Master proactive decision-making with clear criteria and strategic timing to avoid reactive responses and stay ahead in product development."
lang = "en"
publishDate = "2025-11-29T01:02:04+09:00"
+++

## 3-Line Summary

- **Whether you can take the initiative depends on two axes: "clarity of decision criteria" and "design of decision timing"**
- **Clear criteria enable proactive decisions; unclear criteria lead to reactive responses. Designing decision timing creates planfulness**
- **Even excellent decision criteria become obsolete with environmental changes. A mechanism for regular review is essential**

---

## Why Do People Fall Behind?

In the previous article ([Prioritizing Multiple Options: Switching Criteria by Context](/posts/prioritization-under-multiple-objectives/)), I explained techniques for prioritizing among multiple options. However, even if you can determine priorities, if those are "reactive decisions made after falling behind," your hard work becomes meaningless.

In product development, we often see situations like these:

- Starting investigations in a panic after competitors launch products
- Considering response methods after regulations are decided
- Reviewing designs after systems fail
- Considering response methods after complaints accumulate

So how can we escape from such reactive responses and make proactive decisions consistently?
What's the difference between organizations/people who can take the initiative and those who fall behind? Is it a difference in capability?

No, I believe it lies in **the difference in "decision design."**

In this article, I've organized the decisive differences between proactive and reactive decisions along two axes.
I'll also explain how to design decisions to consistently take the initiative.

---

## Two Axes That Determine Decisions

Whether you can take the initiative or fall behind is determined by the combination of two axes.

| Axis | Definition | Components |
|---|---|---|
| **Decision Criteria** | What to aim for and what to value | Direction to pursue, values to cherish, judgment rules |
| **Decision Timing** | Design of when to decide | Time-based, metric-based, event-based |

The first axis is **decision criteria**. This is whether what you aim for, what you value, and how you judge are clearly defined, such as "safety first" or "hybrid strategy."

The second axis is **decision timing**. This is whether you've designed in advance when to make decisions, such as "quarterly reviews" or "improvement when bug rate exceeds 5%." You can design based on three triggers: time, metrics, and environmental changes.

### Comparison of the Two Axes

#### Differences Based on Presence of Decision Criteria

| State | Clear Decision Criteria | Unclear Decision Criteria |
|---|---|---|
| **Example** | Safety first, hybrid strategy | While watching competitors, problem response |
| **Result** | ✓ Quickly narrow down, no hesitation | ✗ Think from scratch, slow |

With clear decision criteria, you can quickly narrow down options. No hesitation. Conversely, with unclear criteria, you must think from scratch each time, making decisions slow and prone to inconsistency.

#### Differences Based on Presence of Decision Timing

| State | Timing Designed | Timing Not Designed |
|---|---|---|
| **Example** | Quarterly review, response when bug rate exceeds 5% | When it occurs to you, after problems arise |
| **Result** | ✓ Clear, planned | ✗ Unclear, instant decision or completely reactive |

With designed decision timing, the timing is clear and you can act planfully. Conversely, without timing design, you oscillate between instant decisions when something occurs to you and completely reactive responses after problems arise.

Combining these two axes creates **four patterns** of decision-making, which determine whether you can take the initiative or fall behind.

---

## The Four Quadrants of Decision-Making

Combining the two axes classifies decisions into four quadrants.

**Decision criteria** determine direction, and **decision timing** determines execution timing. This combination determines whether you can take the initiative or fall behind.

![Four Quadrants of Decision-Making](/figures/decision-quadrants-framework.svg)

### Which Quadrant Was Your Recent Decision In?

Let's examine each quadrant with concrete examples. Consider where your decisions fall as you read.

### Characteristics of Each Quadrant

| Quadrant | Characteristics | Example | Result |
|---|---|---|---|
| **Quadrant 1<br>Implemented Initiative** | Determine direction with decision criteria, determine execution timing with decision timing | Quarterly review, improvement when bug rate exceeds 5%, mass production when LiDAR cost ≤$500 | ✓ 6 months ahead of competitors, abundant options, easy team buy-in |
| **Quadrant 2<br>Instant Initiative** | Can make instant decisions because criteria are clear. Most proactive but low planfulness | Instant decision to adopt new technology when it occurs to you, instant job change to attractive field | ✓ Most proactive, breakthrough potential, △ Low planfulness |
| **Quadrant 3<br>Ad-hoc Reactive** | Neither decision criteria nor timing. Completely reactive | Panicked response to quality problems, complaints, supervisor's pointing out |  ✗ Completely reactive, no options, high cost, low quality |
| **Quadrant 4<br>Prepared Reaction** | Has decision timing but no criteria. Quick reaction but no direction | 2-week response to competitor's new feature, price cut when share drops 5% | △ Prepared, ✗ Following, cannot differentiate |

The key is moving toward **Quadrant 1 (Implemented Initiative)**. By designing both decision criteria and timing, you can consistently take the initiative in a planned manner.

### Semiconductor Industry Case: Obsolescence of Decision Criteria

There's a case where a company that once led the semiconductor manufacturing industry struggled to respond to environmental changes.

**Initial Decision Criteria:**
- "Manufacturing technology is the source of competitive advantage" (effective strategy in the 2000s)

**Environmental Changes:**
- Rise of foundry companies (TSMC, etc.)
- Rapid growth of GPU/AI chip manufacturers
- Business model changes

**However, because there was no decision timing set for environmental changes:**
- Strategy review didn't progress until market share was lost
- The significant lag became clear around 2020
- Large-scale strategic transformation became necessary

**Lessons from This Case:**
- Even once-successful decision criteria become obsolete with environmental changes
- Designing decision timing for regular criteria review is important
- Event-based decision timing to detect market changes is also necessary

---

## Why Decision Criteria Are Decisive

### The Wall of Decision Criteria

Looking at the four quadrants, did you notice something?
Yes. **The decisive difference is the vertical axis (presence of decision criteria).** Whether you can cross this wall determines everything.

### With Decision Criteria, You Can Take Initiative Even Without Timing Design

Quadrant 2 (Instant Initiative):
Decision criteria present × Decision timing not designed

→ Even at spontaneous timing, you can make instant decisions because you have criteria
→ Overwhelmingly proactive

Example: Visionary entrepreneurs, innovators

### Without Decision Criteria, You Fall Behind Even With Timing Design

Quadrant 4 (Prepared Reaction):
No decision criteria × Decision timing designed

→ Can react quickly at decision timing
→ But no direction, so following
→ Cannot differentiate

Example: Competitor-following companies

### Beware of Decision Criteria "Freshness"

The most important lesson from the semiconductor industry case is that **even excellent decision criteria become obsolete with environmental changes.**

"Safety First" as a decision criterion is certainly important in autonomous driving system development. However, if you cling only to this criterion, you may sacrifice the product appeal customers truly seek (usability, comfort, price competitiveness).

Having decision criteria is a necessary condition, but not sufficient. **Continuously maintaining competitive decision criteria** is fundamentally important.

What's needed for this is a mechanism to review the decision criteria themselves:

- **Time-based**: Review the validity of decision criteria once a year
- **Event-based**: Re-evaluate decision criteria when major market changes occur (competitor's disruptive innovation, major regulatory changes, etc.)
- **Metric-based**: Question decision criteria when indicators like market share, customer satisfaction, or technological competitiveness deteriorate beyond a certain level

Decision criteria are not "set and forget." **It's essential to continuously update them as living criteria.**

### Decision Criteria as a System Architect

As an autonomous driving system architect, what are decision criteria? The following are examples, but they are merely "currently effective criteria" that need review in response to environmental changes.

**Examples of Technical Decision Criteria:**
- "Architecture that doesn't compromise safety"
- "Excellence in sensor fusion"
- "Balance of scalability and maintainability"

**Examples of Strategic Decision Criteria:**
- "Camera + LiDAR hybrid strategy"
- "Focus on Level 2+"
- "Platform for OEMs"

**Examples of Organizational Decision Criteria:**
- "Culture that doesn't tolerate technical debt"
- "Continuous technological innovation"
- "Autonomous teams"

**Don't Forget Customer Value Decision Criteria:**
- "Balance of safety and usability"
- "Balance of cost and performance"
- "Realizing product appeal the market demands"

With these decision criteria clear, you won't hesitate in daily decisions. However, remembering to review them regularly becomes most important.

---

## Implementing Through Decision Timing Design

We've established that decision criteria are important. However, criteria alone don't enable action.

**Why?**

### Decision Criteria Alone Are Too Demanding

Decision criteria: "Safety-first architecture"

But with this alone:
- When and what to do?
- At what timing to decide?
- Who monitors what?

→ Impossible to decide everything "now"
→ Cognitive load is too high

**This is like trying to do everything from high-level design to detailed design at once.**

### Implement Through Decision Timing

Therefore, **decompose decision criteria into decision timing for implementation.**

#### Three Types of Decision Timing

| Type | Definition | Example |
|---|---|---|
| **Time-based** | Decide in advance when to decide | Annual strategy review, quarterly technical review, travel planning 3 months ahead |
| **Metric-based** | Decide which indicators/values trigger decisions | Improvement when bug rate exceeds 5%, mass production when cost ≤$500, monetization at 500 followers |
| **Environmental Change-based** | Decide what events trigger decisions | New technology emerges → 2-week investigation, regulation published → impact analysis, sale → check candidates |

**Time-based** executes periodically like "annual strategy review." **Metric-based** uses thresholds as triggers like "improvement when bug rate exceeds 5%." **Environmental change-based** uses external events as triggers like "investigation when new technology emerges."

By combining these three, you can translate decision criteria into executable form.

### Relationship Between Decision Timing and Information Gathering

Designing decision timing clarifies **what should be continuously monitored.**

#### Information Gathering in Quadrant 1 (Implemented Initiative)

**Time-based Preparation:**
- Continuously accumulate materials for quarterly reviews
- Prepare dashboards for monthly checks

**Metric-based Monitoring:**
- Measure bug rate and test time weekly
- Track LiDAR cost and sensor market prices

**Environmental Change Monitoring:**
- Regular checks of technology trend blogs and papers
- Quarterly review of competitive analysis reports
- Watch regulatory trends

#### Decisive Difference from Quadrant 4 (Prepared Reaction)

Quadrant 4 also monitors the environment, but without decision criteria, it only reacts. In contrast, Quadrant 1 also monitors the environment, but with decision criteria, it can make proactive decisions. This difference separates following from leading.

### Four Implementation Steps

#### Step 1: Define Decision Criteria (Once a Year)

Clarify what to aim for, such as "safety-first architecture" or "camera + LiDAR hybrid strategy."

#### Step 2: Decompose Decision Criteria into Decision Timing

Convert decision criteria into concrete decision timing.

- Time: Technical review every quarter
- Metric: Bug rate exceeds 5% → Improvement week
- Environment: LiDAR cost ≤$500 → Consider mass production

#### Step 3: Create Information Gathering Mechanisms

Establish mechanisms to continuously gather information needed for decision timing.

- Check technology trends monthly
- Track sensor market prices
- Review competitive analysis quarterly

#### Step 4: Decision Timing Runs Automatically

Once mechanisms are running, decisions trigger automatically.

- Quarterly review → Check decision timing → Decide
- LiDAR cost drops → Decision timing triggers → Instant decision

**Result:**
✓ Can take initiative in a planned manner
✓ No hesitation, no delays
✓ Easy team buy-in

---

## How to Move Between the Four Quadrants

I'll explain how to diagnose your current position and move to Quadrant 1 (Implemented Initiative).

### Diagnosing Current Position

First, knowing where you are is the first step. **Answer two questions:**

#### Question 1: Do You Have Decision Criteria?

✓ Decision criteria are clear
✓ Can articulate what you aim for
✓ Can return to criteria when in doubt

→ Yes: Upper half (Quadrant 2 or Quadrant 1)
→ No: Lower half (Quadrant 3 or Quadrant 4)

#### Question 2: Do You Have Decision Timing?

✓ When to decide is determined
✓ Metric/environmental thresholds are designed
✓ Information gathering runs continuously

→ Yes: Right side (Quadrant 1 or Quadrant 4)
→ No: Left side (Quadrant 2 or Quadrant 3)

### Three Movement Patterns

| Movement | Challenge | Solution |
|---|---|---|
| **Quadrant 3→Quadrant 4<br>Ad-hoc Reactive→Prepared Reaction** | Completely reactive, respond after problems arise | Design decision timing (quarterly competitive analysis, countermeasure meeting when share drops 5%). Start information gathering.<br>→ Can react slightly faster (**but still following**) |
| **Quadrant 4→Quadrant 1<br>Prepared Reaction→Implemented Initiative [MOST IMPORTANT]** | No direction, cannot differentiate, swayed by competitors | ① Define decision criteria (✗ "Don't lose to competitors" → ✓ "Safety first," "Hybrid strategy")<br>② Link timing to criteria<br>③ Change quality of information gathering (competitors → technology trends)<br>→ Can take initiative |
| **Quadrant 2→Quadrant 1<br>Instant Initiative→Implemented Initiative** | No planfulness, organization can't keep up, high risk | ① Decompose decision criteria into timing (improvement when bug rate exceeds 5%, quarterly review)<br>② Systematize information gathering (individual intuition → team monitoring)<br>→ Planned initiative, teamwork |

#### Quadrant 3→Quadrant 4: The First Step

To escape from the most dangerous Quadrant 3 (Ad-hoc Reactive), first design decision timing. Even with unclear decision criteria, designing timing enables preparation. However, don't forget this is still following.

#### Quadrant 4→Quadrant 1: The Most Important Movement

This is the most important movement. By defining decision criteria, you shift from following to leading. The key is having your own direction like ✓ "Safety first" or "Hybrid strategy," not reactive criteria like ✗ "Don't lose to competitors."

#### Quadrant 2→Quadrant 1: From Individual Play to Teamwork

Instant initiative is proactive but difficult to sustain in organizations. By decomposing decision criteria into decision timing and systematizing information gathering, you can take initiative in a planned manner as a team without relying on individual intuition.

---

## Summary - Decision Design Is the Essence

Whether you can take the initiative or fall behind is not a difference in capability. **It's a difference in whether you design decisions.**

Decision design has two axes. First is the clarity of decision criteria, second is the design of decision timing. The combination of these two axes creates four quadrants.

**Quadrant 1 (Implemented Initiative)** is the state where both decision criteria and decision timing are designed. This is most powerful, enabling you to consistently take initiative in a planned manner. **Quadrant 2 (Instant Initiative)** has clear decision criteria but undesigned decision timing. It's overwhelmingly proactive but tends toward individual play and is difficult to realize organizationally.

On the other hand, **Quadrant 4 (Prepared Reaction)** has designed decision timing but unclear decision criteria. There's preparation but it's a following strategy that cannot differentiate. **Quadrant 3 (Ad-hoc Reactive)** has neither decision criteria nor decision timing, is completely reactive, and is the weakest state.

The decisive difference lies in the vertical axis—the presence of decision criteria. With decision criteria, you can take initiative; without them, you fall behind. The horizontal axis of decision timing is an implementation refinement. Designing decision timing makes it planned and sustainable; without design, you oscillate between instant decisions and complete reactivity.

However, decision criteria are not "set and forget." Because they become obsolete with environmental changes, a mechanism for regular review is essential.

---

## Actions You Can Take Today

Proactive decision-making is not talent. It can be designed. Start small.

### By Current Position: First Step You Can Take Today

Concrete actions to move from your current position toward Quadrant 1 (Implemented Initiative).

| Current Quadrant | 1 Action You Can Take Today | Concrete Example |
|---|---|---|
| **Quadrant 1<br>Implemented Initiative** | Check decision criteria freshness | Schedule annual review of decision criteria validity |
| **Quadrant 2<br>Instant Initiative** | Set one decision timing | Register quarterly review in calendar, decompose decision criteria into timing |
| **Quadrant 3<br>Ad-hoc Reactive** | Write down 3 decision criteria | Write on paper what you aim for, what you value |
| **Quadrant 4<br>Prepared Reaction** | Define unique direction | Rewrite ✗ "Don't lose to competitors" → ✓ "Differentiate with XX" |

### Common to Everyone: What to Do Today

#### ① Write Down 3 Decision Criteria

- What values do you (or your team) cherish?
- What are you aiming for?
- When in doubt about decisions, what do you use as criteria?

Paper or smartphone notes are fine. First, articulate them.

#### ② Decide One "When to Decide"

- Review strategy every quarter
- Confirm priorities at the beginning of each month
- Make it improvement week when bug rate exceeds 5%

Even just one is fine. Decide decision timing and put it in your calendar.

That's all. You don't need to aim for perfection. Start small and improve quarterly, and you'll surely become "someone who can take the initiative."

---

## Related Articles

- [Prioritizing Multiple Options: Switching Criteria by Context](/posts/prioritization-under-multiple-objectives/)
- [When to Switch Decision Criteria: Trigger Design for System Engineers](/posts/when-to-switch-decision-triggers/)
- [Drawing the Line: What Should System Architects Decide?](/posts/drawing-decision-boundaries/)
- [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/)

---

**[Disclaimer]**  
The content of this article represents the personal views of the author and does not represent the official views of any affiliated organization. The specific examples in the article are simplified models for explanation purposes and may differ from actual product implementations or corporate strategies.