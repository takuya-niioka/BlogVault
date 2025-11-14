+++
created = "2025-11-14"
date = "2025-11-14T16:33:37+09:00"
title = "When to Switch Decision Criteria: Trigger Design for System Engineers"
author = "Takuya Niioka"
draft = false
portfolio = ["[[Portfolio_Blog]]"]
tags = ["System-Design", "Decision-Making", "ADAS", "Engineering"]
slug = "when-to-switch-decision-triggers"
categories = ["Engineering", "System Design"]
description = "Learn when systems should switch decision criteria in ADAS design, from driver monitoring warnings to safety interventions."
lang = "en"
publishDate = "2025-11-14T16:46:50+09:00"
+++

In system development, we need to design behaviors that can change decision criteria depending on the situation and achieve different objectives, even for the same function. However, "when" and "what should trigger" the switch in behavior and objectives is a challenge many designers face.

In Advanced Driver Assistance Systems (ADAS) development, we confront this question daily. For example, consider driver monitoring in systems with partial driving assistance capabilities.

The system simultaneously holds two objectives: "ensure the driver monitors driving" and "intervene when the driver cannot monitor." The system must switch decision criteria between these two objectives.

**Phase 1: Warning Mode** (Objective: Prompt return to driving)
- Detection: Gaze diverted from forward
- Behavior: Warning sound, display notification
- Decision criterion: "Driver can recover"

**Phase 2: Escalation Mode** (Objective: Forceful attention-getting)
- Detection: 10 seconds elapsed ignoring warning
- Behavior: Increased warning sound, steering wheel vibration
- Decision criterion: "Driver can recover but requires force"

**Phase 3: Emergency Intervention Mode** (Objective: Minimize secondary damage)
- Detection: No response for 30+ seconds + possible vital sign abnormality
- Behavior: Safe stop, hazard lights, emergency call
- Decision criterion: "Driver cannot recover, emergency response needed"

This raises an important question: **Why switch to Phase 2 at 10 seconds and Phase 3 at 30 seconds?** What philosophy lies behind these thresholds?

In system design, when incorporating multiple objectives into a single function, we frequently face the problem of blurred decision criteria. Trying to judge contradictory objectives like "prompt driving monitoring" and "intervene in emergencies" with a single threshold makes both half-hearted.

**This article proposes "explicitly switching decision criteria."** For functions with multiple objectives, we can prevent blurred judgment by preparing decision criteria for each objective and explicitly switching them according to the situation.

This article systematizes knowledge gained from ADAS development experience about designing "triggers" that switch decision criteria.

---

## Three Elements of Trigger Design

Triggers that switch decision criteria consist mainly of three elements.

### Element 1: Observable (Detectable State Changes)

**What should be detected to trigger a switch?**

For a system to change decision criteria, it must first be able to observe state changes. However, not all states can be measured by sensors.

ADAS development faces challenges such as:

- **Directly observable**: Gaze direction, steering operation, speed, lane position
- **Requires estimation**: Driver attention level, fatigue, intent
- **Difficult to observe**: Consciousness level, cognitive load, sudden health changes

For example, the state "driver has lost consciousness" cannot be directly measured. It must be estimated from multiple indirect evidence: eye movement, blink frequency, posture collapse, abnormal steering operation.

Therefore, trigger design requires careful consideration of "what is observable" and "is the risk of false detection acceptable?"

### Element 2: Threshold

**At what level should the switch occur?**

Once observable indicators are determined, we must decide "at what value to switch." This threshold setting always requires justification.

Threshold justifications include:

- **Ergonomic data**: Human cognitive and physical capability limits
- **Statistical analysis**: Data from experiments and field tests
- **Regulatory requirements**: Standards defined by law or industry
- **Risk analysis**: Worst-case scenarios from FMEA[^5] etc.
- **Medical knowledge**: Physiological and neurological research findings

For example, the threshold "how many seconds after gaze diversion to issue warning" can be determined based on ergonomic research data (visual attention duration averages 2-3 seconds).

However, not all thresholds have clear scientific basis. In many cases, engineers select "the most reasonable value" from limited data and experience, then adjust through validation testing.

