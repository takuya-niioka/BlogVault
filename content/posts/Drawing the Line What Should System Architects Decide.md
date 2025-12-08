+++
created = "2025-11-22"
date = "2025-11-22T23:19:02+09:00"
title = "Drawing the Line: What Should System Architects Decide?"
author = "Takuya Niioka"
draft = false
portfolio = ["[[Portfolio_Blog]]"]
tags = ["systems-architecture", "decision-making", "delegation", "leadership", "decision-record", "RASIC"]
slug = "drawing-decision-boundaries"
categories = ["Systems Architecture", "Decision Making"]
description = "Learn how to navigate ambiguous decision boundaries as a tech lead or systems architect and stop second-guessing every choice you make."
lang = "en"
publishDate = "2025-11-22T23:23:27+09:00"
+++

## The Endless Dilemma: "What Should I Actually Decide?"

"Can I decide on the specification change for the next-generation control function myself? Or should I consult my manager?"

When you consult your manager, they say "think for yourself." When you decide independently and report, they say "I wish you had consulted me first."

"Can I delegate this decision to my junior colleague?"

When you delegate, the direction goes wrong. When you give detailed instructions, you're accused of "micromanagement." Your junior becomes passive, waiting for instructions, and your workload never decreases.

**You're damned either way.**

This is the pain of ambiguous decision boundaries. If you're a systems architect or tech lead, you've probably experienced this at least once.

### Why Decision Boundaries Become Ambiguous

