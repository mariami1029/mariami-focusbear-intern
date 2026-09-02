# Release Cycles & Version Control — QA Reflection

## 1. Software Release Cycle

A software release cycle is the process a software product goes through from development to being available to users. QA is involved throughout this process to help identify defects and reduce release risks.

A typical release cycle includes the following stages:

### Development

Developers implement new features, improvements, and bug fixes.

QA can already contribute during this stage by:

* Reviewing requirements and acceptance criteria
* Identifying possible risks and edge cases
* Preparing test scenarios and test data
* Asking questions about unclear requirements
* Testing individual changes when they become available

### Testing

The new functionality is deployed to a testing environment where QA performs different types of testing.

Typical activities include:

* Functional testing
* Regression testing
* Integration testing
* API testing
* Exploratory testing
* Negative and edge-case testing
* Cross-browser or cross-device testing when necessary

The goal is to verify that the change works as expected and has not introduced unexpected regressions.

### Staging

Staging is an environment that is intended to be similar to production.

QA performs final validation before the release reaches real users.

Testing may include:

* Smoke testing
* Critical user journeys
* Integration checks
* Configuration validation
* Regression testing of high-risk areas
* Final verification of important fixes

Staging is useful because some problems may only appear when the application runs in a production-like environment.

### Production

The software is released to real users.

QA performs post-release verification to make sure the deployment was successful.

Important checks may include:

* Application availability
* Login and authentication
* Critical user workflows
* Important API integrations
* Data integrity
* Error rates
* Performance and responsiveness

QA may also monitor user reports and production issues after release.

### Release Cycle Overview

```text
Development
     ↓
Testing
     ↓
Staging
     ↓
Production
     ↓
Post-Release Monitoring
```

---

## 2. Feature Release vs. Hotfix

QA strategy depends on the size and risk of the change.

### Feature Release

A feature release introduces significant new functionality or a larger set of changes.

Because more code and functionality may be affected, QA usually needs broader testing.

QA may perform:

* Requirement analysis
* Test planning
* Functional testing
* Integration testing
* Regression testing
* Exploratory testing
* Cross-browser/device testing
* Performance testing when relevant
* Accessibility testing when relevant
* Final smoke testing

A major feature release should receive more extensive testing because the probability of introducing regressions is generally higher.

### Hotfix

A hotfix is an urgent change intended to resolve a serious production problem.

The testing process is usually more focused because the fix needs to reach users quickly.

QA should:

1. Reproduce the production issue.
2. Verify that the fix resolves the problem.
3. Test the directly affected functionality.
4. Perform targeted regression testing.
5. Check critical user journeys that could be affected.
6. Verify the fix after deployment.

The goal is to balance **speed and risk** without skipping important validation.

### Feature Release vs. Hotfix

| Area          | Feature Release                   | Hotfix                                   |
| ------------- | --------------------------------- | ---------------------------------------- |
| Scope         | Usually larger                    | Usually smaller and focused              |
| Testing       | Broad                             | Targeted and risk-based                  |
| Regression    | Wider regression                  | Targeted regression                      |
| Time pressure | Normal                            | Usually high                             |
| Risk          | New functionality and regressions | Fix may introduce new problems           |
| QA focus      | Overall feature quality           | Fix correctness and production stability |

---

## 3. What Is Version Control?

Version control is a system that records changes to files over time.

Git is one of the most widely used version control systems.

Git allows teams to:

* Track changes
* See who changed something
* Review previous versions
* Create branches
* Merge changes
* Revert changes
* Collaborate without overwriting each other's work

For QA, version control is important because the exact version of the software can affect test results.

For example, if a bug exists in version `2.5.0` but was fixed in `2.5.1`, testing the wrong version could lead to an incorrect conclusion.

QA should therefore know:

* Which version is being tested
* Which branch contains the change
* Which commit or build was deployed
* Whether the environment contains the expected code

---

## 4. Git Branches

A Git branch is an independent line of development.

Teams commonly use branches such as:

```text
main
develop
feature/login
bugfix/payment-error
release/2.5.0
hotfix/2.5.1
```

The exact branching strategy depends on the team.

### Why Do Testers Need to Know About Branches?

A bug may behave differently depending on which branch or build is being tested.

For example:

```text
main
  │
  ├── feature/new-dashboard
  │
  └── hotfix/login-error
```

The `feature/new-dashboard` branch may contain unfinished changes, while `main` may contain the latest stable version.

QA should therefore confirm the correct branch/build before testing.

Knowing the branch also helps QA:

* Understand what changes are included
* Reproduce branch-specific bugs
* Identify whether a fix has been merged
* Understand why behavior differs between environments
* Communicate accurately with developers

