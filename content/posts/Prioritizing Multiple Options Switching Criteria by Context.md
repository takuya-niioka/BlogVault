+++
created = "2025-11-25"
date = "2025-11-27T11:59:09+09:00"
title = "Prioritizing Multiple Options: Switching Criteria by Context"
author = "Takuya Niioka"
draft = false
tags = ["prioritization", "decision-making", "system-design", "ADAS", "project-management"]
slug = "prioritization-under-multiple-objectives"
categories = ["Engineering", "Decision Making"]
description = "Learn how system architects prioritize multiple team initiatives in ADAS development, from AEB improvements to ISO compliance and cost reduction."
lang = "en"
publishDate = "2025-11-27T12:06:00+09:00"
+++

## When Advancing Multiple Initiatives as a Team, Where Do You Start?

In the previous article ([Drawing the Line: What Should System Architects Decide?](/posts/drawing-decision-boundaries/)), I explained the importance of clarifying the boundaries of "what you should decide." As a system architect, defining the scope of judgment that you—not your boss, not your juniors—should make is the first step.

However, just because the boundaries are clear doesn't mean decisions become easy. Rather, new questions emerge.

**"There are multiple initiatives the team should pursue. What should we propose, and in what order?"**

In ADAS development work, we face this question daily.

- AEB performance improvement
- LKA adverse weather response
- ACC comfort improvement in traffic jams
- Next-generation sensor technology research
- ISO 26262 compliance
- Cost reduction initiatives
- Development process improvement
- Technical debt resolution
- New employee training system establishment
- Documentation maintenance

All of these are "important." But we can't do everything simultaneously. Choosing something means abandoning something else.

And what's most difficult is that **this prioritization changes depending on who you're explaining to and what the current situation is**.

- The points you emphasize differ between internal team discussions and proposals to management
- Priorities change between normal times and crisis situations
- Options change between when resources are abundant and when they're limited

This article systematizes prioritization techniques learned from practical experience. In particular, I'll explain a practical approach that many textbooks don't discuss: **"switching judgment criteria by considering who the decision is for and what the current situation is."**

---

## Why Is Prioritization Difficult?

### The Essential Difficulty of Prioritization

Prioritization is difficult for the following reasons.

**Reason 1: Everything appears "important"**

In practice, things that "don't need to be done" don't make it onto the list. Everything on the list is important to someone.

- Sales: "New features are top priority"
- Quality Assurance: "Stability is top priority"
- Finance: "Cost reduction is top priority"
- Engineers: "Resolving technical debt is top priority"

Everyone is right. But we can't do everything at once.

**Reason 2: Multiple judgment criteria exist**

What makes something "high priority"? There isn't just one criterion.

- Urgency (by when is it needed)
- Importance (how much value does it have)
- Feasibility (can we do it now)
- Strategic importance (how does it connect to the future)

And these criteria sometimes contradict each other. Things that are urgent but not important. Things that are important but not urgent. Prioritization is about resolving these contradictions.

**Reason 3: When the situation changes, the answer changes too**

What's even more troublesome is that the "correct priority" changes depending on the situation.

Priorities change between this week and next month. Judgment criteria change between normal times and crisis situations. The points you emphasize change between internal team discussions and reports to management.

**It's not a one-time decision but requires constant review. This is the essential difficulty of prioritization.**

### Common Failure Patterns

Here are three failure patterns commonly seen in practice.

**Failure Pattern 1: Fixating on a single criterion**

If you judge only by "urgency," you end up only responding to immediate problems. Things that are important but not urgent (strategic investment, personnel development, technology research) get postponed, and before you know it, you've fallen behind competitors.

If you judge only by "customer value," technical debt accumulates. Internal improvements that users don't notice are always postponed, and one day suddenly, the system collapses.

A single criterion is easy to understand. But reality is more complex.

**Failure Pattern 2: Inconsistent judgment criteria**

Monday: "Let's prioritize customer value"
Wednesday: "No, emergency response comes first"
Friday: "Isn't cost reduction important?"

When judgment criteria aren't consistent, the team becomes confused. They don't know what to believe and act on. As a result, no one can make decisions, and decision-making becomes paralyzed.

**Failure Pattern 3: The loudest voice wins**

Without clear judgment criteria, decisions become political.

