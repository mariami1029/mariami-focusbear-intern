# Exploratory Testing, Scripted Testing & Testing as Investigation

## Introduction

Software testing is not only about executing predefined test cases and checking whether the expected result matches the actual result.

A strong QA approach combines structured testing with exploration and investigation. Scripted testing provides consistency and repeatability, while exploratory testing allows the tester to discover unexpected behaviour and investigate areas that may not have been anticipated during test design.

Testing can also be viewed as an investigative process. A tester observes behaviour, asks questions, forms hypotheses, gathers evidence, and uses the results to decide what to investigate next.

---

## 1. Exploratory Testing

Exploratory testing is an approach where learning, test design, and test execution happen together.

Instead of following a completely predefined script, the tester uses their knowledge, observations, and curiosity to decide what to test next.

A tester might start with a general mission such as:

> "Explore the new task creation feature and look for problems that could affect users."

During the session, the tester can change their approach based on what they discover.

For example:

1. Create a normal task.
2. Notice that the application automatically assigns a due date.
3. Question why the date was assigned.
4. Try different task durations.
5. Try editing the task.
6. Restart the application.
7. Check whether the due date remains consistent.
8. Investigate whether the behaviour is intentional.

The important part is that each observation can lead to a new question and a new testing direction.

---

## 2. Scripted Testing

Scripted testing uses predefined test cases or test procedures.

A typical scripted test contains:

* Preconditions.
* Test data.
* Steps.
* Expected results.
* Actual results.
* Pass/fail status.

For example:

**Test:** Create a task with valid information.

**Steps:**

1. Open the task creation screen.
2. Enter a valid task name.
3. Enter a valid duration.
4. Save the task.

**Expected result:**

The task is created successfully and appears in the task list.

Scripted testing is useful because different testers can execute the same scenario consistently.

---

## 3. Regression Testing

Regression testing verifies that existing functionality still works after changes have been made to the application.

A regression test can be manual or automated, but it usually focuses on known functionality and previously identified risks.

For example, after changing the task-management functionality, regression testing could verify:

* Existing tasks can still be created.
* Tasks can still be edited.
* Tasks can still be completed.
* Task status changes are saved.
* Existing navigation still works.
* Related functionality has not been broken.

Regression testing provides confidence that new changes have not introduced defects into previously working functionality.

---

## 4. Exploratory Testing vs. Scripted/Regression Testing

| Aspect                | Exploratory Testing            | Scripted/Regression Testing       |
| --------------------- | ------------------------------ | --------------------------------- |
| Test design           | Created during testing         | Defined beforehand                |
| Main goal             | Discover unexpected problems   | Verify known behaviour            |
| Flexibility           | High                           | Lower                             |
| Human judgement       | Very important                 | Still useful, but more structured |
| Repeatability         | Lower                          | High                              |
| Best for              | New, changing, uncertain areas | Stable and critical functionality |
| Unexpected behaviour  | Excellent for investigation    | May not be covered                |
| Regression protection | Limited by itself              | Strong                            |
| Documentation         | Session notes/findings         | Detailed test cases/results       |
| Testing mindset       | Explore and investigate        | Verify and confirm                |

Neither approach replaces the other.

A mature QA process uses both depending on context.

---

## 5. Why Regression Testing Is Important

Regression testing is important because software changes can have unintended consequences.

A developer may change one feature while accidentally affecting another feature that depends on the same code.

For example:

**Change:** Modify task status functionality.

**Potential regression areas:**

* Task creation.
* Task editing.
* Task filtering.
* Task completion.
* Dashboard statistics.
* Notifications.
* API responses.

Without regression testing, a previously working feature might break without being noticed.

Regression testing is therefore particularly valuable for stable, important functionality that must continue working after every significant change.

---

## 6. When to Use Exploratory Testing

Exploratory testing is especially useful when:

### Testing a New Feature

There may not yet be enough information to create a complete set of test cases.

Exploration can help the tester learn how the feature behaves and identify important scenarios.

