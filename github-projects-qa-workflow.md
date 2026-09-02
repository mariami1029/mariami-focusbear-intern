# Getting Familiar with GitHub Projects

## Introduction

GitHub Projects is a project management tool integrated with GitHub. It can be used to organise issues, track work, manage priorities, and visualize the progress of tasks.

For QA teams, GitHub Projects can provide a central place to track testing tasks, bugs, investigations, and other QA-related work.

Instead of keeping track of tasks separately, the team can use issues and project views to understand what needs to be done, what is currently being worked on, and what has already been completed.

---

## 1. What Are GitHub Projects?

GitHub Projects allows teams to organise and manage GitHub work items such as issues and pull requests.

Projects can be represented using different views, including:

* Table views.
* Board views.
* Roadmap views.

A board view is particularly useful for QA because tasks can be visualised according to their current status.

For example:

**To Do → In Progress → Review → Done**

Each item can represent a GitHub issue or pull request.

This makes it easier to see the current state of work without opening every individual issue.

---

## 2. GitHub Issues and Projects

GitHub Issues are used to describe and track individual pieces of work.

An issue could represent:

* A bug.
* A feature request.
* A testing task.
* A technical task.
* An investigation.
* A documentation task.

GitHub Projects can then organise these issues into a larger workflow.

For example:

**Issue:** Login fails with valid credentials.

The issue can be added to the QA project and moved through the relevant project statuses as the team works on it.

This creates a connection between the detailed issue information and the overall project workflow.

---

## 3. Creating a Bug Issue

When I find a bug during testing, I would create a clear and actionable GitHub Issue.

A good bug issue should contain enough information for another team member to understand and reproduce the problem.

### Bug Title

The title should be concise and describe the problem.

For example:

> Login fails when valid credentials are submitted

This is more useful than:

> Login broken

because it provides more specific information.

### Description

The description should explain the problem and provide relevant context.

A typical structure could be:

* Summary.
* Environment.
* Preconditions.
* Steps to reproduce.
* Expected result.
* Actual result.
* Reproduction rate.
* Severity/impact.
* Evidence.

### Example

**Summary:** Login fails with valid credentials.

**Environment:** Windows, current application build.

**Preconditions:** A valid user account exists.

**Steps to reproduce:**

1. Open the login page.
2. Enter valid credentials.
3. Select the Login button.

**Expected result:**

The user is successfully authenticated and taken to the dashboard.

**Actual result:**

The login request fails and the user remains on the login page.

**Reproduction rate:**

5/5 attempts.

**Impact:**

Users may be unable to access the application.

**Evidence:**

Screenshot, screen recording, and relevant console/network information.

The exact information should be adjusted according to the issue and the project requirements.

---

## 4. Assigning Issues

An issue can be assigned to a team member who is responsible for investigating or completing it.

For example:

* A QA task may be assigned to a tester.
* A development bug may be assigned to a developer.
* A documentation task may be assigned to its owner.

Assigning an issue helps clarify ownership.

However, assigning an issue does not necessarily mean that only that person can contribute to it. Other team members can still provide comments, evidence, investigation results, or suggestions.

---

## 5. Labels

Labels are used to categorize GitHub Issues.

Examples include:

* `bug`
* `feature`
* `documentation`
* `testing`
* `high-priority`
* `blocked`
* `enhancement`

Labels make it easier to filter and identify related issues.

For QA, labels can help distinguish bugs from testing tasks and highlight issues that require special attention.

For example:

> `bug` + `high-priority` + `authentication`

can quickly communicate important characteristics of an issue.

Labels should be used consistently so that they remain useful across the project.

---

## 6. Milestones

Milestones group issues that belong to a larger goal or release.

For example, a project could have milestones such as:

* Version 1.0.
* Version 1.1.
* MVP.
* Sprint 5.
* Onboarding.

A QA team can use milestones to understand which issues are associated with a particular release or objective.

For example:

> A critical login bug could be associated with the release milestone for the next version.

This helps the team track whether important work is completed before a release.

---

## 7. Assignees

An assignee is the person responsible for an issue.

Using assignees helps answer:

> "Who is currently responsible for this task?"

This is especially useful when a project contains many issues.

For QA work, clear ownership can prevent issues from being overlooked.

---

## 8. Project Columns and Status

A GitHub Project board can represent the workflow of an issue.

A simple workflow could be:

**To Do → In Progress → Review → Done**

### To Do

The issue is ready to be worked on but has not started.

### In Progress

Someone is actively working on the issue.

### Review

The work has been completed and requires review or validation.

### Done

The required work has been completed and verified.

The exact statuses can vary depending on the team's workflow.

For example, a QA-focused workflow might be:

**Backlog → Ready for Testing → Testing → Failed/Blocked → Ready for Verification → Done**

The important principle is that statuses should clearly communicate the current state of work.

---

## 9. Tracking QA Work With GitHub Projects

GitHub Projects can help QA testers track work from beginning to completion.

For example:

### Backlog

Potential testing tasks and bugs that have not yet been prioritized.

### To Do

Tasks selected for current work.

### In Progress

Testing or investigation is currently happening.

### Blocked

Testing cannot continue because something is preventing progress.

### Ready for Verification

A fix is available and needs QA validation.

### Done

The issue has been tested and the required work is complete.

This gives the team visibility into the current testing workload.

---

## 10. Prioritising Issues

Not every issue should receive the same level of attention.

Issues can be prioritized using factors such as:

