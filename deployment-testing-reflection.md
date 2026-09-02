# Understanding Deployment & Hotfix Testing

## 1. Scheduled Release, Rollback, and Hotfix

Software releases can happen in different ways depending on the situation.

### Scheduled Release

A scheduled release is a planned deployment of new or updated functionality to a production environment.

Before a scheduled release, QA may perform:

* Functional testing.
* Regression testing.
* Integration testing.
* API testing.
* Cross-browser or cross-platform testing when relevant.
* Acceptance testing.
* Verification of known risks and critical user flows.

After deployment, QA performs post-release checks to make sure the production version is working as expected.

---

### Rollback

A rollback means returning the application to a previous stable version after a deployment causes a serious problem.

For example, if a new release causes users to be unable to log in, the team may decide that restoring the previous version is safer than keeping the broken release in production.

A rollback is mainly focused on **restoring stability**.

QA should then verify that:

* The previous version is available.
* The critical problem is no longer present.
* Important functionality works again.
* The rollback itself did not introduce additional problems.

---

### Hotfix

A hotfix is an urgent change released to address a serious problem, usually without waiting for the next planned release.

For example, if a critical production bug prevents users from completing an important action, the team may prepare a hotfix.

Because hotfixes are usually developed under time pressure, QA needs to balance speed with sufficient risk-based validation.

---

# 2. What QA Should Test Immediately After Deployment

After a deployment, QA should first perform a **smoke test** or set of critical post-deployment checks.

The goal is to quickly determine whether the application is fundamentally working.

Important checks may include:

### Application availability

* Can the application be opened?
* Are the main pages loading?
* Are there obvious server or deployment errors?

### Authentication

* Can users log in?
* Can users log out?
* Do important authentication flows work?

### Critical user journeys

The most important business flows should be checked first.

For example:

* Creating or editing important data.
* Completing the application's primary workflow.
* Saving changes.
* Navigating between critical sections.

### API and integrations

Where relevant:

* Are important API endpoints responding?
* Are requests returning expected status codes?
* Are important integrations functioning?

### Data integrity

QA should check that important existing data is still available and behaves correctly after deployment.

### Environment-specific issues

The production environment can behave differently from a development or test environment, so QA should pay attention to configuration, permissions, URLs, services, and other environment-specific factors.

The initial goal is not to perform a complete regression test immediately. It is to quickly determine whether the release is stable enough for continued use and deeper testing.

---

# 3. How QA Handles Hotfix Testing

When a critical production bug is discovered, QA should first understand the impact and urgency of the issue.

A practical hotfix workflow is:

`Production Bug → Investigation → Fix → Targeted Testing → Regression Check → Deployment → Post-Deployment Verification`

### Step 1: Understand the defect

QA should understand:

* What is broken?
* Who is affected?
* How severe is the problem?
* Can it be reproduced?
* What functionality is affected?

### Step 2: Understand the proposed fix

QA should understand what the developer changed and which functionality could be affected by the change.

### Step 3: Test the fix

The original bug should be reproduced when possible and then tested again after the fix.

The goal is to confirm:

**The original problem is resolved.**

### Step 4: Perform targeted regression testing

QA should test the functionality directly related to the change and the areas most likely to be affected.

### Step 5: Deploy and verify

After deployment, QA should perform post-release checks in production to confirm that the hotfix works in the real environment.

---

# 4. Preventing New Bugs in Urgent Fixes

Hotfixes are risky because there may be less time for testing.

Several practices can reduce the risk.

## Keep the change as small as possible

The smaller and more focused the fix, the smaller the potential regression surface.

## Reproduce before and after

If possible, QA should confirm that the original bug exists before the fix and no longer occurs after the fix.

## Perform targeted regression testing

Testing should focus not only on the exact bug but also on related functionality.

## Review dependencies

The team should consider whether the fix affects APIs, databases, authentication, integrations, or other components.

## Use automated tests where available

Existing automated tests can provide fast feedback and help detect obvious regressions.

## Communicate risk clearly

If time limitations prevent complete regression testing, QA should communicate what was tested, what was not tested, and what risks remain.

## Avoid unnecessary changes

A hotfix should generally focus on solving the critical problem rather than introducing unrelated improvements.

---

# 5. Post-Release Monitoring

QA is not necessarily finished when deployment is complete.

Post-release monitoring can include:

* Application health monitoring.
* Error logs.
* Crash reports.
* Performance metrics.
* API monitoring.
* User reports.
* Customer support feedback.
* Analytics and unusual behaviour detection.