The opinion of someone who loudly insists "This feature is absolutely necessary!" wins. Decisions are made by emotion, not data. As a result, decision-making becomes inconsistent, and later you can't explain "why we did this."

### Conditions for Functional Prioritization

So what's needed for functional prioritization?

**Condition 1: Clear judgment criteria**
Articulate the criteria for what makes something "high priority."

**Condition 2: Clarify who the decision is for**
For customers? For the company? For your own career? Make the beneficiary clear.

**Condition 3: Situational awareness**
Is it normal times or crisis times? Are resources sufficient or limited? Correctly recognize the situation.

**Condition 4: Visualize trade-offs**
Doing this = not doing that. Make explicit what you're abandoning.

**Condition 5: Flexibility**
When the situation changes, change priorities too. It's not over once you decide.

This article proposes a practical framework that satisfies these five conditions.

---

## Five Basic Prioritization Patterns

There are multiple "patterns" for prioritization. It's not that one is correct, but rather it's important to use them appropriately depending on the situation.

First, I'll introduce five basic patterns based on the axes of **"for whom" and "what to emphasize."**

### Pattern 1: Urgency × Importance Matrix

**Philosophy: "Consider both time constraints and importance"**

The most famous is the Eisenhower Matrix. This is essentially **a triage technique**, judging where to allocate limited resources.

```
        Importance
        High  |  Low
    ─────────┼─────────
High |  ①   |  ③
Urgency    |      |
Low  |  ②   |  ④
```

- **①: Urgent and important** → Do now
- **②: Important but not urgent** → Schedule (most important!)
- **③: Urgent but not important** → Delegate
- **④: Neither urgent nor important** → Don't do

**ADAS development example:**

```
①: Emergency response to quality issues (regulatory violation risk)
②: Next-generation technology research (needed in 1 year)
③: Regular meeting material preparation
④: Organizing unread emails
```

**When to use:**
- Personal task management
- Short-term resource allocation
- "What to do today" level decisions

**Advantages:**
- Simple and easy to implement
- Easy to explain
- Easy to debug and test

**Limitations:**
- Definition of "importance" is ambiguous (for whom? from what perspective?)
- Insufficient for medium to long-term strategic decisions
- Doesn't consider the situation

### Pattern 2: Business Value Priority

**Philosophy: "Maximize value for the company"**

Judge by how much this initiative contributes to the company.

**Evaluation criteria:**
- Contribution to revenue
- Cost reduction
- Risk mitigation
- Competitive advantage

**ADAS development example:**

```
High Priority:
- Regulatory compliance (risk of not being able to sell)
- Major customer requirement response (directly linked to sales)
- Feature development with competitive advantage

Low Priority:
- Technically interesting but unclear market needs
- Will be needed eventually but not right now
```

**When to use:**
- Proposals to management
- Allocation of limited budget
- "Which project to invest in" decisions

**Advantages:**
- Easy to explain to executives
- Can be quantified by ROI (return on investment)
- Easy to get budget approval

**Limitations:**
- Tends to favor short-term profits
- Innovation gets postponed
- Risk of decreased engineer motivation

### Pattern 3: Customer Value Priority

**Philosophy: "Maximize value for end users"**

Judge by value to users.

**Evaluation criteria:**
- User experience improvement
- Safety improvement
- Convenience improvement
- Pain point resolution

**ADAS development example:**

```
High Priority:
- LKA performance improvement in adverse weather (many user complaints)
- AEB false positive reduction (damages user experience)
- ACC comfort improvement in traffic jams

Low Priority:
- Internal improvements users don't notice
- Important from engineer perspective but no experience change
```

**When to use:**
- Determining product development direction
- When user feedback is clear
- "What should we build" decisions

**Advantages:**
- High user acceptance
- Directly linked to market evaluation
- Increases team motivation

**Limitations:**
- Technical debt accumulates
- Regulatory compliance gets postponed
- Internal improvements don't progress
- What users say they "want" isn't necessarily right

### Pattern 4: Career Priority

**Philosophy: "Maximize value for your own career"**

Judge by value for your career.

**Evaluation criteria:**
- Skill acquisition (new experience)
- Achievement building (results you can communicate externally)
- Network expansion
- Market value improvement

**ADAS development example:**