---

## 5. QA and Version Identification

Knowing exactly which version of the application is being tested is essential.

A bug report should include relevant version information such as:

* Application version
* Build number
* Git branch, when relevant
* Commit SHA, when available
* Environment
* Browser/device/OS
* Date and time of testing

For example:

> **Version:** 2.5.1
> **Environment:** Staging
> **Branch:** release/2.5.1
> **Browser:** Chrome
> **OS:** Windows 11

This information makes the bug easier to reproduce and investigate.

Without version information, a developer may test a different build and conclude that the bug cannot be reproduced.

---

## 6. Handling a Bug That Only Happens on an Older Branch

If a developer says:

> "This bug only happens on an older branch."

I would not immediately assume that the bug is irrelevant.

First, I would clarify:

* Which branch contains the bug?
* Which commit or build was tested?
* Which version is affected?
* Is the branch still supported?
* Is the branch used by any users or environments?
* Was the issue fixed in a newer branch?
* Was the fix actually merged into the relevant release branch?

Then I would reproduce the issue on the reported branch/build and compare it with the current version.

I would document the results clearly.

For example:

```text
Affected branch: release/2.4.0
Affected build: 2.4.0-145
Current main: 2.5.0
Result: Issue reproduced on release/2.4.0 but not reproduced on main.
```

If the older branch is still used in production or is part of a supported release, the issue may still require attention.

If the branch is obsolete and no longer supported, the team can decide whether the issue should be fixed or closed based on the project's support policy.

The important point is to **verify the scope and impact instead of making assumptions**.

---

## 7. Rollbacks

A rollback means returning the application to a previous stable version after a problematic release.

For example:

```text
Version 2.5.0
     ↓
Production Release
     ↓
Critical problem discovered
     ↓
Rollback
     ↓
Version 2.4.5
```

A rollback may be necessary when a release causes:

* Critical functionality failures
* Data integrity problems
* Severe performance issues
* Widespread application errors
* Security problems
* Major production instability

### QA's Role During a Rollback

QA should help verify that:

1. The previous stable version has been restored.
2. The original production problem is no longer present.
3. Critical user journeys work correctly.
4. Important integrations are functioning.
5. Data has not been corrupted or lost.
6. The environment is stable.

After the rollback, QA should also help investigate the original release to understand what went wrong and what testing or process improvements could prevent a similar issue.

---

## 8. Testing Strategy: Major Feature vs. Small Bug Fix

I would adjust my testing strategy based on the scope, risk, and potential impact of the change.

### Major Feature Release

For a major feature, I would use a broader testing strategy.

I would:

* Review requirements carefully
* Identify affected areas
* Create test scenarios
* Test positive and negative cases
* Perform exploratory testing
* Test integrations
* Perform regression testing
* Check important edge cases
* Test different environments/devices when relevant
* Verify critical existing workflows

I would also communicate risks early instead of waiting until the end of the release.

### Small Bug Fix

For a small bug fix, I would use a more targeted approach.

I would:

1. Reproduce the original bug.
2. Verify the fix.
3. Test nearby functionality that could be affected.
4. Perform targeted regression testing.
5. Check the relevant critical workflow.
6. Verify that the fix works in the intended environment.

Even a small change should not be assumed to be risk-free.

---

## 9. Why Knowing the Version Matters

It is important for QA to know exactly which version of the application is being tested because different versions can contain different code, features, fixes, and bugs.

Without version information:

* Bugs may be difficult to reproduce.
* QA may test the wrong code.
* Developers may investigate a different build.
* A bug may appear fixed simply because a different version was tested.
* Regression results may be inaccurate.

Version information creates a clear connection between:

**Requirement → Code → Build → Environment → Test Result → Bug Report**

This makes testing and debugging much more reliable.

---

## 10. My QA Approach

When testing a release, I would first identify the **scope and risk of the changes**.

For a large feature release, I would increase test coverage and include broader regression testing.

For a small bug fix, I would focus on reproducing the original problem, verifying the fix, and testing the areas most likely to be affected.

I would always confirm the application version, environment, and relevant Git branch or build before starting testing.

If a bug is reported on an older branch, I would verify the exact branch and build, reproduce the issue, check whether the branch is still supported, and compare the behavior with newer versions.

For a major production problem, I would support the team in validating a rollback and confirming that the application has returned to a stable state.

---

## 11. Personal QA Principle

> **Know what changed, know what version you are testing, and adjust testing based on risk.**

Understanding release cycles and Git helps QA test the right software at the right time and communicate defects with enough context for the team to act on them.