### Element 3: Consequence (Purpose and Result of Switching)

**Why is the switch performed, and what changes?**

When decision criteria switch, system behavior changes. However, understanding only "what changes" is insufficient. **Documenting "why change" is key to designing appropriate triggers and behaviors.**

Points to clarify when designing switches:

- **Change in objective**: What decision criteria are we switching to prioritize?
  - Phase 1 (Warning Mode): Respect driver autonomy
  - Phase 2 (Forced Warning): Prioritize safety
  - Phase 3 (Emergency Intervention): Prioritize minimizing secondary damage

- **Reversibility**: Can we return to the previous state?
  - If reversible, early intervention is possible
  - If irreversible, more careful judgment is needed

- **Impact assessment**:
  - **User experience impact**: Will it cause discomfort or distrust?
  - **Safety impact**: Will secondary risks occur?
  - **Legal responsibility**: Is this switch legally acceptable?

For example, when ADAS switches from Phase 1 to Phase 2, the system's objective changes from "alert while respecting driver autonomy" to "intervene forcefully prioritizing safety." Clarifying this objective change also clarifies the threshold justification.

Furthermore, switching to Phase 3 changes the judgment to prioritize "minimizing harm to others" over "driver autonomy." This irreversible operation carries rear-end collision risk, requiring clear justification for "why switch objectives at this point."

---

## Three Approaches to Trigger Design

There are three main philosophical approaches to trigger design. Each has advantages and disadvantages, requiring selection based on system characteristics.

### Comparison of Three Approaches

| Approach | What to Observe (Observable) | How to Determine Threshold | When to Use |
|---|---|---|---|
| **Time-based** | Duration of specific state | Fixed value (e.g., 2 sec, 10 sec) | When universal physical/physiological limits exist |
| **State-based** | System or driver state | Change threshold according to state | When priority objectives change by situation |
| **Evidence accumulation-based** | Integrate multiple observations | Score and make comprehensive judgment | When false detection is high with single indicator |

### Approach 1: Time-based

**Philosophy: "Human cognitive and physical capabilities have physical limits"**

Time-based triggers are the simplest and easiest to implement. They set clear rules like "switch after a state continues for X seconds."

**ADAS example:**
- Gaze diverted for 2 seconds → Start warning
- No response for 10 seconds after warning → Forced warning
- No response for 30 seconds after forced warning → Safe stop

**Why these values?**

- **2 seconds**: NHTSA guidelines[^1] show that forward inattention exceeding 2 seconds significantly increases crash risk
- **3 seconds**: Euro NCAP[^2] defines gaze diversion over 3 seconds as "prolonged distraction"
- **10 seconds**: Line distinguishing intentional ignoring from temporary inattention (empirical threshold based on experimental data)
- **30 seconds**: Time when loss of consciousness is physiologically likely

**Advantages:**
- Clear and easy to implement
- High explainability (easy regulatory compliance)
- Easy debugging and testing

**Disadvantages:**
- Doesn't consider situation (same criteria for highway or traffic jam)
- Doesn't consider individual differences
- Prone to over-intervention or under-intervention

Time-based approaches are effective in domains with universal human capability limits. For example, in fatigue management functions like "prompt rest after 2 hours continuous driving," time is the most important indicator.

### Approach 2: State-based

**Philosophy: "System objectives change depending on context"**

State-based triggers **change what to observe (Observable) and post-switch objectives (Consequence) according to situation**. While time-based judges by "time as a single indicator," state-based observes "system or driver state" and switches the decision criteria themselves according to that state.

**Relationship with three elements:**
- **Observable**: System operational state, estimated driver state, sensor reliability
- **Threshold**: Dynamically adjust decision criteria according to state (not fixed values)
- **Consequence**: Priority objectives change according to situation

**ADAS example:**

| Situation | State to Observe | Priority Objective | Decision Criteria |
|---|---|---|---|
| **Normal driving** | System normal, driver alert | Respect driver autonomy | Longer to Phase 2 (15 sec from warning) |
| **System abnormality** | Sensor failure detected | Early safety assurance | Shorter to Phase 2 (5 sec from warning) |
| **Driver fatigue** | Fatigue signs present | Gradual arousal support | Repeat Phase 1 (delay Phase 2) |