```
High Priority:
- New technology (LiDAR) project participation
- Results presentable at conferences
- Collaboration with global teams
- Leading next-generation system design

Low Priority:
- Routine work (familiar tasks)
- Coordination-heavy with unclear results
- Legacy system maintenance
```

**When to use:**
- Personal career strategy
- Choosing between multiple projects
- "Which work to take on" decisions

**Advantages:**
- Can accelerate personal growth
- Increases motivation
- Market value improves

**Limitations:**
- Risk of divergence from organizational goals
- If you only choose "interesting work," the team can't function
- Favors long-term career over short-term results

### Pattern 5: Strategic Balance (Portfolio Thinking)

**Philosophy: "Balance multiple perspectives"**

Judge comprehensively across multiple perspectives rather than a single criterion.

**Four evaluation axes:**
1. **Urgency** (by when is it needed)
2. **Business value** (importance to the company)
3. **Customer value** (impact on users)
4. **Strategic importance** (investment in the future)

**ADAS development example:**

| Initiative | Urgency | Business Value | Customer Value | Strategic Importance | Overall Judgment |
|------|--------|----------|----------|--------------|----------|
| ISO 26262 compliance | High | High | Low | Medium | **High** |
| Next-gen sensor research | Low | Medium | Low | High | Medium |
| LKA adverse weather performance | Medium | Medium | High | Low | **Medium-High** |

**Weighting example:**

```
Situation A: Regulatory compliance deadline approaching
→ Urgency 40%, Business value 30%, Customer value 20%, Strategy 10%

Situation B: New product development phase
→ Urgency 20%, Business value 20%, Customer value 40%, Strategy 20%
```

**When to use:**
- Medium to long-term roadmap development
- Resource allocation optimization
- Stakeholder coordination

**Advantages:**
- Can integrate multiple perspectives
- Can visualize trade-offs
- Can fulfill accountability

**Limitations:**
- Complex implementation
- Need rationale for weighting
- Analysis takes time

---

## Three Supplementary Patterns

The five basic patterns judge by "for whom" and "what to emphasize." However, in practice, another perspective is needed: **"execution constraints."**

The following three supplementary patterns are used in combination with the basic patterns.

### Pattern 6: Dependency Priority

**Philosophy: "Clear what's blocking others first"**

If you prioritize without considering dependencies, rework occurs later.

**Evaluation criteria:**
- What else stops if this task isn't completed
- How many tasks depend on this

**ADAS development example:**

```
High Priority:
- Common interface design for sensor data
  → Multiple feature developments are waiting for this
- Test environment setup
  → All quality verification depends on this

Low Priority:
- Independent improvement initiatives (don't affect others)
```

**When to use:**
- Team development with many parallel tasks
- Technical debt is blocking other development
- Timing decisions for infrastructure setup

**Advantages:**
- Increases overall team productivity
- Prevents rework
- Enables parallel work

**Limitations:**
- Takes time to understand dependencies
- Risk of "non-blocking" tasks being postponed forever

### Pattern 7: Risk Priority

**Philosophy: "Validate high-uncertainty items first"**

If you postpone high-risk tasks, the impact becomes larger when it's too late.

**Evaluation criteria:**
- Technical feasibility is unknown
- High external dependencies (third parties, regulatory changes, etc.)
- Large impact if it fails

**ADAS development example:**

```
High Priority:
- Feasibility validation of new sensor technology
  → If found impossible, need to revise entire plan
- Regulatory trend research
  → Delayed response means can't sell

Low Priority:
- Implementation of features certain to be realized
- Improvements with known technology
```

**When to use:**
- Considering introduction of new technology
- Early stages of high-uncertainty projects
- Want to validate hypotheses early in long-term projects

**Advantages:**
- Can discover failures early
- Minimize rework costs
- Can reduce uncertainty

**Limitations:**
- Definition of "risk" is subjective
- Certain tasks get postponed, making results less visible
- Team may become unstable

### Pattern 8: Quick Win Priority

**Philosophy: "Start with things that show results quickly to build momentum"**

Large results take time. However, by accumulating small successes, you can boost team morale and gain stakeholder trust.

**Evaluation criteria:**
- Small effort (hours to days)
- Visible effects
- Leads to improved team morale

**ADAS development example:**

```
High Priority:
- Build time reduction (2 hours of work cuts it in half)
- Common bug fixes (30 minutes improves customer satisfaction)
- Documentation maintenance (1 day halves new hire onboarding time)

Low Priority:
- Large-scale architecture changes (takes months to see effects)
```

