+++
title = "Decision-Making Under Uncertainty: The 70% Rule"
date = "2025-11-07T12:40:49+09:00"
draft = false
tags = ["decision-making", "leadership", "engineering-management", "risk-management", "product-development"]
slug = "decision-making-under-uncertainty-70-percent-rule"
description = "A practical framework for making better decisions in uncertain environments. Learn Amazon's 70% rule, One-Way vs Two-Way Door thinking, Pre-mortem Analysis, and other techniques to improve judgment in advanced technology development"
publishDate = "2025-11-07T12:40:49+09:00"
lastmod = "2025-12-13T13:49:47+09:00"
+++

**[Disclaimer]**  
The content of this article represents the author's personal views and does not reflect the official position of any organization. For decisions involving safety, it is essential to always comply with appropriate standards and regulations.

---

**[Important Prerequisites]**  
The "decide at 70%" principle discussed in this article applies only under the following conditions:

1. **Safety-critical decisions are excluded**: For functions involving human life, 100% verification and validation are mandatory
2. **Appropriate risk assessment is assumed**: Decisions within development processes compliant with functional safety standards such as ISO 26262
3. **Within organizational governance**: Decision-making under appropriate approval processes and oversight

This article discusses decision-making in **non-safety domains** such as product planning, strategic planning, and organizational management.

---

## Don't Wait for Perfect Information

When trying to improve the accuracy of our decisions, we often think, "Let me gather a bit more information." However, in reality, complete information is rarely available.

Amazon founder Jeff Bezos stated in his 2016 letter to shareholders[^1]:

> "Most decisions should probably be made with somewhere around 70% of the information you wish you had. If you wait for 90%, in most cases, you're probably being slow."

This statement symbolizes the trade-off between speed and accuracy. Why 70%? Because while waiting for 90% or 100% of the information, markets change and opportunities are lost.

In fact, Amazon appears to have made numerous swift decisions based on this principle. The launch of AWS (Amazon Web Services), introduction of Prime membership, and development of Kindle devices—all seem to be decisions made with 70% confidence without waiting for complete market research.

Waiting for 100% of information is synonymous with postponing decisions indefinitely. **Decide with 70% confidence and fill the remaining 30% through action**. This mindset forms the foundation of thinking in an era of uncertainty.

---

## The Reality of Development in Uncertain Environments

Particularly in cutting-edge technology fields, development itself is a continuous series of unknowns. Hardware and software are intricately intertwined, stakeholders are diverse, and legal and market trends are fluid. In such environments, "actionable decisions" are more important than "correct answers."

In advanced technology development, we routinely face the following uncertainties:

* **Technical Constraints**: Even if theoretically possible, physical and technical limitations exist in reality
* **Regulatory Uncertainty**: Legal frameworks for new technologies are still evolving worldwide, requiring decisions in domains without clear standards
* **Collaboration Complexity**: Consensus-building with diverse stakeholders takes time
* **Market Volatility**: Consumer acceptance and social receptivity constantly change

Under these conditions, "deciding after obtaining 100% certainty" is impossible. Rather, **the ability to formulate quality hypotheses with limited information** becomes crucial.

In development settings, postponing decisions due to "insufficient data" is essentially equivalent to making a decision to "do nothing." Instead of fearing uncertainty, we need a decision-making framework that assumes it.

However, to reiterate, this applies to **strategic decisions in non-safety domains**. For safety-related decisions, adherence to appropriate standards and verification processes is an absolute requirement.

---

## Framework 1: One-Way Door vs. Two-Way Door Thinking

In the same 2016 letter to shareholders, Jeff Bezos presented another important concept[^1]: the distinction between "One-Way Doors (irreversible decisions)" and "Two-Way Doors (reversible decisions)."

| Type | Definition | Decision-Making Approach | Examples |
|------|------------|-------------------------|----------|
| **Type 1: One-Way Door** | Critical decisions that cannot be undone once made | Careful, thorough verification | Factory construction, M&A, fundamental architecture selection |
| **Type 2: Two-Way Door** | Decisions that can be changed or withdrawn | Try quickly, modify quickly | Feature additions, UI changes, marketing initiatives |

The essence of this thinking is **not treating all decisions with the same weight**.

According to Bezos, the mistake many organizations make is applying One-Way Door processes to Two-Way Door decisions. As a result, even small, reversible decisions require excessive meetings and approval flows, slowing down organizational decision-making speed.

