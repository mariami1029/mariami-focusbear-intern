# Testing Without Clear Requirements – MVP Mindset

## 1. Minimum Viable Behaviour

When requirements are missing or incomplete, I would first try to identify the minimum behaviour that a reasonable user would expect from the feature.

My approach would be to consider:

* What is the main purpose of the feature?
* What is the simplest behaviour that allows the user to complete that purpose?
* Is the behaviour consistent with similar features in the application?
* Does it follow common UX and industry conventions?
* Could the current behaviour confuse the user or cause data loss?
* Is there anything in the UI that explicitly communicates how the feature should work?

I would avoid assuming detailed business rules that are not documented. Instead, I would separate what is reasonably expected from what requires clarification.

For example, if a task creation form allows a user to enter a task duration but does not require a due date, I would expect the task to be created without a due date unless the application clearly explains that one will be assigned automatically. Automatically assigning a date would be something I would investigate further rather than immediately declaring it a bug.

---

## 2. Common Sense vs. Escalation

I think common sense is reasonable when the expected behaviour is obvious from the context of the feature or follows a well-established convention.

For example:

* A password field should normally hide the password.
* A successful save action should normally provide some indication that the action was completed.
* A button labelled "Cancel" should not save the user's changes.
* A deleted item should not continue appearing as if it still exists.

However, I would escalate when the behaviour depends on a business decision, product-specific rule, or information that cannot be determined from the UI.

I would ask a developer or PM when:

* Multiple behaviours could be considered valid.
* The requirement could be interpreted in different ways.
* The behaviour affects important user data.
* I cannot determine the expected result from the feature's purpose or UI.
* Reporting the behaviour as a bug could result in changing intentional product behaviour.

Instead of guessing, I would ask a specific question such as:

> "When a user creates a task without selecting a due date, should the application automatically assign one, or should the task remain without a due date?"

This is more useful than simply asking, "Is this a bug?"

---

## 3. How Silent Assumptions Affect Testing

Silent assumptions can lead to both missed defects and false bug reports.

If a tester assumes that a feature must work in a particular way, they may report intentional behaviour as a bug. On the other hand, if they assume that something is "probably fine", they may overlook a real usability or functional problem.

For example, during my Focus Bear testing, I noticed that different newly created tasks displayed the same TOP Score values. Since the tasks had different durations and purposes, I initially questioned whether the score was being calculated dynamically.

Instead of immediately assuming that the calculation was broken, I would first investigate:

1. Whether the TOP Score is supposed to depend on task characteristics.
2. Whether the displayed values are default values.
3. Whether users are expected to be able to modify the parameters.
4. Whether the product documentation explains how the score is calculated.

Only after understanding the intended behaviour would I decide whether this should be reported as a functional bug, a usability issue, or expected behaviour.

This example showed me that observing unexpected behaviour is not the same as proving that something is a bug.

---

## 4. Questions for Developers or Product Managers

When requirements are ambiguous, I would try to ask questions that are specific and easy to answer.

Useful questions include:

* What is the expected result when this field is left empty?
* Is this value automatically generated or should the user provide it?
* Is this behaviour intentional?
* What should happen if the user performs this action multiple times?
* Should this information persist after restarting the application?
* Which status should be displayed after this action?
* Is this feature required for the MVP, or is it planned for a future release?
* Are there any business rules that are not visible in the UI?
* What should happen in edge cases such as invalid, empty, or unexpected input?

I would try to provide the observed behaviour and the specific ambiguity instead of making a vague request for clarification.

---

# 5. Reflection: An Ambiguous Focus Bear Feature

### Feature: TOP Score

One Focus Bear feature that I found potentially ambiguous during exploratory testing was the TOP Score assigned to tasks.

I created multiple tasks with different durations and purposes, but the newly created tasks displayed the same TOP Score and the same underlying parameters. The values also could not be manually adjusted.

### What I would consider Minimum Viable Behaviour

For the MVP, I would expect the application to do at least one of the following:

* Calculate the TOP Score based on clearly defined task characteristics, or
* Provide default values and clearly explain that these are default values, or
* Allow the user to adjust the parameters if the score is intended to reflect the user's own assessment.

The most important minimum behaviour is that the user should be able to understand what the score means and why a particular score has been assigned.

### What I Would Escalate

Before concluding that the calculation is incorrect, I would ask the product team:

> "Are TOP Score parameters expected to be automatically calculated from the task information, or are the same default values intentionally applied to every new task?"

I would also ask whether users are expected to have control over these parameters.

This would prevent me from reporting intentional product behaviour as a bug.

---

# 6. Example of a Wrong Assumption

A hypothetical example would be a task status.

Suppose the task list displays a status called "Done", while the task creation form uses "Completed". I might initially assume that these represent different states and report the inconsistency as a bug.

However, after investigating the application, I might discover that "Completed" in the creation/edit form maps directly to "Done" in the task list.

In that situation, the behaviour itself may be correct, while the terminology could simply be a UX consistency issue.

This demonstrates why I should distinguish between:

**"The system does not work correctly"**

and

**"The system works, but the way it is presented may be confusing."**

The second case may still be worth reporting, but it should be reported as a usability or UX concern rather than automatically being classified as a functional defect.

---

# 7. My Rule of Thumb: Assume vs. Ask

My personal rule of thumb is:

> **Assume the obvious, question the important.**

I can use common sense for simple behaviours that follow standard UX conventions and do not involve important business logic.

However, when the behaviour depends on a product decision, business rule, user data, or multiple reasonable interpretations, I should stop assuming and ask for clarification.

As a QA tester, my goal is not to prove that my assumption is correct. My goal is to understand the intended behaviour and verify whether the product meets it.

Therefore, when I am unsure, I would rather ask one clear question early than make an incorrect assumption and spend time testing against the wrong expected behaviour.