**When to use:**
- Early in project when you want to build trust
- Team morale is down
- Want to show early results to stakeholders

**Advantages:**
- Can show results early
- Team morale improves
- Gain stakeholder trust

**Limitations:**
- Essential problem-solving gets postponed
- Risk of only doing "easy things" and avoiding difficult challenges
- Too focused on short-term results

---

### How to Combine Basic and Supplementary Patterns

Supplementary patterns function as "constraints" on basic patterns.

**Combination examples:**

```
Basic: Developing with Pattern 3 (Customer Value Priority)
  ↓ However...
Constraint: Consider Pattern 6 (Dependencies)
  → First set up common interface, then individual feature development

Basic: Investment decision with Pattern 2 (Business Value Priority)
  ↓ However...
Constraint: Consider Pattern 7 (Risk)
  → First validate technical feasibility, then full investment

Basic: Annual plan with Pattern 5 (Balance)
  ↓ However...
Constraint: Consider Pattern 8 (Quick Wins)
  → Accumulate some small successes initially, then move to major initiatives
```

**Important principle:**
Supplementary patterns don't **replace** basic patterns, they **complement** them

---

### Trade-off Comparison Table for 8 Patterns

What do you gain and what do you sacrifice when choosing each pattern? Here's a summary table of the overall picture.

**[Basic Patterns: For Whom, What to Emphasize]**

| Pattern | What You Gain | What You Sacrifice | Suitable Situations |
| --------------------- | ------------------------------------------- | ----------------------------------------------- | --------------------------------- |
| **Pattern 1:<br>Urgency×Importance** | ✓ Quick decisions<br>✓ Simple implementation<br>✓ Easy to explain | ✗ Lack of strategic perspective<br>✗ Medium to long-term investment postponed<br>✗ Ambiguous definition of "importance" | Short-term decisions<br>Personal task management<br>Crisis response |
| **Pattern 2:<br>Business Value Priority** | ✓ Executive support<br>✓ Easy to get budget approval<br>✓ Can quantify by ROI | ✗ Favors short-term profits<br>✗ Innovation postponed<br>✗ Decreased engineer motivation | Management proposals<br>Budget allocation<br>Investment decisions |
| **Pattern 3:<br>Customer Value Priority** | ✓ Improved user satisfaction<br>✓ Directly linked to market evaluation<br>✓ Improved team motivation | ✗ Technical debt accumulates<br>✗ Regulatory compliance postponed<br>✗ Internal improvements don't progress | Product development<br>Feature prioritization<br>User-focused |
| **Pattern 4:<br>Career Priority** | ✓ Accelerated personal growth<br>✓ High motivation<br>✓ Improved market value | ✗ Divergence from organizational goals<br>✗ Impact on team operations<br>✗ Short-term results less visible | Personal career strategy<br>Project selection<br>Self-investment decisions |
| **Pattern 5:<br>Strategic Balance** | ✓ Integration of multiple perspectives<br>✓ Visualization of trade-offs<br>✓ Can fulfill accountability | ✗ Complex implementation<br>✗ Need rationale for weighting<br>✗ Analysis takes time | Medium to long-term roadmap<br>Resource allocation<br>Stakeholder coordination |

**[Supplementary Patterns: Execution Constraints]**

| Pattern | What You Gain | What You Sacrifice | Suitable Situations |
| -------------------- | -------------------------------------------- | ------------------------------------------- | -------------------------------- |
| **Pattern 6:<br>Dependency Priority** | ✓ Improved overall team productivity<br>✓ Prevents rework<br>✓ Enables parallel work | ✗ Takes time to understand dependencies<br>✗ Independent tasks postponed forever<br>✗ Risk of only infrastructure work | Parallel development<br>Technical debt blocking<br>Infrastructure setup timing |
| **Pattern 7:<br>Risk Priority** | ✓ Discover failures early<br>✓ Minimize rework costs<br>✓ Can reduce uncertainty | ✗ Subjective definition of risk<br>✗ Certain tasks postponed<br>✗ Results less visible | New technology introduction<br>Early stages of high-uncertainty projects<br>Hypothesis validation |
| **Pattern 8:<br>Quick Win Priority** | ✓ Can show results early<br>✓ Improved team morale<br>✓ Gain stakeholder trust | ✗ Essential problems postponed<br>✗ Risk of avoiding difficult challenges<br>✗ Favors short-term results | Early in project<br>Morale is down<br>Trust building needed |