### Requirements Are Unclear

When requirements contain ambiguity, exploratory testing can help identify questions that need clarification.

### The Product Changes Frequently

Rapidly changing functionality can make detailed scripted tests outdated.

Exploratory testing allows the tester to adapt quickly.

### Investigating a Bug

Once a defect is discovered, exploratory testing can help determine:

* How consistently it occurs.
* What conditions trigger it.
* Whether related functionality is affected.
* Whether there are additional variations of the same problem.

### Looking for Unknown Risks

Sometimes the biggest risk is something nobody thought to include in a test case.

Exploration is useful for discovering those unknowns.

---

## 7. When to Use Scripted or Regression Testing

Structured testing is particularly valuable when:

### Functionality Is Stable

Stable features benefit from repeatable test cases.

### The Same Checks Are Repeated Frequently

Regression suites prevent testers from repeatedly recreating the same test strategy.

### Requirements Are Well Defined

When expected behaviour is clearly documented, scripted testing provides consistent verification.

### Critical Functionality Must Be Verified

For important workflows such as authentication, payments, or data integrity, structured regression testing provides repeatable evidence that the functionality still works.

### Multiple Testers Are Involved

Detailed test cases help ensure that different testers follow the same procedure and expectations.

---

## 8. How Exploratory Testing Can Reveal Bugs Scripted Tests Miss

A scripted test normally verifies specific scenarios.

For example:

> Enter valid information → save → verify task is created.

An exploratory tester might ask additional questions:

* What happens if I save repeatedly?
* What happens if I change the duration?
* What happens if I navigate away while saving?
* What happens if the network connection is interrupted?
* What happens after restarting the application?
* What happens with unusually long input?
* What happens if two actions are performed very quickly?
* Does the behaviour remain consistent after editing?

These scenarios may not exist in the original test case.

This is one of the major strengths of exploratory testing: the tester can follow evidence rather than being restricted to the original script.

---

## 9. Testing as an Investigative Process

Testing can be treated as a form of investigation.

A tester is not simply asking:

> "Does the test pass?"

They are also asking:

> "What is really happening here, and what does it tell me about the product?"

An investigative testing cycle can look like:

**Observe → Question → Hypothesize → Test → Gather Evidence → Analyse → Follow the Lead → Report**

### Observe

Notice something unusual.

Example:

> A task behaves differently after restarting the application.

### Question

Ask why this happens.

> Is the state being saved correctly?

### Hypothesize

Create a possible explanation.

> Maybe the task state is only stored locally and is not persisted correctly.

### Test

Try a controlled experiment.

> Create the same task, restart the application, and compare the state.

### Gather Evidence

Collect:

* Screenshots.
* Screen recordings.
* Logs.
* Network requests.
* Error messages.
* Reproduction steps.
* Relevant test data.

### Analyse

Compare expected and actual behaviour.

### Follow the Lead

If the evidence suggests another possible problem, investigate it.

This process turns testing into structured problem solving rather than random clicking.

---

## 10. Questioning Skills in QA

Good testers ask questions continuously.

Useful categories of questions include:

### What?

* What exactly happened?
* What was expected?
* What changed?

### When?

* Does it happen every time?
* Does it happen only after a restart?
* Does timing affect the result?

### Where?

* Does it happen on one screen or multiple screens?
* Does it happen on a particular device or browser?

### Who?

* Does it affect every user?
* Does it depend on account type or permissions?

### Under What Conditions?

* Does it require specific data?
* Does it happen only with slow network conditions?
* Does it occur after repeated actions?

### What If?

This is especially valuable in exploratory testing.

For example:

> What if the user enters the minimum value?

> What if they enter the maximum value?

> What if they leave the field empty?

> What if they perform the action twice?

> What if they interrupt the workflow?

Questioning helps transform vague curiosity into systematic investigation.

---

## 11. Investigative Testing Techniques

Several techniques can help testers investigate behaviour systematically.

