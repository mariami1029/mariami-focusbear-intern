# Using Heuristics to Guide Testing — QA Reflection

## 1. What Are Heuristics in Software Testing?

A heuristic is a practical rule of thumb that helps a tester make decisions when there is incomplete information, limited time, or no exact procedure to follow.

In software testing, heuristics can help testers decide:

* What to test first
* Where defects are more likely to exist
* Which areas deserve deeper exploration
* Which risks should receive more attention
* What additional scenarios should be investigated

A heuristic is not a guaranteed rule. It is a useful strategy for guiding investigation.

Experienced testers often use their previous experience, knowledge of common failure patterns, product understanding, and observations to decide where to investigate next.

---

## 2. Why Are Testing Heuristics Useful?

Requirements and test cases cannot describe every possible user behavior or system condition.

A tester may encounter situations such as:

* Incomplete requirements
* Limited testing time
* Unexpected user behavior
* New functionality without previous test coverage
* Complex integrations
* Unusual input
* Unclear expected behavior

Heuristics provide a way to make reasonable testing decisions in these situations.

For example, if a new feature accepts user input, I would naturally investigate:

* Empty input
* Very long input
* Special characters
* Invalid values
* Boundary values
* Repeated submissions
* Unexpected navigation

These are not necessarily explicitly written in every requirement, but they are common areas where defects can occur.

---

## 3. Common Testing Heuristics

There are many heuristics that testers can use. They should be treated as guides rather than strict rules.

### The Rule of Three

When investigating a problem, three examples or observations can sometimes reveal a pattern.

For example, if the same type of error appears in three different workflows, I would investigate whether they share a common component or underlying cause.

The important idea is to look for patterns rather than treating every observation as completely isolated.

### Consistency Heuristic

Users expect similar things to behave in similar ways.

I would compare:

* Similar buttons
* Similar forms
* Similar messages
* Navigation patterns
* Terminology
* Status labels
* Error handling

For example, if one screen calls a status "Completed" while another calls the same state "Done," I would investigate whether the inconsistency could confuse users or indicate different underlying behavior.

### Follow the Data

Data moving through the system can reveal defects.

I would consider:

```text
User Input
   ↓
UI
   ↓
API
   ↓
Backend
   ↓
Database
   ↓
UI Response
```

I would check whether the data remains correct throughout this process.

### Change It

Changing conditions can reveal hidden defects.

For example:

* Change the input
* Change the device
* Change the browser
* Change the network
* Change the order of actions
* Change the user's state

### Check the Boundaries

Defects often occur around limits.

For example, if a field accepts 1–100 characters, I would test:

* 0
* 1
* 2
* 99
* 100
* 101

This connects heuristic exploration with Boundary Value Analysis.

### Start Where the Risk Is Highest

Testing should not necessarily begin with the easiest feature.

I would consider:

* Critical user journeys
* Recent changes
* High-value functionality
* Areas with a history of defects
* Complex integrations
* Security-sensitive functionality
* Features with many dependencies

---

## 4. Heuristics and Exploratory Testing

Heuristics are particularly useful during exploratory testing.

In exploratory testing, learning, test design, and execution happen together.

Instead of following only predefined test cases, the tester observes the application and decides what to investigate next.

For example:

```text
Test
 ↓
Observe
 ↓
Learn
 ↓
Form a hypothesis
 ↓
Change the test
 ↓
Observe again
```

This approach can help uncover unexpected behavior that predefined test cases may not cover.

---

## 5. How Experienced Testers Prioritize What to Test

When experienced testers have limited time, they usually do not test everything equally.

They consider risk and available information.

I would prioritize areas based on:

### Business Impact

What happens if this feature fails?

A login system or task-management workflow may deserve more attention than a minor visual detail.

### User Impact

How many users could be affected?

### Complexity

Complex functionality often has more possible failure paths.

### Recent Changes

Newly modified code may deserve additional attention.

### Historical Defects

If an area has previously contained many bugs, I would consider testing it more deeply.

### Dependencies

Features that depend on APIs, databases, authentication, or external services may require additional testing.

### Uncertainty

If requirements or implementation details are unclear, exploratory testing can help identify unexpected behavior.

---

# 6. 15-Minute Testing Scenario — Focus Bear

If I had only 15 minutes to test a new Focus Bear feature, I would not attempt to execute every possible test case.

I would use heuristics to maximize the information I can gain from the limited time.

### First 2 Minutes — Understand the Feature

I would quickly identify:

* What the feature is supposed to do
* Who uses it
* What the main workflow is
* What changed
* What could go wrong

### Next 5 Minutes — Test the Critical Path