**Important insight:**

What this table shows is that **there is no "perfect pattern."** All patterns have advantages and limitations, and you need to use them appropriately depending on the situation.

**Basic pattern usage examples:**
- In crisis, respond quickly with **Pattern 1**, postpone strategy
- In normal times, emphasize customer value with **Pattern 3**
- For budget approval, emphasize business value with **Pattern 2** to gain executive support
- For annual planning, balance multiple perspectives with **Pattern 5**

**Supplementary pattern combination examples:**
- **Pattern 3 + Pattern 6**: Emphasize customer value while resolving technical debt through dependencies
- **Pattern 2 + Pattern 7**: Make investment decisions by business value while prioritizing risk validation
- **Pattern 5 + Pattern 8**: Plan with balance while building trust with quick wins initially

---

## How to Switch Patterns

So far I've introduced 8 patterns (5 basic + 3 supplementary). However, what's most important is **"which pattern to use when."**

The essence of prioritization isn't the patterns themselves, but **being able to switch patterns according to the situation**.

### Four Triggers for Pattern Switching

Prioritization patterns need to be switched based on the following four triggers.

#### **Trigger 1: Crisis Occurrence**

```
Normal times: Developing with Pattern 3 (Customer Value)
         ↓
Crisis:   Quality issue discovered (regulatory violation risk)
         ↓
Response:   Immediately switch to Pattern 1 (Urgency×Importance)
         ↓
Action:   Invest all resources in problem resolution
         ↓
After recovery: Return to Pattern 3 (Customer Value)
```

**Signs:**
- Regulatory violation risk
- Quality issue discovery
- Delivery deadline crisis
- Budget overrun warning

**Switching judgment criteria:**

"If we continue as is, will it affect business continuity?"
→ YES → Immediately switch to risk priority

**ADAS development example:**

```
Normal times:
Priority 1: LKA adverse weather performance (customer value)
Priority 2: ACC comfort improvement (customer value)
Priority 3: Next-generation technology research (strategy)

After quality issue discovery:
Priority 1: Quality issue resolution (urgency×importance)
Priority 2: Recurrence prevention implementation
Priority 3: Everything else frozen

After problem resolution:
Return to Priority 1
```

#### **Trigger 2: Time Horizon Change**

```
Short-term (this week/month) → Pattern 1 (Urgency×Importance)
Medium-term (this quarter)   → Pattern 3 (Customer Value) or 2 (Business Value)
Long-term (this year onward) → Pattern 5 (Balance) + strategy emphasis
```

**Signs:**
- Quarter transitions
- Project phase transitions
- Roadmap review timing

**Switching judgment criteria:**

"On what time horizon should this decision produce effects?"
→ Short-term → Urgency, effort
→ Medium-term → Customer value, business value
→ Long-term → Strategy, balance

**ADAS development example:**

```
Weekly level (short-term):
Pattern 1 (Urgency×Importance)
→ This week's task priorities

Quarterly level (medium-term):
Pattern 3 (Customer Value)
→ Next feature development priorities

Annual level (long-term):
Pattern 5 (Balance)
→ Roadmap development
```

#### **Trigger 3: Stakeholder Change**

```
Personal judgment        → Pattern 4 (Career)
  ↓
Team proposal      → Pattern 3 (Customer Value)
  ↓
Management approval → Pattern 2 (Business Value)
```

**Signs:**
- Change in reporting line
- Review meetings
- Budget approval process

**Switching judgment criteria:**

"Who are you explaining to?"
→ Self       → Career
→ Team     → Customer value
→ Management → Business value
→ Multiple       → Balance

**ADAS development example:**

```
Personal level (your own judgment):
"Should I join the LiDAR project?"
→ Judge with Pattern 4 (Career Priority)
→ New technology acquisition, achievement building, market value improvement

Team level (feature development proposal):
"Which feature should we develop next?"
→ Propose with Pattern 3 (Customer Value Priority)
→ User complaint resolution, experience improvement

Management level (budget approval):
"Why should we invest in this feature?"
→ Explain with Pattern 2 (Business Value Priority)
→ Revenue contribution, competitive advantage, risk reduction
```