### Boundary Testing

Test values around boundaries rather than only normal values.

For example, if a field accepts 1–100:

* 0
* 1
* 2
* 99
* 100
* 101

### Equivalence Partitioning

Divide input into groups expected to behave similarly and test representative values.

### State Transition Testing

Test how the application behaves when moving between states.

For example:

**Not Started → In Progress → Completed**

The tester can also investigate invalid or unexpected transitions.

### Error Guessing

Use experience and knowledge of common failure patterns to predict where defects may exist.

### Negative Testing

Test invalid inputs and unexpected actions rather than only successful workflows.

### Change One Variable at a Time

When investigating an intermittent problem, changing one variable at a time makes it easier to identify the cause.

### Follow the Data

Track important information through the system to determine where it changes, disappears, or becomes incorrect.

---

## 12. Why Exploratory Testing Is Useful for Focus Bear

An application like Focus Bear can benefit significantly from exploratory testing because it contains workflows involving tasks, habits, focus sessions, schedules, user interactions, and application state.

Exploratory testing can help investigate interactions between these features.

For example, instead of testing only:

> "A user can create a task."

A tester could explore:

* Creating a task with different durations.
* Editing the task after creation.
* Changing its status.
* Restarting the application.
* Creating multiple tasks quickly.
* Navigating between related features.
* Using unusual input.
* Interrupting an action.
* Testing the feature under different network conditions.
* Checking whether related functionality is affected.

This type of exploration can reveal interactions and edge cases that isolated scripted tests may not cover.

---

## 13. Risks of Relying Too Much on Exploratory Testing

Exploratory testing is powerful, but relying only on exploration has disadvantages.

### Inconsistent Coverage

Different testers may explore different areas, leaving some functionality untested.

### Difficult to Repeat

Without good notes, it can be difficult to reproduce exactly what was tested.

### Regression Gaps

A previously discovered scenario may not be tested again after future changes.

### Dependence on Tester Skill

The quality of exploratory testing depends heavily on the tester's knowledge, curiosity, and ability to identify risk.

### Poor Traceability

It may be difficult to demonstrate exactly which scenarios were tested if sessions are not documented properly.

For these reasons, exploratory testing should complement rather than replace structured regression testing.

---

## 14. Risks of Relying Only on Regression Testing

The opposite extreme also creates problems.

If a team only executes existing regression tests:

* New risks may remain undiscovered.
* Test cases may become outdated.
* Unknown edge cases may be missed.
* Requirements ambiguity may go unnoticed.
* Usability problems may be overlooked.
* The team may develop false confidence because all predefined tests pass.

A product can therefore have a 100% passing regression suite and still contain serious defects.

This is because passing existing tests only proves that the tested expectations were met.

---

## 15. How to Combine Both Approaches

A practical strategy is:

### 1. Explore

Use exploratory testing to learn about new or risky functionality.

### 2. Document Important Findings

Create test cases for stable, important scenarios discovered during exploration.

### 3. Regression Test

Use those test cases to verify that important functionality continues working after changes.

### 4. Automate Where Valuable

Stable, repetitive regression scenarios can eventually be automated.

### 5. Continue Exploring

Automation should not stop exploratory testing. New changes can introduce new risks that were not previously known.

This creates a continuous testing cycle:

**Explore → Discover → Document → Regression → Automate → Explore Again**

---

## 16. Documenting an Exploratory Testing Session

Exploratory testing should not mean undocumented testing.

A useful session record can contain:

* Testing mission.
* Scope.
* Environment.
* Build/version.
* Time spent.
* Features explored.
* Test data.
* Important observations.
* Bugs discovered.
* Reproduction information.
* Screenshots or recordings.
* Follow-up questions.
* Areas that were not tested.

For example:

**Mission:** Explore task creation and editing.

**Time:** 30 minutes.

**Environment:** Windows, current application build.

**Areas explored:**

* Task creation.
* Task editing.
* Task status.
* Restart behaviour.