**Essence of this approach:**

In time-based, it's a fixed rule "switch after 10 seconds," but in state-based, "if the system is operating normally and driver fatigue signs are detected, prioritize repeating warnings to promote arousal" - **switching the objective itself according to situation**.

**Why is it explainable:**

To the question "why 5 seconds in this situation?", we can explain "because the system is in abnormal state and driver state estimation reliability is low, we're making an early decision toward the safe side." This is simply changing the three elements (Observable, Threshold, Consequence) according to situation, which is logically explainable.

**Advantages:**
- Situation-specific optimization possible
- Can reduce unnecessary intervention (improved user acceptance)
- Can change objective priorities according to situation

**Disadvantages:**
- Implementation becomes complex
- State definition and detection required
- Test cases increase

State-based approaches are powerful in systems where environmental and system state changes are large and priority objectives change according to situation.

### Approach 3: Evidence Accumulation-based

**Philosophy: "Judge by integrating multiple evidence, not a single indicator"**

Evidence accumulation-based triggers **integrate multiple observations (Observable) into a score**, switching when that score exceeds a threshold. While state-based "changes decision criteria according to situation," evidence accumulation-based is an approach to "calculate confidence from multiple evidence."

**Relationship with three elements:**
- **Observable**: Collect multiple observations simultaneously (gaze, steering operation, speed variation, etc.)
- **Threshold**: Integrated score threshold (comprehensive judgment of multiple evidence, not single value)
- **Consequence**: Gradually switch objectives according to score

**ADAS example:**

```
Evidence Score =
  Gaze-off time × 0.4 +
  Abnormal blink frequency × 0.2 +
  Unnatural steering operation × 0.3 +
  Speed variation instability × 0.1

if Evidence Score > 0.3:
    Warning Mode
elif Evidence Score > 0.6:
    Forced Warning Mode
elif Evidence Score > 0.8:
    Emergency Intervention Mode
```

**Difference from state-based:**

| Approach | What to Judge | How to Determine Criteria | Example |
|---|---|---|---|
| **State-based** | Which state currently | Change threshold according to state | "System abnormal" → intervene early |
| **Evidence accumulation-based** | How confident | Integrate multiple evidence into score | Judge by total of gaze+operation+speed |

**Why this approach?**

Single indicators alone lead to many false detections. For example, "gaze diverted" alone cannot distinguish mirror checking from distraction. However, if gaze is diverted AND steering operation is unnatural AND speed is unstable, distraction probability is high.

**Advantages:**
- Can significantly reduce false detection
- Can handle gray zones (quantify "somewhat suspicious")
- Good compatibility with machine learning

**Disadvantages:**
- Difficult to explain weighting rationale
- Prone to black-boxing
- Complex parameter adjustment

Evidence accumulation-based approaches have high affinity with modern machine learning technology and are expected to become increasingly important. However, ensuring explainability remains a challenge.

---

## Trigger Design in Practice: Five Design Questions

When actually designing triggers, answering the following five questions can improve design quality.

### Question 1: Who is this decision criteria switch for?

Decision criteria switches always have beneficiaries. Clarifying who they are reveals priorities.

- **Driver protection**: Prioritize personal safety
- **Other vehicle protection**: Minimize harm to surroundings
- **Pedestrian protection**: Protect most vulnerable traffic participants
- **Manufacturer risk avoidance**: Manage legal liability and reputation risk

Even in the same system, beneficiaries change by situation. Normally prioritize driver convenience, in emergencies prioritize surrounding safety - such switches are necessary.

### Question 2: What are the timing tradeoffs for switching?

Decision criteria switches always have **timing tradeoffs**. Both too early and too late carry risks, and which to emphasize is the core of trigger design.

#### Risks of Switching Too Early

**Example: Safe stop initiated immediately when driver temporarily checks mirror**