**Important insight:**

Even for the same feature development, the points you emphasize change depending on who you're explaining to. This isn't lying, it's simply **changing how you communicate to match the values the other party emphasizes**.

#### **Trigger 4: Resource Change**

```
Abundant resources → Pattern 5 (Balance) with multiple parallel initiatives
  ↓ Budget cuts
Insufficient resources → Narrow to Pattern 2 (Business Value) or Pattern 3 (Customer Value)
  ↓ Further cuts
Minimal resources → Pattern 1 (Urgency×Importance) narrow to minimum
```

**Signs:**
- Budget cut notification
- Personnel transfers
- Schedule compression requests

**Switching judgment criteria:**

"Are available resources sufficient?"
→ Sufficient  → Balance type (reconcile multiple objectives)
→ Insufficient  → Narrow down (business value or customer value)
→ Minimal  → Minimum (urgency×importance)

**ADAS development example:**

```
When resources are abundant:
- Regulatory compliance + new feature development + technology research in parallel
→ Pattern 5 (Balance)

After budget cuts:
- Narrow to regulatory compliance + major features
→ Pattern 2 (Business Value Priority)

Further cuts:
- Regulatory compliance only
→ Pattern 1 (Urgency×Importance)
```

---

### Five Questions for Pattern Selection

When actually choosing a pattern, you can select the appropriate pattern by answering the following five questions.

#### **Question 1: Who is this prioritization for?**

Prioritization always has beneficiaries. Clarifying who they are determines the pattern.

**Beneficiary examples:**
- **Customers**        → Pattern 3 (Customer Value Priority)
- **Company**        → Pattern 2 (Business Value Priority)
- **Self**        → Pattern 4 (Career Priority)
- **Team**      → Consider feasibility
- **Regulators**    → Compliance priority
- **Multiple beneficiaries** → Pattern 5 (Balance)

Even for the same project, beneficiaries change depending on the situation. In normal times, prioritize customers; in crisis times, prioritize the company (business continuity). Such switching is necessary.

#### **Question 2: What's the current situation?**

Situational awareness is key to pattern selection.

**Situation diagnosis:**

| Question | Answer | Recommended Pattern |
|------|------|------------|
| Is there a crisis? | Yes | Pattern 1 (Urgency×Importance) |
| Time horizon? | Short-term (this week/month) | Pattern 1 |
| | Medium-term (this quarter) | Pattern 2 or 3 |
| | Long-term (this year onward) | Pattern 5 |
| Who are you explaining to? | Self | Pattern 4 |
| | Team | Pattern 3 |
| | Management | Pattern 2 |
| Resources? | Abundant | Pattern 5 |
| | Insufficient | Pattern 2 or 3 |
| | Minimal | Pattern 1 |

**Example: ADAS feature development team**

```
Situation diagnosis:
- Crisis: None
- Time horizon: Medium-term (this quarter)
- Stakeholder: Team-level judgment
- Resources: Somewhat insufficient

→ Recommended pattern: Pattern 3 (Customer Value Priority)
  Reason: Not a crisis, team-level judgment,
        to achieve medium-term goals
```

#### **Question 3: What's the rationale for this pattern?**

Pattern selection needs rationale.

**Types of rationale:**
- **Data**: Market research, customer feedback, experimental results
- **Regulatory requirements**: Criteria defined by law, industry standards
- **Management policy**: Company strategy, annual goals
- **Resource constraints**: Budget, personnel, time constraints
- **Past experience**: Success/failure cases from similar projects

By making the rationale explicit, you can explain "why we chose this pattern." This is also important when reviewing later.

#### **Question 4: What are the trade-offs?**

We can't achieve everything simultaneously. Make explicit what gets sacrificed when you prioritize something.

**Trade-off examples:**

```
Choosing Pattern 3 (Customer Value Priority):
✓ User satisfaction improves
✓ Market evaluation increases
✗ Technical debt accumulates
✗ Regulatory compliance gets postponed

Choosing Pattern 2 (Business Value Priority):
✓ Easy to get executive support
✓ Easy to secure budget
✗ User experience may be sacrificed
✗ Risk of decreased engineer motivation
```

By visualizing trade-offs, you can recognize "what you're abandoning."