**Observation:**

A task's behaviour changed after restarting the application.

**Next step:**

Repeat the scenario and collect logs to determine whether the state is being persisted correctly.

This provides useful evidence without turning exploratory testing into a rigid scripted process.

---

## 17. Reporting Bugs Found During Exploration

A bug discovered through exploration should still be reported using the same principles as any other defect.

A useful bug report should include:

### Title

Clear description of the problem.

### Environment

Relevant operating system, application version/build, browser/device, etc.

### Preconditions

Anything required before reproducing the issue.

### Steps to Reproduce

Exact actions needed to reproduce the problem.

### Expected Result

What should happen.

### Actual Result

What actually happens.

### Reproduction Rate

For example:

> Reproduced 4 out of 5 attempts.

### Evidence

Relevant:

* Screenshots.
* Screen recordings.
* Logs.
* Console errors.
* Network information.

### Impact

Explain who or what is affected and why the issue matters.

Exploratory testing may produce unexpected findings, but the resulting bug report should still be clear, reproducible, and actionable.

---

## 18. Uncertainty and Curiosity as Testing Skills

Testing often involves uncertainty.

A tester may not immediately know:

* Whether behaviour is intentional.
* What causes a failure.
* How widely the problem occurs.
* Whether two symptoms have the same root cause.
* Whether a strange result is actually a defect.

Instead of immediately assuming an answer, a tester can treat uncertainty as a reason to investigate.

Curiosity encourages questions such as:

> "Why did this happen?"

> "What happens if I change this?"

> "Can I reproduce it?"

> "Does this happen elsewhere?"

> "What evidence would confirm or disprove my hypothesis?"

This mindset helps testers discover problems that simple test execution might miss.

---

## 19. Reflection

### Why is exploratory testing particularly useful for Focus Bear?

Exploratory testing is useful because Focus Bear contains multiple interacting workflows and application states. A tester can investigate how features behave together instead of testing every feature only in isolation.

It is especially useful for new or changing functionality where the full set of risks may not yet be known.

### What questions would I ask when testing a new Focus Bear feature?

I would start with questions such as:

* What is the intended user workflow?
* What happens with valid input?
* What happens with invalid or missing input?
* What are the boundaries?
* What happens if the user performs the action twice?
* What happens if the user interrupts the workflow?
* What happens after restarting the application?
* What happens if the network is slow or unavailable?
* What happens if related data changes?
* What happens on different environments?
* What happens when the feature interacts with existing functionality?
* Is the behaviour understandable from the user's perspective?

These questions help me move beyond the happy path.

### What risks come with relying too much on exploratory testing vs. only doing regression testing?

Relying too much on exploratory testing can lead to inconsistent coverage and make regression difficult to repeat.

Relying only on regression testing can create blind spots because the tester may only verify scenarios that were already known and documented.

The best approach is to combine both.

### How would I document and report issues found during an exploratory session?

I would record the testing mission, environment, test data, observations, reproduction information, and evidence.

If I discover a defect, I would create a clear bug report with reproduction steps, expected and actual results, reproduction rate, severity/priority considerations, and supporting evidence.

### How can uncertainty and curiosity make me a better tester?

Uncertainty reminds me that I may not have the complete picture, while curiosity motivates me to investigate instead of accepting the first result.

A good tester should not only verify what is expected. They should also ask whether the assumptions behind the expected behaviour are correct.

---

## Conclusion

Exploratory testing, scripted testing, and regression testing serve different purposes.

Scripted and regression testing provide consistency and repeatability. Exploratory testing provides flexibility and helps discover unknown problems. Investigative testing connects the two by encouraging testers to observe, question, form hypotheses, gather evidence, and follow meaningful leads.

The strongest QA approach is therefore not:

**Exploratory OR scripted testing**

but:

**Exploratory + structured + investigative testing**

My QA principle is:

> **Do not stop at "the test passed." Ask what else could happen, investigate the evidence, and use what you learn to improve future testing.**
