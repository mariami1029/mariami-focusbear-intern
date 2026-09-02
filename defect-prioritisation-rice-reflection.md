# Defect Tracking & Prioritisation — RICE Reflection

## 1. What Is Defect Prioritisation?

Defect prioritisation is the process of deciding which bugs should be addressed first.

Not every defect has the same impact. A critical login failure may prevent many users from accessing the application, while a small visual alignment issue may only slightly affect the user experience.

QA should provide clear evidence about the defect and its impact, while the wider team can use this information to decide what should be worked on first.

At Focus Bear, the RICE framework is used to help prioritise work.

---

## 2. What Is RICE?

RICE is a prioritisation framework based on four factors:

* **R — Reach**
* **I — Impact**
* **C — Confidence**
* **E — Effort**

The formula is:

```text
RICE = (Reach × Impact × Confidence) / Effort
```

A higher RICE score generally indicates that the item has greater expected value relative to the effort required.

---

## 3. Reach

**Reach** estimates how many users are affected during a specific period.

For a defect, QA can consider:

* How many users experience the problem?
* Does it affect all users or only a subset?
* Does it affect a critical user journey?
* How frequently does the problem occur?

For example:

> A login bug affecting 500 users per week has a greater Reach than a cosmetic issue affecting 20 users per week.

Reach should be based on available evidence whenever possible rather than simply guessing.

---

## 4. Impact

**Impact** describes how significantly the defect affects an affected user.

A high-impact defect might:

* Prevent users from logging in
* Cause data loss
* Prevent an important workflow
* Cause an application crash
* Block a critical feature

A lower-impact defect might:

* Slightly reduce usability
* Cause a small visual inconsistency
* Require an extra click
* Affect a non-critical part of the interface

Impact should describe the effect on users, not simply how technically difficult the bug is.

---

## 5. Confidence

**Confidence** represents how certain we are about the Reach and Impact estimates.

For example:

* **100% confidence:** supported by strong data or reliable evidence
* **80% confidence:** good evidence, but some uncertainty remains
* **50% confidence:** limited evidence and significant uncertainty

A high-confidence estimate is more reliable than an estimate based mostly on assumptions.

Confidence can be improved by collecting:

* User reports
* Analytics
* Reproduction data
* Error logs
* Crash reports
* Usage statistics
* Support tickets
* Production monitoring data

---

## 6. Effort

**Effort** estimates how much work is required to resolve the defect.

This can include:

* Developer implementation time
* Code changes
* Testing effort
* Regression testing
* Deployment complexity
* Coordination with other teams
* Database or infrastructure changes

A small defect that can be fixed quickly may receive a higher RICE score than a severe defect requiring a large amount of work.

---

## 7. Example RICE Calculation

For example, suppose a bug has:

* Reach = 500 users
* Impact = 2
* Confidence = 80% = 0.8
* Effort = 4

The calculation is:

```text
RICE = (500 × 2 × 0.8) / 4
     = 200
```

Therefore, the estimated RICE score is **200**.

---

# 8. Severity vs. Priority vs. RICE

Severity and priority are useful concepts, but they are not the same as RICE.

### Severity

Severity describes **how serious the effect of the defect is**.

Examples:

* Critical
* High
* Medium
* Low

### Priority

Priority describes **how urgently the team should address the defect**.

Examples:

* P0 / Critical
* P1 / High
* P2 / Medium
* P3 / Low

### RICE

RICE provides a more quantitative way to compare work by considering:

* Number of affected users
* User impact
* Confidence in the estimates
* Effort required

A defect can therefore have high severity but still have a lower RICE score if it affects very few users or requires a very large amount of effort.

Conversely, a moderate-severity defect can have a high RICE score if it affects many users and is relatively inexpensive to fix.

RICE does not replace judgment. It provides a structured way to support prioritisation decisions.

---

# 9. Hypothetical Focus Bear Bug #1 — Cosmetic UI Issue

### Bug

The **Save** button on a settings page is slightly misaligned on certain screen sizes.

### User Impact

The feature still works correctly, but the interface looks less polished.

### RICE Estimates

* **Reach:** 100 users/week
* **Impact:** 0.5
* **Confidence:** 90% = 0.9
* **Effort:** 1

### Calculation

```text
RICE = (100 × 0.5 × 0.9) / 1
     = 45
```

### RICE Score

**45**

This issue has relatively low impact and does not prevent users from completing the workflow.

---

# 10. Hypothetical Focus Bear Bug #2 — Login Failure

### Bug

Some users cannot log in because the login request occasionally fails with a server error.

### User Impact

Affected users cannot access their accounts or use the application.

### RICE Estimates

* **Reach:** 500 users/week
* **Impact:** 3
* **Confidence:** 80% = 0.8
* **Effort:** 2

### Calculation

```text
RICE = (500 × 3 × 0.8) / 2
     = 600
```

### RICE Score

**600**

This is significantly higher than the cosmetic UI issue.

---

# 11. Comparing the Two Bugs

| Bug               | Reach | Impact | Confidence | Effort | RICE |
| ----------------- | ----: | -----: | ---------: | -----: | ---: |
| Cosmetic UI issue |   100 |    0.5 |        90% |      1 |   45 |
| Login failure     |   500 |      3 |        80% |      2 |  600 |