#### **Question 5: Can you change the pattern when the situation changes?**

This is the most important question.

Don't fixate on a pattern once decided; you need the flexibility to change patterns when the situation changes.

**Flexibility check:**

```
Q: If a crisis occurs, can you immediately change the pattern?
Q: When the quarter changes, is there a process to review priorities?
Q: When new information comes in, can you revise the judgment?
Q: Can the entire team share the reason for pattern switching?
```

To ensure flexibility, it's important to **define pattern switching triggers in advance**.

---

## Practical Examples

Let's look at these concepts through three specific scenarios.

### Scenario 1: Normal Product Development

**Situation:**
```
- Regulatory compliance completed
- No particular fires burning
- Considering how to prioritize next features
```

**Things to do (5 items):**
1. LKA adverse weather performance improvement
2. ACC traffic jam comfort improvement
3. AEB false positive reduction
4. Next-generation sensor technology research
5. Documentation maintenance

**Step 1: Situation Diagnosis**

```
Crisis occurrence: None
Time horizon: Medium-term (this quarter)
Stakeholder: Team-level judgment
Resources: Somewhat insufficient
```

**Step 2: Pattern Selection**

```
Recommended pattern: Pattern 3 (Customer Value Priority)

Reason:
- Not a crisis, so urgency priority unnecessary
- Normal operations, so should emphasize customer value
- However, strategic investment also needed, so complement with Pattern 5
```

**Step 3: Priority Determination**

```
1. LKA adverse weather performance improvement
   Customer value: High (many user complaints)
   Strategic importance: Medium (leads to differentiation)
   → Priority 1

2. AEB false positive reduction
   Customer value: High (damages experience)
   Strategic importance: Medium
   → Priority 1

3. ACC traffic jam comfort improvement
   Customer value: Medium (nice to have)
   Strategic importance: Low
   → Priority 2

4. Next-generation sensor technology research
   Customer value: Low (not yet manifested)
   Strategic importance: High (needed in 3 years)
   → Priority 2 (allocate some resources)

5. Documentation maintenance
   Customer value: None
   Strategic importance: Low
   → Priority 3 (if there's capacity)
```

**Step 4: Monitor Switching Triggers**

```
Trigger 1 (Crisis occurrence): None → Maintain status quo
Trigger 2 (Time horizon): Medium-term (this quarter) → Customer value priority
Trigger 3 (Stakeholder): Team level → Customer value priority
Trigger 4 (Resources): Somewhat insufficient → Need to narrow down

→ Conclusion: Based on Pattern 3 (Customer Value),
       complement with Pattern 5 (Balance)

First focus on 1, 2
When capacity allows, invest in 4
Postpone 3, 5
```

---

### Scenario 2: Regulatory Compliance Deadline Approaching

**Situation:**
```
- ISO 26262 certification in 6 months
- Delayed response means can't sell
- Other tasks also piling up
```

**Things to do (5 items):**
1. ISO 26262 compliance (ASIL decomposition review)
2. LKA adverse weather performance improvement
3. Cost reduction initiatives
4. Development process improvement
5. New employee training system establishment

**Step 1: Situation Diagnosis**

```
Crisis occurrence: Yes (regulatory violation risk)
Time horizon: Short-term (6 months)
Stakeholder: Regulators, executives
Resources: Limited
```

**Step 2: Pattern Selection**

```
Recommended pattern: Pattern 1 (Urgency×Importance)

Reason:
- Deadline approaching → Urgency is most important
- High risk → Directly linked to business continuity
- Others can be postponed
```

**Step 3: Priority Determination**

```
1. ISO 26262 compliance
   Urgency: High (6 months)
   Importance: High (can't sell)
   → Priority 1 (concentrate resources)

2. LKA adverse weather performance improvement
   Urgency: Low
   Importance: Medium
   → Priority 3 (start after ISO completion)

3. Cost reduction initiatives
   Urgency: Medium (management request)
   Importance: Medium
   → Priority 2 (minimal response)

4, 5. Others
   → Priority 4 (freeze)
```

**Step 4: Detect Switching Triggers**

