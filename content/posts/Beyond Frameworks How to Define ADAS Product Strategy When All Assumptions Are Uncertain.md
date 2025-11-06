+++
title = "Beyond Frameworks: How to Define ADAS Product Strategy When All Assumptions Are Uncertain"
date = "2025-11-05T13:30:00+09:00"
draft = false
tags = ["ADAS", "Product-Strategy", "Decision-Making", "Frameworks", "Uncertainty", "Design-Thinking", "Autonomous-Driving"]
slug = "beyond-frameworks-adas-strategy-under-uncertainty"
description = "The limitations of frameworks in ADAS development and a practical approach to drawing strategy amid uncertainty. Introducing the 5-Layer Decision Framework derived from 9 years of practical experience."
+++

## The Framework Trap

I have been involved in ADAS feature development for nine years now. During this time, I have tried numerous frameworks that are said to "provide answers" when developing product strategies. Design Thinking, User Journey Mapping, Jobs-to-be-Done Theory, Lean Startup, and consulting-style Case Methods. I believe they are all theoretically excellent.

However, I must confess honestly: I have never once been able to confidently say "this is the optimal solution" using these frameworks.

Rather, even after faithfully following the frameworks to define personas, draw user journeys, identify issues, and derive solutions, questions keep arising when I try to explain them to others or actually present them. Eventually, I have experienced several cases where either we proceed with a launch despite lingering doubts due to time constraints, or the project fades away.

Why does this happen? Is it due to my lack of ability? Or is there some fundamental problem?

## Why Frameworks Fail in ADAS Development

Through trial and error, I believe there are three fundamental reasons why these frameworks fail to function.

### Problem 1: Uncertainty of Assumptions

For example, let's say we are considering developing a lane change assist feature. Following the Design Thinking process faithfully, we first conduct user interviews. When we talk to 20 drivers, many respond that they "feel anxious about lane changes" and "feel stressed on highways."

Based on this, we define personas: business professionals in their 30s-40s who use highways three times a week. Their pain points are clear, and the solution seems obvious. We should develop a feature that assists with highway lane changes. Following the framework, it appears we have drawn a perfect strategy.

However, questions then begin to arise.

Can we really claim representativeness with N=20 interviews? Will those who said "anxious" actually pay for this feature? Will they be satisfied with Level 2 implementation, where the driver ultimately holds responsibility?

Thinking further leads to more fundamental questions. Don't people who are already good at lane changes not need this feature? Conversely, aren't people who are truly anxious about lane changes avoiding not just highways but driving itself? In other words, does the target user segment we envision actually exist?

Thus, even neatly organized personas and user journeys, if built on uncertain assumptions, collapse entirely when those assumptions crumble.

### Problem 2: Complexity of Constraints

ADAS development involves countless intertwined constraints. Technical constraints include sensor detection limits and processing power ceilings. Regulatory constraints clearly define the driver's scope of responsibility in Level 2 systems, and particularly in the UN regulations, also define what the system must do. Cost constraints are always severe, requiring a balance between BOM costs and development costs.

Furthermore, there are time constraints from competitor timelines, organizational constraints from internal decision-making processes and the time they require. Above all, there is market constraint uncertainty: how much will users be willing to pay?

Frameworks can organize these constraints individually. However, finding the optimal balance point by integrating everything is not simple. This is because these constraints influence each other, and moving one causes others to change in tandem.

### Problem 3: Impossibility of Defining "Optimal Solution"

There is an even more fundamental problem. What does "optimal solution" even mean, and optimal for whom?

For engineers, the optimal solution is technical excellence. For marketing departments, what's important is ease of communication to customers. Management seeks high ROI, while users expect usability and convenience. Regulatory authorities demand high safety.

These criteria often conflict. A technically excellent solution might be too costly for adequate ROI. Features easy to communicate might be difficult to realize due to regulatory constraints, and prioritizing safety might sacrifice usability.