In product development:
- **One-Way Door**: Core system architecture, programming language selection, quality policy formulation
- **Two-Way Door**: UI design improvements, test scenario prioritization, development tool selection

For Two-Way Door decisions, trying quickly and learning quickly is effective. Rather than aiming for perfection, verifying through small-scale experiments and modifying decisions based on feedback ultimately produces better results.

**Decision Type Classification:**

| Type | Definition | Characteristics | Examples |
|------|------------|-----------------|----------|
| **Type 1 (One-Way Door)** | Critical decisions that cannot be undone | Careful, thorough verification | Factory construction, M&A, fundamental architecture selection |
| **Type 2 (Two-Way Door)** | Decisions that can be changed or withdrawn | Try quickly, modify quickly | Feature additions, UI changes, development tool selection |

However, this is limited to **reversible domains**. Decisions that cannot be reversed, such as safety functions or core technology selection, still require a cautious approach.

---

## Framework 2: Risk-Weighted Thinking

In uncertain situations, it's important to estimate "how much error is acceptable." A useful approach here is **considering the product of impact and probability**[^2].

> Expected Impact = Probability × Severity

This thinking applies expected value calculations used in statistics and financial engineering to decision-making.

For example, let's compare two risks in product development:

**Risk A**: Introducing a new algorithm
- Failure probability: 30%
- Impact if failed: 2-week development schedule delay
- Risk weight: 0.3 × 2 weeks = 0.6 weeks equivalent

**Risk B**: Fundamental change in development approach
- Failure probability: 10%
- Impact if failed: Entire project delayed by 6 months
- Risk weight: 0.1 × 6 months = 0.6 months equivalent (approximately 2.4 weeks)

While Risk B has a lower probability of occurrence, it has a much larger impact when viewed through risk weighting.

Using this framework clarifies decision-making priorities:
- When risks are large and irreversible: Gather more information and proceed carefully
- When risks are small and correctable: Decide quickly and move forward

---

## Practical Wisdom: Mental Models Supporting Judgment

Several thinking methods have been proposed to improve decision-making quality. Here we introduce four approaches that can be expected to be useful in practice.

### Pre-mortem Analysis: "If We Failed, Why?"

Pre-mortem is a technique proposed by psychologist Gary Klein[^3]. Unlike the usual post-mortem (retrospective), it assumes a "failed future" before decision-making and identifies the causes.

**Method**:
1. Assume the project has completely failed
2. Have all team members write down "why it failed"
3. Classify the failure causes that emerge and consider countermeasures

The advantage of this technique is that more specific and vivid failure scenarios emerge than in typical "risk analysis." By asserting "it failed," psychological defenses are lowered and genuine concerns surface.

### Decision Tree: Visualizing Options

Rather than worrying in your head, organizing thoughts by visualizing options and outcomes is effective.

A Decision Tree is a technique for expressing possible outcomes of each option in a tree diagram. It's particularly effective when multiple decisions are chained together.

**Application examples**:
- Technology selection choices (in-house development vs. utilizing existing libraries)
- Development strategy choices (parallel development vs. phased development)
- Market launch timing (early release vs. after feature completion)

Visualization transforms vague feelings of "somehow anxious" into concrete problems like "there's this risk at this branch point."

### Bayesian Thinking: The Courage to Modify Decisions

This applies Bayesian statistical thinking to decision-making[^4]. Each time new information (evidence) comes in, update the prior probability and calculate the posterior probability.

In the context of decision-making, it means the flexibility to "modify past decisions when new information comes in."

In many organizations, changing a decision once made tends to be criticized as "inconsistent." However, it's far more irrational to ignore new evidence and stick to old decisions.

**What's important**:
- Clearly explain why the decision was changed
- Show what the new information (evidence) was
- Position it as a learning and growth process

Don't fear being seen as "inconsistent"; take pride in being flexible.

### Kill Criteria: Deciding Withdrawal Conditions in Advance

This is a technique of clearly defining "at what point to stop" before starting a project or initiative.

**Examples**:
- "Discontinue if no results after 3 months"
- "Withdraw if costs exceed 150% of budget"
- "Reconsider if technical feasibility is determined to be below 50%"

The advantage of Kill Criteria is eliminating emotional attachment. People tend to fall into the "sunk cost fallacy" for projects they've invested in, unable to withdraw even when clearly failing.

By deciding withdrawal conditions in advance, you can stop coldly without missing the timing of judgment.

---

## Overcoming the Perfectionism Trap