| Risk Type | Specific Impact |
|---|---|
| **Secondary damage** | Rear-end collision risk from following vehicles |
| **User experience** | Driver confusion, system distrust |
| **Operational issues** | System turned OFF as result (counterproductive) |

Over-intervention from false detection significantly damages user acceptance. This results in a vicious cycle where the system isn't used when truly needed.

#### Risks of Switching Too Late

**Example: Emergency intervention mode entered only after 60 seconds when driver lost consciousness**

| Risk Type | Specific Impact |
|---|---|
| **Life danger** | Driver life danger, collision risk with other vehicles/pedestrians |
| **Serious accidents** | Accidents that should have been prevented occur |
| **Legal liability** | Regulatory violations, litigation risk |
| **Corporate credibility** | Media criticism, recalls, social credibility loss |

Switching too late negates the purpose of having triggers. In worst cases, serious accidents cannot be prevented, questioning the system's very existence.

#### Worst-Case Scenario of Not Switching

From a risk management perspective, we must also consider the option "not having switch triggers at all."

**Example: No trigger exists for switching to emergency intervention mode**
- System only continues issuing warnings forever
- Cannot respond even if driver loses consciousness
- Legal and social responsibility for "why intervention function wasn't implemented"

From this scenario, **the necessity of triggers themselves** is derived.

#### Judgment Guidelines for Tradeoffs

| Judgment Aspect | Choose Earlier Switch | Choose Later Switch |
|---|---|---|
| **Reversibility** | Operation is reversible (warnings etc.) | Operation is irreversible (safe stop etc.) |
| **Safety importance** | Safety is top priority (medical, transportation) | User experience also valued (general apps) |
| **False detection cost** | False detection cost is low | False detection cost is high |
| **Miss cost** | Miss cost is high | Miss cost is low |

**General judgment criteria:**

In most cases, we must weigh "too early risk" against "too late risk" and decide which to emphasize. Generally, in safety-related systems, "too late risk" is judged more serious, and somewhat earlier thresholds are adopted.

However, for irreversible operations (transition to Phase 3 etc.), caution is required. This judgment balance is the essential challenge of engineering.

### Question 3: What is the basis for this threshold?

When determining thresholds, the following justifications must be clarified:

- **Ergonomic data**: Citations from academic papers, ISO standards, etc.
- **Statistical analysis**: Analysis results from experimental data
- **Regulatory requirements**: Standards defined by law or guidelines
- **Competitive benchmarking**: Analysis of other companies' product behavior
- **Risk analysis**: Worst-case scenarios and acceptable risk settings

Thresholds with unclear justification become problematic later. Especially from regulatory compliance and litigation risk perspectives, documenting design decision rationale is important.

### Question 4: How much should individual and situational differences be considered?

Ideally, triggers optimized for all users and all situations are desirable. However, in reality, there are the following tradeoffs:

**Apply same threshold to everyone:**
- Advantages: Simple, easy to explain, fair
- Disadvantages: Ignores individual differences, not optimal

**Individual optimization:**
- Advantages: Optimal for each user
- Disadvantages: Learning period needed, privacy concerns, difficult to explain

For example, young and elderly drivers differ in reaction time. However, changing thresholds by age may invite criticism of "age discrimination."

Most systems take an approach of starting with fixed thresholds and gradually introducing individual optimization.

### Question 5: Can we return after switching?

Trigger reversibility is **the most important factor determining the tradeoff between early intervention and careful judgment**. Reversible operations have low false detection cost enabling early intervention, but irreversible operations require careful judgment as false detection is fatal.

| Reversibility | Threshold Setting | Evidence Requirement Level | Risk |
|---|---|---|---|
| **Reversible** | Early/loose | Single evidence acceptable | False detection → poor user experience |
| **Irreversible** | Late/strict | Multiple evidence required | Miss → serious accident |

**Examples of reversible triggers:**
- Issue warning sound, change screen display
- Phase 1 → Phase 2 (can return anytime)
- Strategy: Intervene early and observe user response

**Examples of irreversible triggers:**
- Safe stop, forced system shutdown
- Phase 2 → Phase 3 (cannot return)
- Strategy: Accumulate multiple evidence, execute after high confidence