In other words, the "optimal solution" that frameworks presuppose simply doesn't exist.

## The Case Method's Illusion

While I find case methods used in consulting firm interviews effective for improving logical thinking and business skills, I feel the limitations of frameworks in ADAS development settings.

The typical flow of case methods involves quantitatively defining the problem, clearly identifying the target, specifying their pain points, drawing a strategy that addresses them, and concluding "this is the answer." The structured, point-driven, conclusion-first narrative style is very logical, clear, and persuasive. Above all, it's effective in early-stage discussions as a basis for debate.

However, when explaining the drawn strategy to others, various questions arise. "Why did you define the target segment that way? What about this age group?" "Your market environment assumptions are based on this, but isn't reality actually like that?" "What if competitors move like this?"

When assumptions are shaken this way, the strategy that seemed promising moments ago crumbles instantly. You must rebuild the strategy to match the new assumptions.

However, this point is also important: flexibility in "how to respond when assumptions change" is a very important stance in drawing strategy.

### The Uncomfortable Truth

Case method frameworks appear logical when assumptions are fixed. But when assumptions change, answers change too. And in real business environments, assumptions constantly change.

In other words, the conclusion "this is the optimal solution" derived using frameworks actually carries a major caveat: "as long as these assumptions hold true." However, in most cases, this caveat is not explicitly stated.

What does this mean? In environments with high uncertainty, isn't the stance itself of "there must be an optimal solution somewhere, so let's find it" fundamentally wrong?

## A Different Approach: Strategy Under Uncertainty

So what should we do? Should we completely abandon frameworks?

No, we shouldn't. Frameworks themselves are useful tools. The problem lies in "how we use" frameworks. We tend to try using frameworks as "magic wands that lead us to answers." However, frameworks should properly be used as "tools for systematically organizing thinking" and "frameworks for making uncertainty explicit."

What does this mean? From here, I'd like to introduce an approach I've gradually developed through practical experience. It's not about "finding the optimal solution," but rather "explicitly stating assumptions and adapting to change."

### Not Abandoning Frameworks, But Changing How We Use Them

#### Step 1: Explicitly State and Layer Assumptions

The first step is to explicitly state all assumptions and layer them.

I find it helpful to classify assumptions into three layers.

**Layer 1: Immovable Constraints (Hard Constraints)**  
These are assumptions that cannot be changed no matter how hard we try, such as laws of physics, regulatory requirements, and current technical limitations. For example, we cannot change the regulatory requirement that "drivers hold final responsibility at Level 2."

**Layer 2: Changeable Assumptions (Soft Assumptions)**  
These are assumptions that might change through validation, such as hypotheses about user needs, market size estimates, and competitive trend forecasts. Hypotheses like "business professionals aged 30-40 use highways three times a week" fall into this layer.

**Layer 3: Unknown Elements (Unknowns)**  
These are elements that cannot even be predicted at present, such as future regulatory changes, technological breakthroughs, and changes in social acceptance.

What's important is explicitly stating which layer each assumption belongs to. This reveals "which assumptions are prone to collapse and how that affects strategy."

#### Step 2: Create an Assumption Dependency Map

Next, we visualize which assumptions each strategic option depends on.

For example, let's consider the lane change assist feature example.

**Strategy A: Develop at Level 2**  
This strategy depends on assumptions that "users will accept somewhat imperfect implementation" (Soft), "there is value in first-mover advantage over competitors" (Soft), and "realizable within Level 2 regulatory scope" (Hard).

**Strategy B: Wait for Level 3**  
This strategy depends on assumptions that "Level 3 will be realized within 3 years" (Soft), "won't lose market share despite delay" (Soft), and "Level 3 responsibility scope will be clarified" (Unknown).

**Strategy C: Phased Feature Rollout**  
This strategy depends on assumptions that "there is value in traffic jam scenarios only" (Soft), "cost recovery possible with phased approach" (Soft), and "technically divisible" (Hard).