* Severity.
* User impact.
* Business impact.
* Probability of occurrence.
* Number of affected users.
* Security implications.
* Release deadlines.
* Dependencies.
* Effort required.

A critical authentication issue should generally receive more immediate attention than a minor cosmetic issue.

For example:

| Issue                      | Impact   | Priority  |
| -------------------------- | -------- | --------- |
| Application cannot start   | Critical | Very High |
| Users cannot log in        | Critical | Very High |
| Task data is not saved     | High     | High      |
| Minor text alignment issue | Low      | Low       |

Priority should be based on context and risk rather than simply on how easy an issue is to notice.

---

## 11. Using GitHub Projects to Prioritise QA Work

A QA tester can use several mechanisms to make priorities visible.

### Labels

For example:

* `critical`
* `high-priority`
* `blocked`

### Milestones

Issues can be associated with a specific release or objective.

### Project Fields

Projects can use custom fields such as:

* Priority.
* Status.
* Risk.
* Effort.
* Team.
* Target release.

### Sorting and Filtering

Project views can be filtered or sorted to focus on the most important work.

For example, a tester could create a view showing:

> High-priority bugs that are currently ready for testing.

This reduces the time needed to search through unrelated issues.

---

## 12. Example QA Workflow

A practical QA workflow could look like:

**1. Discover**

A tester finds an issue during manual or exploratory testing.

↓

**2. Create Issue**

The tester documents the problem clearly.

↓

**3. Categorize**

Add appropriate labels and priority information.

↓

**4. Assign**

Assign the issue to the appropriate person when ownership is clear.

↓

**5. Add to Project**

Place the issue into the appropriate GitHub Project.

↓

**6. Prioritize**

Determine where it belongs relative to other work.

↓

**7. Development**

The developer investigates and fixes the issue.

↓

**8. Verification**

QA validates the fix.

↓

**9. Regression**

Relevant related functionality is checked.

↓

**10. Done**

The issue is closed when the required work and verification are complete.

---

## 13. Example: Tracking a Focus Bear Bug

Imagine a tester discovers that a task's status is displayed inconsistently in different parts of the application.

A QA issue could be created with:

**Title:**

> Task status terminology is inconsistent between task list and Add Task modal

**Labels:**

* `bug`
* `UI`
* `testing`

**Priority:**

Medium, depending on the impact.

**Project status:**

`To Do`

The issue could then move through:

**To Do → In Progress → Ready for Verification → Done**

When a fix is provided, QA would verify:

* The original problem is fixed.
* Related status values are consistent.
* Existing task workflows still work.
* No new regression issues were introduced.

The exact project statuses and labels should follow the team's existing conventions.

---

## 14. Advantages of GitHub Projects for QA

### Visibility

The team can quickly see what is being worked on and what remains.

### Organisation

Issues can be grouped by status, priority, milestone, or other project fields.

### Collaboration

Developers, QA testers, and other team members can work from the same source of information.

### Traceability

A QA task can be connected to an issue, pull request, milestone, and project status.

### Prioritisation

Important issues can be identified and worked on first.

### Progress Tracking

Moving an issue through project statuses provides a clear picture of progress.

### Centralised Information

Instead of tracking work across separate documents or messages, important information can remain connected to the relevant GitHub Issue.

---

## 15. Limitations and Things to Watch For

GitHub Projects is useful, but the tool itself does not guarantee good project management.

Problems can occur if:

* Issues are poorly written.
* Statuses are not updated.
* Labels are used inconsistently.
* Priorities are unclear.
* Issues have no owner.
* Completed work is not moved to the correct status.
* The project contains too many unnecessary fields.
* Important information is kept outside the issue.

A project board is only useful when the team keeps it accurate and up to date.

---

# Reflection

## How would I create a new issue for a bug found during testing?

I would first confirm the problem and collect enough evidence to describe it accurately.

Then I would create a GitHub Issue with:

* A clear title.
* Summary.
* Preconditions.
* Reproduction steps.
* Expected result.
* Actual result.
* Environment.
* Reproduction rate.
* Impact/severity.
* Supporting screenshots, recordings, logs, or other evidence.

I would then apply the appropriate labels, priority, milestone, and assignee according to the team's workflow and add the issue to the relevant GitHub Project.

---

## How can I prioritise issues in a GitHub Project?

I would consider severity, user impact, business impact, likelihood, security implications, dependencies, and release deadlines.

For example, an issue preventing users from logging in should normally be prioritized above a minor visual defect.

I would use project fields, labels, milestones, and sorting/filtering to make priorities visible and focus on the highest-risk work first.

---

## What are some advantages of using GitHub Projects for tracking QA tasks?

The main advantages are visibility, organisation, collaboration, traceability, prioritisation, and progress tracking.

It allows QA work to be connected directly to GitHub Issues and development work, making it easier for the whole team to understand what needs testing, what is currently being investigated, what is blocked, and what has already been verified.

---

# Conclusion

GitHub Projects provides a practical way to organise QA work and connect individual issues with the broader development workflow.

For QA, a useful workflow is:

**Discover → Report → Prioritize → Track → Verify → Regress → Complete**

Issues provide detailed information about individual problems, while GitHub Projects provide a higher-level view of progress and priorities.

The most important part is not simply creating a project board. The team must keep issues accurate, update statuses consistently, communicate clearly, and prioritize work according to risk and impact.

My QA principle is:

> **Keep the work visible, keep issues actionable, and keep priorities aligned with risk.**