**Hysteresis[^7] design:**

Irreversible triggers need mechanisms to prevent frequent switching:

```
Condition to enter Phase 3: Evidence Score > 0.8
Condition to exit Phase 3: Evidence Score < 0.4

→ Maintain state between 0.4-0.8 (prevent chattering)
```

By setting the "exit threshold" lower than the "entry threshold," once emergency mode is entered, it doesn't immediately return, allowing return to normal mode only after safety is confirmed.

---

## Case Study: Driver Monitoring System Design Process

Let's examine an actual driver monitoring system trigger design process integrating the concepts so far.

### Step 1: Hierarchize Objectives

First, hierarchize the multiple objectives the system has.

```
Level 1 objective: Have driver monitor driving
Level 2 objective: Intervene if monitoring impossible
Level 3 objective: Minimize harm to others
```

### Step 2: Priority for Each Level

Priorities change by situation.

- **Normal**: Level 1 > Level 2 > Level 3
- **Emergency**: Level 3 > Level 2 > Level 1

Normally, prioritize letting the driver continue driving. However, in emergencies (driver definitely cannot monitor), minimizing harm to surroundings becomes top priority.

### Step 3: Design Switch Triggers

#### Phase 1 → Phase 2 Trigger

- **Observable**: Forward gaze rate < 50% continues for 5 seconds
- **Threshold**: Why 5 seconds?
  - Human attention recovery averages 3 seconds (research data)
  - Add 2-second margin = 5 seconds
- **Consequence**: Warning sound/display → Small user experience impact

At this stage, we still judge the driver can recover. Warnings are reversible intervention, so can be executed relatively early.

#### Phase 2 → Phase 3 Trigger

- **Observable**: 
  - (Forward gaze rate < 30% continues for 20 seconds) AND
  - (No steering operation OR abnormal operation)
- **Threshold**: Why 20 seconds?
  - Line distinguishing intentional ignoring from loss of consciousness (based on experimental data and medical knowledge)
  - At 10 seconds, temporary intentional ignoring is likely
  - At 30 seconds, intervention may be too late
  - 20 seconds is the balance point
- **Consequence**: Safe stop → Irreversible, following vehicle risk exists

At this stage, we judge the driver cannot recover and enter emergency intervention mode. Since safe stop is irreversible with secondary risks, more stringent conditions are set.

### Step 4: Document Tradeoffs

Document design decision rationale.

```
Risks of too-early Phase 3 transition:
- Possibility of rear-end collision from false intervention
- User trust loss, resulting system OFF
- Excessive alert fatigue[^6]

Risks of too-late Phase 3 transition:
- Driver serious accident
- Regulatory violation (Ministry of Land guidelines)
- Recalls, litigation, corporate credibility loss
```

After comparing both, judged "too late risk" more serious, adopted somewhat earlier threshold (initially 30 sec → finally 20 sec)

By documenting such decision processes, when design changes are needed later, modifications can be made understanding the original intent.

---

## Meta-Framework: Design Patterns for Judgment Switching

Judgment switching patterns are common across various systems. Here we introduce three representative patterns.

### Pattern 1: Gradual Escalation

When state deteriorates continuously, gradually tighten decision criteria.

```
Level 1 (mild) → Level 2 (moderate) → Level 3 (severe)
```

**Examples:**
- **ADAS**: Warning → Forced warning → Safe stop
- **Hospital triage**: Observation → Priority treatment → Emergency treatment
- **Server monitoring**: Log recording → Alert → Auto-restart

**When to use:**
- When state deteriorates continuously
- When early intervention enables recovery
- When gradual response is effective

This pattern's advantage is giving users "advance notice." Rather than immediately taking final measures, gradually raising warning levels gives users opportunity to respond themselves.

### Pattern 2: Binary Switch

When intermediate states are meaningless, instantly switch decision criteria.

```
Mode A (normal) ⇔ Mode B (abnormal)
```

**Examples:**
- **ADAS**: Comfort Mode ⇔ Emergency Mode
- **Data center**: Normal operation ⇔ Failover
- **Security system**: Permit mode ⇔ Lockdown mode