Creating this map visualizes "which strategy fails when which assumption collapses." For example, we can see that Strategy B is high-risk because it depends on two Soft Assumptions and an Unknown.

#### Step 3: Scenario Planning

Rather than pursuing a single "optimal solution," I consider it effective to envision multiple scenarios and corresponding strategies for each.

For example, let's create a matrix with two axes: "User Needs" and "Technology Maturity."

When user needs are high and technology is mature (S2), we develop at full force aiming for market leadership. When user needs are high but technology is still immature (S1), we start development early while investing in market education. When technology is mature but user needs are low (S4), we postpone development and focus on other features. When both are low (S3), we conduct minimal development and wait and see.

What's important is preparing conditional strategies in advance: "if S2 occurs, do this."

#### Step 4: Set Decision Points

We validate assumptions at set milestones while proceeding with development.

For example, we conduct a user survey at Month 3, continuing if 50% or more say "want it," reconsidering strategy if less than 50%. At Month 6, we conduct prototype testing, continuing if satisfaction is 80% or above, reducing scope if below 80%. At Month 12, we implement pilot sales, proceeding to mass production if purchase rate is 10% or above, canceling or pivoting if below 10%.

When assumptions collapse, honestly change the strategy. This is the essence of flexible decision-making.

#### Step 5: Speak of "Best Solutions" Not "Optimal Solutions"

Finally, the most important point: changing how we use language.

Instead of saying "this is the optimal strategy," say "given current assumptions, this is the best strategy." Instead of "users will definitely want this," say "as a hypothesis, this persona likely finds value." Instead of "will definitely succeed," say "if Assumption A is correct, success probability is high. If assumptions collapse, we'll shift to Strategy B."

Acknowledging uncertainty and speaking conditionally—this is not weakness but rather honesty, correctness, and an appropriate professional stance.

## What 9 Years in ADAS Taught Me

From here, let me share five lessons I've learned from practical experience.

### Lesson 1: Frameworks Are Tools, Not Answers

Design Thinking and Case Methods are themselves excellent tools for organizing thinking. However, they don't provide answers. This is because answers aren't found but created, and told as stories. Tools only demonstrate value when combined with the user's judgment and communication skills. Rather than seeking answers from frameworks, we should use frameworks to organize our thinking, gather decision-making materials, and effectively communicate them.

### Lesson 2: Keep Questioning Assumptions

"Does this persona actually exist?" "Is this market size estimate correct?" "Will this technology really be realized?" Constantly questioning assumptions is important.

This is not pessimism. Rather, it's the essence of risk management. By questioning assumptions, we can evaluate the impact when those assumptions collapse in advance and prepare alternatives. Questioning is preparing.

### Lesson 3: The Courage to Say "I Don't Know"

Engineers tend to avoid saying "I don't know." However, what we don't know, we don't know. Rather than forcing answers and building strategy on uncertain assumptions, honestly acknowledging "I don't know" is far more professional. (Related post: [Decision-Making Under Uncertainty: The 70% Rule](/posts/decision-making-under-uncertainty-70-percent-rule/))

What's important is explicitly stating what we know, what we don't know, and how to validate what we don't know. Acknowledging uncertainty while showing how to address it—that is true professionalism, in my view.

### Lesson 4: Strategy Evolves

Perfect strategies don't exist. When assumptions change, strategies change too. That's okay.

What's important is thinking ahead about which assumptions collapsing would require which strategy changes. Not fixing strategy, but preparing to adapt to change—that is a truly "strategic" stance.

### Lesson 5: Prepare Multiple Answers

The approach of "this is the only answer" is dangerous. In environments with high uncertainty, we need to prepare conditional answers: "if Assumption A, then Strategy A; if Assumption B, then Strategy B."

Flexibility is the essence of strategy. Rather than clinging to one answer, preparing to choose the best option according to circumstances—that is the best way to face uncertainty.