I would test the most important happy path first.

For example:

```text
Open feature
   ↓
Perform main action
   ↓
Save/submit
   ↓
Verify result
```

I would confirm that the basic functionality works.

### Next 5 Minutes — Explore Risky Areas

I would quickly test:

* Empty input
* Invalid input
* Boundary values
* Repeated clicks
* Refresh/restart
* Back navigation
* Network interruption
* Unexpected user actions

I would also check whether the feature behaves consistently with similar parts of the application.

### Final 3 Minutes — Verify and Document

I would:

* Recheck anything suspicious
* Capture evidence
* Record unexpected behavior
* Note what I did not have time to test
* Report important findings

My goal would be to maximize **useful information**, rather than simply maximize the number of test cases executed.

---

# 7. Using Heuristics to Find Edge Cases

Heuristics encourage testers to ask questions beyond the happy path.

For example, instead of asking only:

> "Does the feature work?"

I would ask:

* What if the user does this twice?
* What if the input is empty?
* What if the input is extremely large?
* What if the user goes back?
* What if the network disappears?
* What if the application is restarted?
* What if the same data already exists?
* What if two actions happen quickly?
* What if the user has unusual data?
* What if the user uses a different device?

These questions can reveal edge cases that are not explicitly documented.

---

# 8. Gut Instinct vs. Structured Test Cases

Heuristics and intuition can be powerful, but relying only on gut instinct has risks.

### Advantages of Heuristics

They can help testers:

* Work effectively with limited time
* Explore unknown areas
* Discover unexpected defects
* Adapt to new information
* Test beyond predefined scenarios
* Identify areas of high risk

### Risks of Relying Only on Intuition

A tester may:

* Miss important requirements
* Focus too much on areas they personally expect to fail
* Repeat familiar tests
* Overlook less obvious scenarios
* Make assumptions about expected behavior
* Produce inconsistent test coverage

### Structured Test Cases

Structured test cases provide:

* Repeatability
* Traceability
* Consistent coverage
* Clear expected results
* Easier regression testing
* Evidence that important scenarios were tested

However, structured test cases also have limitations. If QA follows them too rigidly, unexpected behavior outside the documented scenarios may be missed.

---

# 9. Combining Heuristics with Structured Testing

I believe the strongest approach is to use both.

Structured test cases provide a baseline.

Heuristics provide flexibility and exploration.

For example:

```text
Requirements
     ↓
Structured Test Cases
     ↓
Execute Main Scenarios
     ↓
Use Heuristics
     ↓
Explore Unexpected Behaviour
     ↓
Document Findings
```

This allows QA to maintain reliable coverage while still investigating areas that were not predicted in advance.

---

# 10. When to Be Careful With Heuristics

Heuristics should not replace requirements, acceptance criteria, or other reliable sources of expected behavior.

I would be especially cautious when:

* Requirements are available and specific
* The feature is safety-critical
* The feature handles sensitive data
* Regulatory requirements apply
* The behavior must be precisely verified
* A specific workflow has strict acceptance criteria
* Testing requires traceability

In these situations, structured testing and explicit requirements are particularly important.

Heuristics should supplement, not replace, systematic testing.

---

# 11. My QA Approach

When requirements are unclear or testing time is limited, I would use heuristics to decide where to investigate first.

My process would be:

1. Understand the feature and its purpose.
2. Identify the most important user journey.
3. Consider potential risks.
4. Test the critical path.
5. Explore boundaries and unusual inputs.
6. Change conditions to look for hidden problems.
7. Check consistency with similar functionality.
8. Investigate suspicious behavior.
9. Document evidence and remaining risks.

I would not treat a heuristic as proof that a defect exists.

If I find unexpected behavior, I would investigate it further and compare it with requirements or expected product behavior before reporting it as a confirmed bug.

---

# 12. Personal Reflection

If I had only 15 minutes to test a new Focus Bear feature, heuristics would help me focus on the areas where I could gain the most useful information.

I would start with the critical user journey, then quickly explore boundaries, invalid input, repeated actions, network problems, and unexpected navigation.

Heuristics can also help me discover edge cases because they encourage me to think about how the feature could behave differently under unusual conditions.

However, I would not want to rely only on intuition. Gut instinct is influenced by personal experience and can cause blind spots.

Structured test cases provide consistency and traceability, while heuristics allow flexibility and exploration.

The most effective approach is therefore to combine both: **use structured testing for reliable coverage and heuristics for deeper exploration.**

---

# 13. Personal QA Principle

> **Use structure for coverage, heuristics for exploration, and evidence for decisions.**