In fields where quality and reliability are emphasized, "being cautious" is considered a virtue. However, when caution becomes excessive, all decisions are eventually treated as One-Way Doors (irreversible decisions), ultimately leading to paralysis.

This can be called the "perfectionism trap."

**Mechanism of falling into the perfectionism trap**:
1. Thoroughly analyze past failures and pile up preventive measures
2. Decision criteria gradually become stricter, approval processes more complex
3. Fear of failure leads to avoiding new challenges
4. Decision-making speed decreases, missing innovation opportunities
5. The entire organization becomes conservative, growth stagnates

Particularly in organizations with long histories or companies that have maintained high quality standards, this tendency strengthens.

What's important is **clearly distinguishing between safety-related parts (One-Way Door) and improvable parts (Two-Way Door)**. Rather than treating everything as One-Way, we need to identify domains that truly require caution.

For example:
- **Domains requiring caution**: Safety functions, compliance, quality assurance processes
- **Domains where quick trials are possible**: Development tools, project management methods, communication approaches

By making this distinction clear, we can maintain necessary caution while also maintaining the speed of innovation.

---

## The Wisdom of Setting Time Limits

The simplest way to escape the perfectionism trap is **deciding with a deadline**.

By setting constraints like "decide by this deadline" or "act when these conditions are met," the decision type naturally switches to Type 2 (Two-Way).

According to Parkinson's Law, "work expands to fill the time available for its completion"[^5]. In other words, without setting a deadline, information gathering and analysis for decision-making continue indefinitely.

**Effects of time limits**:
- Motivation to gather only truly important information
- Reduced psychological pressure to seek perfection
- Faster learning cycles through action

In fact, Amazon has a "Six-Page Memo" culture where materials for important decisions must be summarized within six pages[^6]. This is a mechanism that forces a balance between information accuracy and brevity.

Deadlines are not enemies of thinking but allies. By setting time boundaries, decisions turn into actions, and actions generate learning. This is the true meaning of "deciding at 70%."

---

## Conclusion: Don't Fear Uncertainty, Learn Through Action

In uncertain environments, the more we seek "complete correct answers," the more we become unable to move. Decision-making is not about certainty but about presenting hypotheses and having the courage to take the first step to verify them.

Behind Jeff Bezos's advocacy of the 70% rule appears to be Amazon's commitment to maintaining the "Day 1 (first day of founding) spirit"[^1]. Even as they became a large corporation, they constantly maintained awareness of the balance between decision-making quality and speed to avoid losing the sense of speed characteristic of startups—such corporate culture seems to have created this principle.

In fields with high complexity and uncertainty, such as advanced technology development, this way of thinking is particularly important.

However, to emphasize again, **this is limited to strategic decisions in non-safety domains**. For decisions involving safety, compliance-related judgments, and quality assurance processes, appropriate standards and verification are essential.

With that premise, rather than aiming for perfection, **choose the best with limited information and modify while learning**. This accumulation cultivates the intelligence called judgment.

Moving quickly in uncertainty. That's not recklessness but **intelligent speed**.

---



## Related Articles

- [When to Switch Decision Criteria: Trigger Design for System Engineers](/posts/when-to-switch-decision-triggers/)
- [Why the Semiconductor Giant Fell: Intel's Lesson on Inaction](/posts/stagnation-is-the-worst-decision/)
- [Defining Vision: Strategic Choice from Past Success & Failure](/posts/how-to-define-vision-strategic-choice/)
- [The Art of Implementing Vision: Bridging Definition to Execution](/posts/vision-implementation-bridging-definition-to-execution/)

## References

[^1]: Bezos, J. (2016). "2016 Letter to Shareholders." Amazon.com, Inc. https://www.aboutamazon.com/news/company-news/2016-letter-to-shareholders

[^2]: Kahneman, D., & Tversky, A. (1979). "Prospect Theory: An Analysis of Decision under Risk." *Econometrica*, 47(2), 263-291.

[^3]: Klein, G. (2007). "Performing a Project Premortem." *Harvard Business Review*, 85(9), 18-19.

[^4]: Pearl, J., & Mackenzie, D. (2018). *The Book of Why: The New Science of Cause and Effect*. Basic Books.

[^5]: Parkinson, C. N. (1955). "Parkinson's Law." *The Economist*.

[^6]: Bryar, C., & Carr, B. (2021). *Working Backwards: Insights, Stories, and Secrets from Inside Amazon*. St. Martin's Press.