```
Trigger 1 (Crisis occurrence): Regulatory violation risk → Crisis mode
Trigger 2 (Time horizon): Short-term (6 months) → Urgency priority
Trigger 3 (Stakeholder): Regulators → Compliance priority
Trigger 4 (Resources): Limited → Narrow down

→ Conclusion: Switch to Pattern 1 (Urgency×Importance)

Full effort on ISO 26262
Cost reduction at minimum
Others completely postponed

6 months later, regulatory compliance completed:
Trigger 1 (Crisis resolved) → Return to normal mode
→ Switch to Pattern 3 (Customer Value)
```

---

### Scenario 3: Career Turning Point

**Situation:**
```
- System engineer, 6th year
- Can choose from multiple projects
- Struggling with which work to take on
```

**Options (4 items):**
1. Legacy system maintenance (stable, but routine)
2. New architecture design (challenging, high risk)
3. Large project lead (management experience)
4. Collaboration project with overseas sites (global experience)

**Step 1: Situation Diagnosis**

```
Decision maker: Individual (your own career judgment)
Time horizon: Long-term (future career formation)
Resources: Time and energy are limited
```

**Step 2: Pattern Selection**

```
Recommended pattern: Pattern 4 (Career Priority)

Reason:
- Personal career judgment
- Not organizational requirement, but your own choice
- Considering future career formation
```

**Step 3: Priority Determination**

```
Your goals:
- Want to acquire more advanced technical expertise
- Also want to gain management experience
- Want to increase market value

1. Legacy system maintenance
   Skill acquisition: Low (already can do)
   Achievement building: Low (few growth opportunities)
   Market value: Low
   → Don't choose

2. New architecture design
   Skill acquisition: High (new technology)
   Achievement building: High (can demonstrate expertise)
   Market value: High (high market demand)
   → Top priority candidate

3. Large project lead
   Skill acquisition: Medium (management)
   Achievement building: Medium (leadership experience)
   Market value: Medium
   → Priority candidate

4. Overseas collaboration
   Skill acquisition: Medium (global experience)
   Achievement building: Low (limited technical depth)
   Market value: Medium
   → Hold
```

**Step 4: Decision**

```
Choice: 2 (New architecture design)

Reason:
- Strengthening technical expertise
- Market value improvement
- Greatest growth opportunity

3 (Project lead) is also attractive, but
prioritize establishing technical foundation first

However, if a crisis occurs (Trigger 1):
Prioritize team/company priorities over personal career
```

---
## Summary - The Essence of Adaptive Prioritization

The essence of prioritization isn't the patterns themselves, but **being able to switch judgment criteria according to the situation**.

**Three core principles:**

### 1. Clarify who the decision is for

Even for the same initiative, value changes depending on whose perspective you view it from.

- Value to customers
- Value to the company
- Value to your own career
- Team feasibility

By clarifying the beneficiary, the rationale for prioritization becomes clear.

### 2. Recognize the current situation

When the situation changes, the criteria you prioritize also change.

**Four switching triggers:**
1. Crisis occurrence (normal times → emergency response mode)
2. Time horizon change (short-term → medium-term → long-term)
3. Stakeholder change (team → management)
4. Resource change (abundant → insufficient → minimal)

Constantly monitor these, and when the situation changes, change the pattern too.

### 3. Visualize trade-offs

We can't achieve everything simultaneously.

What gets sacrificed when you prioritize something. By making this explicit, you can make realistic judgments. And when reviewing later, you understand "why we made this decision."

---

## Conclusion: Switching Judgment Criteria Is the Essence

There is no "single correct answer" for prioritization.

What's important is:
1. **Knowing multiple patterns** (5 basic + 3 supplementary)
2. **Clarifying who the decision is for**
3. **Recognizing the current situation**
4. **Being able to switch patterns according to the situation**
5. **Designing triggers for switching**

The 8 patterns introduced in this article each have appropriate use cases. And what's most important is **"switching patterns by considering who the decision is for and what the current situation is."**

Next time, I'd like to address "how to execute after deciding priorities" and "how to course-correct when things don't go according to plan."

---

## Related Articles

- [Drawing the Line: What Should System Architects Decide?](/posts/drawing-decision-boundaries/)
- [When to Switch Decision Criteria: Trigger Design for System Engineers](/posts/when-to-switch-decision-triggers/)
- [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/)

---

**[Disclaimer]**  
The content of this article represents the personal views of the author and does not represent the official views of any affiliated organization. The specific examples in the article are simplified models for explanation purposes and may differ from actual product implementations.