Different teams may use different tools and processes for monitoring.

For example, development and operations teams may monitor system health and errors, while customer support may identify problems reported directly by users.

QA can help by validating reported production problems, reproducing them when possible, and checking that fixes resolve the issue.

---

# 6. If Users Immediately Report Problems After Release

If users start reporting problems immediately after a release, I would first avoid assuming that every report is caused by the deployment.

I would:

1. Collect the reported symptoms.
2. Check whether the problem is reproducible.
3. Identify how many users or workflows are affected.
4. Compare the issue with recent deployment changes.
5. Determine the severity and business impact.
6. Communicate the issue to the appropriate team members.
7. Help investigate whether a rollback or hotfix may be required.
8. Test the proposed solution.
9. Perform post-deployment verification after the fix.

If the issue is critical and the release has caused major disruption, restoring a stable version through a rollback may be safer than waiting for a more complex fix.

The response should be based on impact and risk rather than panic.

---

# 7. Prioritizing Testing During a Hotfix

When working under time pressure, I would use **risk-based testing** rather than trying to test everything.

My priority would be:

### Priority 1 — The reported critical bug

First, verify that the original problem is fixed.

### Priority 2 — Directly affected functionality

Test the functionality surrounding the change.

### Priority 3 — Critical user journeys

Check the most important workflows that could be affected by the fix.

### Priority 4 — High-risk integrations

If the change involves an API, database, authentication system, or external integration, test the relevant connection.

### Priority 5 — Broader regression

If time and resources allow, perform additional regression testing.

This approach allows QA to provide meaningful confidence without pretending that complete testing is possible when there is very limited time.

---

# 8. Keeping Production Stable While Fixing Bugs Quickly

QA can help maintain production stability by balancing **speed, risk, and coverage**.

I would suggest the following approach:

* Keep hotfixes small and focused.
* Clearly define the problem being fixed.
* Reproduce the issue.
* Test the fix directly.
* Perform targeted regression testing.
* Run relevant automated checks.
* Communicate remaining risks.
* Perform smoke testing after deployment.
* Monitor the production environment.
* Be prepared to rollback if the fix causes a serious new problem.

Fast delivery should not mean skipping all testing. Instead, testing should become more focused on the highest-risk areas.

---

# 9. Example Hotfix Scenario

Imagine that users suddenly cannot create new tasks after a production deployment.

A possible QA response would be:

### Before the fix

* Reproduce the problem.
* Confirm that task creation fails.
* Identify the affected workflow.
* Check whether existing tasks are affected.

### During the fix

* Understand what the developer changed.
* Identify related functionality that could be affected.
* Prepare targeted tests.

### After the fix

* Confirm that new tasks can be created.
* Test relevant task fields and validation.
* Check editing and viewing tasks.
* Verify that existing tasks still work.
* Perform a small regression check around task management.

### After deployment

* Perform the same critical checks in production.
* Monitor for new errors.
* Check whether users can successfully create tasks again.

If the hotfix causes a serious new problem, the team should evaluate whether rolling back is safer.

---

# 10. My QA Approach to Deployment Testing

As a QA engineer, I would divide deployment testing into three stages:

### Before deployment

* Understand the changes.
* Identify high-risk functionality.
* Review test coverage.
* Prepare smoke and regression checks.
* Confirm important known issues.

### Immediately after deployment

* Check application availability.
* Perform smoke testing.
* Test critical user journeys.
* Verify the specific functionality changed by the release.
* Check important integrations.

### After release

* Monitor reported issues and available system information.
* Investigate unexpected behaviour.
* Reproduce production bugs when possible.
* Verify fixes.
* Communicate risks and findings to the team.

This approach allows QA to provide fast feedback while still protecting product stability.

---

# 11. Reflection

The main thing I learned is that deployment testing is not simply about checking whether the application opens after a release.

QA needs to think about **risk, user impact, and the changes introduced by the deployment**.

I also learned that hotfix testing requires a different mindset from normal regression testing. When time is limited, it is not realistic to test every part of the application equally. Instead, QA should first verify the critical fix and then focus on the functionality most likely to be affected.

If users report problems immediately after a release, I should stay calm, gather evidence, assess the impact, and communicate clearly with the team. Depending on the severity, the appropriate response may be a targeted hotfix or a rollback to a known stable version.

My personal principle is:

> **Move quickly when necessary, but never stop thinking about risk.**