**When to use:**
- When intermediate states are meaningless
- When instant switching is necessary
- When hesitation in gray zones is dangerous

For example, when a data center primary server goes down, an intermediate state of "half-switching to backup" is meaningless. Immediate failover to secondary server is necessary upon detection.

### Pattern 3: Conditional Branch Tree

When situations are complex and single indicators cannot judge, branch on multiple conditions. This pattern **dynamically changes thresholds themselves according to situation**.

#### Decision Structure by Decision Tree

This pattern can be expressed as nested if-else structure (decision tree):

```
                   [System Reliability]
                   /              \
              High /                \ Low
                 /                    \
    [Driver State Estimation Confidence]     [Multiple Sensor Abnormality?]
        /        \                 /         \
    High/          \Low        Yes/           \No
       /            \            /             \
  Standard(20s)  Long(40s)  Short(10s)    Careful(30s)
```

**Implementation example in code:**
```python
if System_Reliability == High:
    if Driver_State_Estimation_Confidence == High:
        Emergency_Intervention_Threshold = Standard (20 sec)
        # Reason: Both system and driver estimation reliable, standard judgment
    else:
        Emergency_Intervention_Threshold = Long (40 sec)
        # Reason: Driver state unclear, judge carefully
elif System_Reliability == Low:
    if Multiple_Sensor_Abnormality_Detected:
        Emergency_Intervention_Threshold = Short (10 sec)
        # Reason: System abnormal, estimation inaccurate, early safe-side decision
    else:
        Emergency_Intervention_Threshold = Careful (30 sec)
        # Reason: Single sensor abnormal, wait for additional confirmation from other sensors
```

#### Situations Where This Pattern is Effective

| Condition | Description |
|---|---|
| **Multiple observations affect** | Optimal threshold cannot be determined by single indicator alone |
| **High context dependency** | Road type, weather, traffic conditions affect judgment |
| **Priority objectives differ by situation** | Prioritize "early safety assurance" during system abnormality, "user experience" normally |

#### Difference from Approach 2 (State-based)

Pattern 3 can be considered an implementation pattern of Approach 2 (state-based), but handles more complex conditional branches:

| Feature | State-based (Simple) | Conditional Branch Tree (Complex) |
|---|---|---|
| **Number of states** | About 3-5 | Many from situation combinations |
| **Judgment complexity** | Determine state by single condition | Determine by multiple condition combinations |
| **Implementation method** | if-elif-else (flat) | Nested if statements (tree structure) |

#### Caution: Controlling Complexity

While this pattern is highly flexible, excessive complexity makes testing and maintenance difficult:

**Bad example (overly complex):**
```python
if (System_Reliability == High) and (Driver_State == Alert) and (Weather == Good) and (Road_Type == Highway) and (Speed > 80):
    Threshold = 15 sec
elif (System_Reliability == High) and (Driver_State == Alert) and (Weather == Good) and (Road_Type == Highway) and (Speed <= 80):
    Threshold = 20 sec
# ... dozens of conditional branches continue
```

**Good example (appropriate abstraction):**
```python
# First branch on main judgment axis
if System_Reliability == High:
    Base_Threshold = 20 sec
    # Fine-tune according to situation
    if Highway_Driving:
        Base_Threshold -= 5 sec  # Intervene earlier
else:
    Base_Threshold = 10 sec  # Err on safe side
```

**Design principles:**
- Maximum 3 judgment axis levels (more is incomprehensible)
- Branch in order of importance
- Document reason for each branch (comments mandatory)

---

## Conclusion: Trigger Design is Technology for Resolving Value Conflicts

The essence of system design is how to mediate contradictory objectives.

- Driver autonomy vs. safety
- Convenience vs. risk avoidance
- Early intervention vs. false intervention avoidance

Designing decision criteria switch triggers means **documenting "at what point, which value to prioritize."**

Just as flight attendants change behavior between normal and emergency situations, systems must also change decision criteria according to situation. Engineers are required to precisely design the timing and conditions of those switches through engineering.

Characteristics of excellent trigger design are these three points:

1. **Observability**: Switch conditions are clear and measurable
2. **Explainability**: Can explain why that threshold, with justification
3. **Adaptability**: Functions appropriately according to situation changes

Most importantly, having a framework where the entire team can share that trigger design philosophy.

Everyone being able to answer questions like "why this threshold?" and "why switch at this timing?" in the same language. That becomes the foundation for realizing sophisticated system design.

Decision criteria switching is not merely a technical implementation issue. It is a fundamental design philosophy issue of how to mediate contradictory values.

---

## Beyond System Design: Application to Organizational Strategy

The trigger design concepts introduced in this article are **a general framework applicable not only to system design but also to organizational and team strategy formulation**.

### Essence of "Mode Switching" in Organizations

The questions organizations face are "what mode are we in now?" and "what conditions should trigger switching to the next mode?"

Like system design, organizations have multiple objectives:

- **Startup growth strategy**: "Short-term revenue" vs. "Long-term market share"
- **Product development**: "Adding new features" vs. "Resolving technical debt"
- **HR strategy**: "Short-term results" vs. "Talent development"

However, trying to pursue these simultaneously blurs decision criteria. **What's important is explicitly declaring "what mode now" and making decisions with decision criteria appropriate to that mode.**

### Application Example to Organizational Strategy: Startup Phase Switching

| Mode | Priority Objective | Example Decision Criteria | Switch Trigger |
|---|---|---|---|
| **Phase 1: Market Validation Mode** | Prioritize hypothesis validation | Don't worry about Customer Acquisition Cost (CAC) | PMF[^8] achieved (retention rate > 40%) |
| **Phase 2: Growth Mode** | Prioritize scale | Growth rate > profitability | Monthly growth rate slows for 3 consecutive months |
| **Phase 3: Monetization Mode** | Prioritize profit | Profitability > growth rate | Market share saturates |

**Problems this framework solves:**

- "Why invest in growth even at a loss now?" → Because in growth mode
- "When should we pivot to monetization?" → When trigger conditions are met
- "Each member's decision criteria vary" → Everyone shares the same mode

### Applying Five Design Questions to Organizational Strategy

The five questions introduced in this article are also effective for organizational decision criteria design:

1. **Who is this switch for?** → Prioritize shareholders, customers, or employees?
2. **What are early/late risks?** → Monetization before PMF (too early) vs. missing growth opportunity (too late)
3. **What's the threshold basis?** → 40% retention rate is PMF indicator (industry data)
4. **Individual/situational differences?** → Different triggers needed for B2B vs B2C
5. **Can we return?** → Returning from monetization mode to growth mode is difficult

Specific application methods to organizational strategy will be detailed in future articles.

What's important is that **decision criteria switching is a universal technology needed in all decision-making situations**. By expanding thinking methods cultivated in system design to broader domains, more precise strategic design becomes possible.

**Related articles:**
- [Decision-Making Under Uncertainty: The 70% Rule](/posts/decision-making-under-uncertainty-70-percent-rule/)
- [Between Safety and Value: Defining 'Correctness' Through Nine Years of Journey](/posts/defining-correctness-nine-years-journey/)

---

**[Disclaimer]**  
The content of this article represents the author's personal views and does not represent the official views of any affiliated organization. Specific examples in the article are simplified models for explanation and may differ from actual product implementations.

[^1]: NHTSA (2013). "Visual-Manual NHTSA Driver Distraction Guidelines for In-Vehicle Electronic Devices"
[^2]: Euro NCAP (2024). "Driver Monitoring Systems Assessment Protocol"  
[^3]: ISO 26262: Road vehicles — Functional safety
[^4]: UN Regulation No. 157: Automated Lane Keeping Systems (ALKS)
[^5]: FMEA (Failure Mode and Effects Analysis) - Method for systematically analyzing potential failure modes and their effects in systems
[^6]: Alert Fatigue - Phenomenon where users begin ignoring alerts due to frequent warnings
[^7]: Hysteresis - Design technique that adds history effects to state change thresholds to prevent frequent switching
[^8]: PMF (Product Market Fit) - State where product fits market needs