## A Practical Framework for Strategy Under Uncertainty

Summarizing this discussion as a practical framework yields a decision-making structure composed of five layers. I've named this the "5-Layer Decision Framework."

### The 5-Layer Decision Framework

**Layer 1: Constraints**  
First, list all immovable assumptions. Laws of physics, regulations, current technical limitations—constraints that cannot be changed no matter what. These are the foundation of strategy, and all decisions are made within these constraints.

**Layer 2: Assumptions**  
Next, explicitly state changeable assumptions. Hypotheses about user needs, market size, competitive trends. Clearly note that these are verifiable and might change through validation.

**Layer 3: Scenarios**  
Prepare strategic options for when assumptions change. Envision three scenarios—Best Case, Base Case, Worst Case—and prepare corresponding strategies for each.

**Layer 4: Validation Gates**  
Set milestones for validating assumptions. Clarify when, what, and how to validate. This enables periodic checking of assumption validity.

**Layer 5: Pivot Triggers**  
Decide in advance how to change strategy when which assumptions collapse. For example, set specific criteria like "reduce scope if user satisfaction falls below 50%" or "cancel development if purchase rate falls below 5%."

### Example: Lane Change Assist Decision

Let's apply this 5-Layer Framework to the lane change assist feature decision as an example.

**Layer 1: Constraints**  
Explicitly state immovable constraints: drivers hold final responsibility in Level 2 systems, sensor detection range is about 100m, development period is 2 years.

**Layer 2: Assumptions**  
List hypotheses requiring validation: target is business professionals aged 30-40, annual market size estimated at 5 million units, competitor plans release in 1 year.

**Layer 3: Scenarios**  
Best Case assumes user satisfaction 80%, purchase rate 15%. Base Case assumes satisfaction 60%, purchase rate 8%. Worst Case assumes satisfaction 40%, purchase rate 3%. Prepare strategies corresponding to each.

**Layer 4: Validation**  
Decide to conduct user survey (N=100) at Month 3, prototype testing at Month 6, pilot sales at Month 12.

**Layer 5: Pivot Triggers**  
Set specific pivot criteria: reduce scope if satisfaction falls below 50%, cancel development if purchase rate falls below 5%, shift to differentiation strategy if competitor leads.

Through this five-layer structure, "which assumptions we depend on" and "what to do if assumptions collapse" becomes clear, enabling decision-making even amid uncertainty.

## Conclusion: Embracing Uncertainty

### The Hard Truth

Once more, the uncomfortable truth:

There is no "perfect answer" in product strategy. Frameworks are not omnipotent. Assumptions constantly change.

Yet we must make decisions. Should we proceed with development or postpone? Should we invest in this feature or prioritize another? We must make decisions amid uncertainty.

### What We Can Do

So what can we do amid uncertainty?

**Explicitly State Assumptions**  
Clarify what assumptions we're making and which assumptions are important. Visualizing implicit assumptions and sharing them with all stakeholders is the starting point for everything.

**Validate Assumptions**  
When and how will we validate assumptions? What will we do if they collapse? It's important to design validation and response processes in advance.

**Adapt Flexibly**  
Accept that strategy evolves. Pivoting is not failure. The ability to adapt to change is our greatest weapon amid uncertainty.

**Speak Honestly**  
Have the courage to say "I don't know." Acknowledge uncertainty. This is not weakness but rather honesty and professional responsibility.

### A Call to Fellow Engineers

We engineers pursue "solving problems technically"—that is our job. However, product strategy doesn't work well when technology-driven alone.

Market needs, user psychology, competitive moves, regulatory changes, organizational constraints—amid all these intertwined complexities, we must find the "best."

Not seeking perfect answers, but accepting uncertainty, explicitly stating assumptions, and adapting flexibly—isn't such a stance the skill required of engineers in the coming era?

Drawing strategy and doing our best amid uncertainty—that is the work truly required of us engineers.