The login failure has the higher RICE score.

This matches my initial expectation because preventing users from logging in has a much greater effect on their ability to use the product.

The calculation also provides a clearer explanation for why the login issue should generally be prioritised.

---

# 12. Why a High-Severity Bug Can Still Have a Lower RICE Score

A high-severity defect does not automatically have the highest RICE score.

For example, imagine a critical bug that:

* Affects only 5 users
* Has very high impact
* Requires a large amount of engineering effort
* Has uncertain reach

Its RICE score could be lower than a moderate defect affecting thousands of users that requires very little effort to fix.

This does not mean the critical bug should automatically be ignored.

Security, data loss, legal, safety, or severe business risks may require immediate attention regardless of a calculated RICE score.

RICE should therefore be used as a decision-support framework rather than as the only factor in every situation.

---

# 13. Tools for Tracking Defects

QA teams can use several tools to track defects in an Agile workflow.

### GitHub Issues

GitHub Issues can be used to:

* Report bugs
* Assign issues
* Add labels
* Track status
* Discuss findings
* Link bugs to pull requests
* Track progress

### GitHub Projects

GitHub Projects can provide a visual workflow for issues.

For example:

```text
Backlog
   ↓
To Do
   ↓
In Progress
   ↓
Ready for Review
   ↓
Done
```

This makes the status of defects easier to understand.

### Jira

Jira is commonly used for Agile project and defect tracking.

It can support:

* Bug reports
* Priorities
* Labels
* Sprint planning
* Workflows
* Assignees
* Reports
* Dashboards

### Other Tools

Teams may also use tools such as:

* Linear
* Azure DevOps
* Trello
* YouTrack

The exact tool is less important than maintaining clear and accurate defect information.

---

# 14. What If QA, Developers, and Product Disagree?

Different team members may have different opinions about defect priority.

For example:

* QA may focus on user impact and risk.
* Developers may focus on technical complexity.
* Product may focus on business value and customer impact.

If there is disagreement, I would avoid making the discussion personal.

Instead, I would bring evidence to the discussion.

I would explain:

1. What the defect does.
2. How often it occurs.
3. How many users may be affected.
4. How serious the user impact is.
5. How confident we are in the estimates.
6. How much effort may be required.
7. Whether there are security, data, or business risks.

The RICE score can provide a common framework for discussing these factors.

The final decision should be made collaboratively by the appropriate product and engineering stakeholders.

---

# 15. If a Developer Says a Bug Is Too Minor

If a developer says that a bug is too minor to fix, I would first understand their reasoning.

I would then use evidence and RICE to evaluate the issue.

For example:

```text
Reach: 1,500 users/week
Impact: 1
Confidence: 90%
Effort: 1

RICE = (1,500 × 1 × 0.9) / 1
     = 1,350
```

Although the defect may appear minor from an individual user's perspective, its large Reach and low Effort could make it worth fixing.

On the other hand, if the RICE score is low, I would be open to deprioritising the issue.

The goal is not for QA to "win" the argument. The goal is to make the prioritisation decision using evidence.

---

# 16. Preventing Low-RICE Bugs From Being Forgotten

A low RICE score does not necessarily mean that a defect should disappear.

To prevent low-priority bugs from being forgotten, QA can:

* Keep them as tracked issues.
* Add appropriate labels.
* Record their RICE score or prioritisation reasoning.
* Keep reproduction steps and evidence.
* Review them during backlog refinement.
* Recalculate the score when circumstances change.
* Link related issues if they are part of a larger problem.
* Close them only when the team explicitly decides they are no longer relevant.

A bug that affects very few users today could become more important after a product change or increase in usage.

Therefore, prioritisation should be revisited when new information becomes available.

---

# 17. My QA Approach to Defect Prioritisation

When I discover a defect, I would first make sure that the issue is clearly documented and reproducible.

Then I would consider:

* User impact
* Number of affected users
* Frequency
* Business impact
* Technical risk
* Confidence in the available information
* Estimated effort
* Security or data risks
* Whether a critical workflow is blocked

For Focus Bear, I would use RICE as a structured way to support the prioritisation discussion.

I would not assume that a bug with a high severity automatically deserves the highest priority. Instead, I would look at the broader impact and effort involved.

If the available information is uncertain, I would collect more evidence before making strong claims about Reach or Impact.

---

# 18. Personal Reflection

Before learning about RICE, I would naturally be more likely to prioritise a bug based mainly on how severe it appears.

RICE adds another perspective because it considers not only the seriousness of the issue but also how many users are affected, how confident we are in the estimates, and how much effort is required.

The comparison between the cosmetic UI issue and login failure matched my intuition: the login failure received a much higher score because it affects more users, has greater impact, and requires relatively little effort compared with its potential value.

However, I also learned that a numerical score should not replace professional judgment. Critical security, data integrity, or other exceptional risks may require immediate action even when their RICE score is not the highest.

My goal as a QA tester is to provide reliable evidence so the team can make informed prioritisation decisions.

---

# 19. Personal QA Principle

> **Prioritise with evidence, consider user impact, and keep every defect visible until the team makes a clear decision.**