There are four reasons why decision boundaries become ambiguous: **Not explicitly defined** (relying on implicit knowledge of "reading the air"), **case-by-case decisions** (no consistent criteria), **unclear role definition** (you have a title but expectations are vague), and **the reality of resource constraints** (it's physically impossible to make every decision yourself).

### What Happens When Decision Boundaries Are Ambiguous

When you continue working with ambiguous decision boundaries, a vicious cycle begins.

**You yourself** spend cognitive resources on trivial decisions and become exhausted, unable to spend time on strategic decisions you should be making. Your manager evaluates you as "lacking initiative," and your career stagnates. **Your juniors** don't know what's expected of them, become passive, and lose opportunities for growth. **Your manager** thinks "I want them to think for themselves" but can't communicate what they want reported, and the team's overall performance doesn't improve.

To break this vicious cycle, you need to **clarify decision boundaries**.

## Understanding the Hierarchical Structure of Decisions

The first step in clarifying decision boundaries is understanding that decisions have hierarchies.

### Five Decision Layers

Decision-making in organizations can be broadly divided into five layers. Why five? Because decisions can be clearly separated along three dimensions: **time horizon, uncertainty, and scope of impact**. Too many layers create complexity; too few make the granularity too coarse. Five layers is the most functional division in practice.

| Layer | Role | Decision Content | Time Horizon | Uncertainty | Scope of Impact | V-Model Position | Decision Examples |
|-------|------|------------------|--------------|-------------|-----------------|------------------|-------------------|
| **Layer 5** | Executive Management | Business policy, budget allocation, organizational structure | Years | ★★★★★<br>Very High | Entire company | Business strategy | Invest 10 billion yen over 5 years in Level 3 autonomous driving |
| **Layer 4** | Department Head<br>Chief Engineer | Overall system direction, architecture decisions | Months to 1 year | ★★★★☆<br>High | Entire department<br>Cross-functional | **Top of left side**<br>(Requirements analysis, system requirements) | Camera-centric vs LiDAR-centric architecture<br>System requirements specification |
| **Layer 3** | Systems Architect<br>Systems Engineer | Functional requirements, performance targets, technology selection, validation planning | Weeks to months | ★★★☆☆<br>Medium | Functional team<br>Assigned system | **Left side** (Requirements definition)<br>**Right side** (Validation) | [Requirements] Functional requirements definition, performance target setting<br>[Strategy] Adopt radar to improve AEB nighttime performance from 70% to 82%<br>[Validation] Verification method definition, planning |
| **Layer 2** | Senior Engineer | Detailed design, implementation architecture, verification strategy | Days to weeks | ★★☆☆☆<br>Low to Medium | Module<br>Component | **Left side** (Detailed design)<br>**Right side** (Verification, integration testing) | Sensor fusion algorithm design<br>Integration test strategy, coverage target setting |
| **Layer 1** | Engineer | Coding, unit testing, bug fix decisions | Hours to days | ★☆☆☆☆<br>Low | File<br>Function level | **Bottom layer**<br>(Implementation and testing) | Function implementation methods, data structure selection<br>Unit test case design, debugging techniques |

**Two perspectives at Layer 3**[The Essence of System Architecture: Building the Right Thing](/posts/what-systems-architects-actually-do/):
- **Systems Engineer perspective**: "Does this system function correctly?" (Requirements definition, validation)
- **System Architect perspective**: "Is this the right system?" (Strategy, value definition)

**When your junior is at Layer 3**: Delegate part of the functional requirements to your junior and check the direction at the 50% point.

#### Another Axis: Role Division with Project Management (PL/PM)

Layers 1-5 above represent the **technical decision hierarchy**. Separately, there exists a **project management axis**. Particularly in vehicle platform teams, Project Leaders (PL) or Project Managers (PM) exist and play different roles from systems architects.

**Important premise: Systems architects do NOT do PM work**

Systems architects (Layer 3) and PL/PM are involved in the same decision items from different perspectives, but their ultimate areas of responsibility are clearly distinct.

**Systems Architect vs PL/PM Role Division:**

| Decision Item | Systems Architect (Technical Axis) | PL/PM (Project Management Axis) |
|---------------|-----------------------------------|--------------------------------|
| **What (What to build)** | **Propose** technical specifications and performance targets | **Decide** scope and priorities |
| **How (How to build)** | **Decide** technology selection and architecture | **Decide** resource allocation and task breakdown |
| **When (By when)** | **Evaluate** technical feasibility | **Set** schedule and milestones |
| **Who (Who does it)** | **Define** technical skill requirements | **Decide** personnel assignment and team formation |
| **Risk** | **Evaluate and propose countermeasures** for technical risks | **Manage** overall project risks |
| **Ultimate Responsibility** | **Technical feasibility** | **Project success (QCD)** |

**Decision flow (example: 4D radar adoption):**

1. **Systems architect** conducts technical review and judges "can meet performance requirements"
2. **PL/PM** evaluates schedule, budget, and impact on other functions
3. Only when both agree is "adoption" decided
4. After adoption, **systems architect** ensures technical realization, **PL/PM** drives overall project

**Problems that arise when boundaries are ambiguous:**
- Systems architect buried in PM work → Can't spend time on Layer 3 strategic decisions
- Technical and schedule responsibilities mixed → "Technically excellent but can't meet deadline"
- Decision delays → Unclear who makes final decisions

**The systems architect's role is to focus on technical decisions and provide technical input to PL/PM**. Leave project management to PL/PM.

### Identifying Your Layer

What do you gain by identifying which layer you should primarily make decisions at?

#### Three Benefits of Clarifying Your Layer

| Benefit | When Layer is Ambiguous | When Layer is Clear |
|---------|------------------------|---------------------|
| **① Cognitive Load** | ✗ Full effort on all decisions<br>✗ Brain exhaustion<br>✗ Constant hesitation | ✓ Delegate Layer 1-2 to juniors<br>✓ Focus cognitive resources on Layer 3<br>✓ Hesitation disappears |
| **② Manager Evaluation** | ✗ Spend time on Layer 1-2<br>✗ Evaluated as "lacking initiative"<br>✗ Career stagnation | ✓ Make proactive decisions at Layer 3<br>✓ Propose to Layer 4 (manager)<br>✓ Evaluated as "proactive" |
| **③ Junior Development** | ✗ Unclear what to delegate<br>✗ Passive state<br>✗ No growth | ✓ Delegate Layer 1-2 decisions<br>✓ Accumulate success experiences<br>✓ Your burden also lightens |

#### Four Criteria for Identifying Your Layer

So, which layer should you primarily make decisions at? Here are the criteria in table form:

| Criteria | Layer 5<br>(Executive) | Layer 4<br>(Department Head) | Layer 3<br>(Systems Architect) | Layer 2<br>(Senior Eng.) | Layer 1<br>(Engineer) |
|----------|----------------------|------------------------------|-------------------------------|------------------------|---------------------|
| **Position/Experience** | Executive<br>Board member | Department head<br>Chief engineer | 5-10 years experience<br>Systems architect | 3-7 years experience<br>Senior engineer | 1-3 years experience<br>Junior engineer |
| **Organizational Title** | CEO, CTO | General Manager, GL | "Systems Architect"<br>"Lead" | "Tech Lead"<br>"Member" | "Member"<br>"Staff" |
| **Decision Time Horizon** | Years | Months to 1 year | Weeks to months | Days to weeks | Hours to days |
| **Scope of Impact** | Entire company | Department, multiple functions | Functional team, assigned system | Module, component | File, function |
| **V-Model Process** | Business strategy | Requirements analysis | Requirements definition<br>Validation | Detailed design<br>Verification | Implementation<br>Unit testing |
| **Decision Examples** | Business investment decisions | System requirements specification | Functional requirements<br>Validation plan<br>Technology selection | Detailed design<br>Integration test strategy | Implementation methods<br>Unit testing |

#### What Happens If You Don't Identify Your Layer?

Conversely, if you don't identify your layer:
- Time consumed by Layer 1-2 trivial decisions (over 50%)
- Time available for Layer 3 strategic decisions decreases (under 30%)
- Manager evaluates you as "lacking initiative"
- Juniors are confused about "what they can decide"
- Result: Neither you nor your juniors grow

**Identifying which layer should be your main battleground is the first step in clarifying decision boundaries.**

## Strategically Designing Decision Boundaries

Once you know your layer, next design specific decision boundaries. You need to draw three boundary lines: with your manager, your own scope, and with your juniors.

### Boundary Line with Upper Layer (Manager)

First, clarify the boundary with your manager. What should your manager decide, and what should you decide yourself?

#### Four Signals to Escalate to Your Manager

If even one of the following signals applies, it's your manager's decision domain:

| Signal | Criteria | Concrete Example |
|--------|----------|------------------|
| **Budget Impact** | Investment over 1 million yen<br>(varies by company) | 30 million yen for new sensor introduction<br>→ Budget authority lies with manager |
| **Cross-Department Coordination** | Negotiation/consultation with other departments needed | Negotiation with procurement department<br>ISO 26262 consultation with quality department |
| **Company Policy Alignment** | Business strategy level decision | Investment decision for Level 3 autonomous driving<br>Differentiation strategy vs competitors |
| **High Risk** | Major problem if it fails<br>Heavy accountability | Fundamental design change affecting safety<br>Risk of regulatory non-compliance |

**Decision flow:**

```
Decision item arises
   ↓
[Check 4 signals]
   ↓
YES (any applicable) → Escalate to manager
   ↓
NO (none applicable) → Decide yourself (with advance notice)
```

#### How to Escalate to Manager: Propose in Decision-Ready Form

When escalating to your manager, "What should we do?" is just dumping the problem. Organize technical options, clearly state your recommendation, and explain reasons and trade-offs. This helps your manager decide.

"Regarding next-generation sensors, there are three options. I recommend Option B (add 4D radar, 30 million yen). The reason is it meets regulatory requirements (nighttime detection rate 80%) with 82% achievement expected, within budget (under 35 million yen), and achievable in 18 months. Option A is low cost but has regulatory non-compliance risk, Option C is high performance but exceeds budget. Please make the final decision."

This way, by providing the five elements of **options, recommendation, reasons, trade-offs, and risks**, your manager can decide easily.

#### How to Communicate When You Decide: Show Autonomy with Advance Notice

On the other hand, for decisions within your scope, take the form of "advance notice."

"Regarding algorithm selection for next-generation sensors, I will proceed with Option B (improved Kalman Filter). The reason is it meets performance requirements with low implementation risk, development cost of 2 million yen within my discretionary range. If there are issues, please indicate by [date]."

Advance notice (avoid surprises), clear reasoning, and setting a period for objections. This shows autonomy while avoiding risk, and you're evaluated by your manager as "having initiative."

### Boundary Line with Lower Layer (Juniors)

Next, clarify the boundary with juniors. What to delegate to juniors, and what to do yourself.

#### Four Signals to Delegate to Juniors

If all of the following signals apply, you should delegate to juniors:

| Signal | Criteria | Concrete Example | Purpose |
|--------|----------|------------------|---------|
| **Implementation Level** | Layer 1-2 decisions | Algorithm detailed implementation<br>Test code design | Appropriate layer separation |
| **Recoverable** | Not a major problem if it fails | Prototype trial<br>Internal module refactoring | Provide learning opportunities |
| **Within Skills** | Within junior's understanding<br>Similar past experience | Technologies they've used<br>Similar problem experience | Build success experiences |
| **Time Buffer** | Can secure time for trial and error | Non-urgent improvement tasks<br>Refactoring | Environment for thorough learning |

**Delegation decision flow:**

```
Decision item (Layer 1-2 level) arises
   ↓
[Check 4 signals]
   ↓
All YES → Delegate to junior (clarify Why, constraints, criteria)
   ↓
Any NO → Decide yourself or decide together
```

#### How to Delegate to Juniors: Clarify Boundaries

When delegating work to juniors, "Please handle this module" is just dumping. Juniors don't know what to do or how far.

"Please implement the sensor fusion module. The purpose is to integrate camera and radar data to improve object detection accuracy. Constraints are processing time within 50ms, memory within 100MB, no additional parts. Criteria are detection accuracy over 90%, false detection rate under 1%. I leave the method to you. Please bring a design proposal by [date]. I'll check progress at the 50% point."

Communicate **Why (purpose), constraints, and criteria**, leave **How (method)** to them, and set timing for interim reports. This makes clear to juniors "the scope they can decide" and "constraints to observe."

#### Follow-up After Delegation: Check Only Direction

At interim reports (50% point), check only direction. Ask "Which approach did you choose? Why did you choose it?" Don't give detailed implementation instructions. Detailed instructions rob juniors of learning opportunities. If the direction is correct, leave How to them.

At final reports, ask "Please explain why you made this decision." Juniors get training in verbalizing their decisions, and if recorded as a Decision Record, it becomes organizational learning assets.

### If You're a Systems Architect: Focus on Your Layer (Layer 3)

Once you've clarified boundaries with your manager and juniors, focus on Layer 3 (functional strategy).

**What to decide at Layer 3 (systems perspective):**
- Define functional requirements and prioritize
- Develop validation plans (how to verify)
- Trade-offs between performance and cost
- Technology selection (sensors, algorithms)
- Set risk and quality targets

**When your junior is at Layer 3:**
- Delegate part of functional requirements to junior (clarify Why, constraints, criteria)
- Check direction at 50% point (don't give detailed instructions)
- Discuss validation plans together and develop junior's judgment

**Ideal time allocation:**
- Involvement in Layer 4: 20% (proposals to manager, input on system requirements)
- **Layer 3 (yourself): 60% (functional requirements, validation plans, technical decisions)** ← Focus here
- Support for Layer 2: 15% (direction confirmation for detailed design)
- Support for Layer 1: 5% (emergencies only)

## Tools for Clarifying Decision Boundaries

Here are two practical tools for clarifying decision boundaries.

### Decision Rights Matrix

The Decision Rights Matrix[^6] is a tool to clarify "who does what." It uses the RASIC model[^5] framework.

**RASIC Model:**
- **R = Responsible**: Person who actually performs the work
- **A = Accountable**: Person who makes final decision/approval (**only one person per item**)
- **S = Supportive**: Person who supports the work
- **C = Consulted**: Person whose opinion is sought
- **I = Informed**: Person who is informed of results

#### Example: RASIC Matrix for Next-Generation Sensor Selection

| Item | Manager<br>(Department Head) | Self<br>(Architect) | Junior<br>(Engineer) | Quality Dept | Procurement | PL/PM |
|------|---------|---------|---------|----------|----------|-------|
| **Technical Research** | I | **R/A** | S | - | - | I |
| **Option Organization** | C | **R/A** | S | - | - | C |
| **Cost Estimation** | C | **R** | S | - | C | **A** |
| **Final Decision** | **A** | **R** | I | C | I | C |
| **Detailed Design** | I | C | **R/A** | S | - | I |
| **Implementation** | I | C | **R/A** | - | - | I |

**Key points of this matrix:**

✓ Who does what is clear at a glance
✓ No more confusion about "whose decision is this?"
✓ All stakeholders can understand
✓ **Accountable (A) is only one person per item** ← Most important principle

When multiple people are A, confusion arises: "Who actually decides?" Always limit A to one person.

### Decision Record

Record important decisions. Record the following as a Decision Record:

**Content to record:**
- Decision item (what was decided)
- Decision layer (Layer 3, etc.)
- Reasons and trade-offs
- Preconditions
- Who was reported to, who was delegated to

Decision Records are useful for later review and decision revision when preconditions change[^1]. They don't need to be perfect. Start with a simple format and improve it with your team.

## Clarifying Decision Boundaries is the First Job for Mid-Level Engineers

Clarifying decision boundaries is a prerequisite for prioritization and value definition[^2].

Why? Because **when decision boundaries are ambiguous, you don't even know what to prioritize**.

### Designing Decision Boundaries is a Strategic Act

Designing decision boundaries is not just task division. This is a strategic act.

**Boundary with upper layer (manager):**
✓ What to escalate, what to decide yourself
✓ Judge by 4 signals (budget, cross-department coordination, company policy, risk)
✓ Show autonomy with advance notice
→ Evaluated as "having initiative"

**Your layer (Layer 3):**
✓ Focus on functional strategy
✓ Spend time on high-quality decisions
✓ Hone strategic thinking[^3]

**Boundary with lower layer (juniors):**
✓ What to delegate
✓ Judge by 4 signals (implementation level, recoverable, within skills, time buffer)
✓ Clarify Why, constraints, criteria; leave How to them
→ Juniors grow

### Usable Tools

**Decision Rights Matrix (RASIC):**
Clarify who does what. Only one Accountable person.

**Decision Record:**
Record decisions and review them. Juniors can learn. You can explain to your manager.

### Boundaries Are Not Fixed

Decision boundaries are not set once and done. They need periodic review.

**Review timing:**
✓ When juniors grow, expand delegation scope
✓ When environment changes, boundaries change
✓ Review every 3 months

**Adjust flexibly:**
✓ Perfect boundaries don't exist
✓ Optimize through trial and error[^4]
✓ Proceed with team consensus

### Final Message

When decision boundaries are clear:
✓ You can focus on your real work
✓ Juniors grow
✓ Manager evaluates you positively
✓ Team's overall performance improves

And the next question arises:

**"So, within my decision scope (Layer 3), when there are 10 things to do, what should I prioritize?"**

This will be explained in detail in the next article, "Techniques for Strategic Prioritization."

---

**Drawing decision boundaries is the first job of a systems architect.**

Start by identifying your layer. Then create a Decision Rights Matrix and share it with your manager and juniors. It doesn't need to be perfect. Taking the first step is what matters.

And record your decisions. Decision Records organize your thinking and become team learning assets.

---

## References

[^1]: [When to Switch Decision Criteria: Trigger Design for System Engineers](/posts/when-to-switch-decision-triggers/): Details timing for decision review when preconditions collapse.
[^2]: [Value-Oriented Engineering: The Power to Define What We Consider Good](/posts/value-oriented-engineering/): Explains prioritization techniques after decision boundaries are clarified.
[^3]: [The Essence of System Architecture: Building the Right Thing](/posts/what-systems-architects-actually-do/): Introduces specific practices of strategic thinking at Layer 3.
[^4]: [Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain](/posts/beyond-frameworks-adas-strategy-under-uncertainty/): Explains flexible decision adjustment in uncertain situations with examples.
[^5]: RASIC Matrix: "RASIC: A Model for Organization and Workflow Management" - Framework for clarifying role division in organizations.
[^6]: Gary L. Neilson, et al., "Who Has the D? How Clear Decision Roles Enhance Organizational Performance", *Harvard Business Review*, January 2006 - Analyzes impact of clarifying decision authority on organizational performance.