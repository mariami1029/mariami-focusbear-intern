# How to Write Effective GitHub Issues — QA Reflection

## 1. What Makes a Good GitHub Issue?

A good GitHub issue should provide enough information for the team to understand the problem or task without unnecessary back-and-forth communication.

A well-structured issue should be:

* Clear
* Specific
* Reproducible when applicable
* Evidence-based
* Concise but complete
* Easy to understand
* Actionable

For a bug report, useful components include:

1. **Title**
2. **Description**
3. **Environment**
4. **Steps to Reproduce**
5. **Expected Result**
6. **Actual Result**
7. **Reproduction Rate**
8. **Severity/Impact**
9. **Evidence**
10. **Additional Context**

### Example Structure

```text
Title:
Application crashes when starting a Focus Session

Environment:
- App version: 2.5.1
- OS: Windows 11
- Device: [device]
- Network: Wi-Fi

Steps to Reproduce:
1. Open Focus Bear.
2. Navigate to Focus Sessions.
3. Select a task.
4. Start a Focus Session.

Expected Result:
The Focus Session starts successfully.

Actual Result:
The application closes unexpectedly.

Reproduction Rate:
3/10 attempts

Evidence:
Crash log and screen recording attached.
```

The exact fields can vary depending on the team's issue template and workflow.

---

## 2. Bug Report

A **bug report** describes behavior that does not work as expected.

The purpose is to give developers enough information to understand, reproduce, investigate, and fix the problem.

A good bug report should answer:

* What is wrong?
* Where does it happen?
* How can it be reproduced?
* What should happen?
* What actually happens?
* Who or what is affected?
* What evidence is available?

### Example

**Title:**
`[Bug] Focus Bear crashes when starting a Focus Session`

**Description:**

The application occasionally crashes when a user attempts to start a Focus Session.

**Steps to Reproduce:**

1. Open Focus Bear.
2. Navigate to Focus Sessions.
3. Select a task.
4. Start the Focus Session.

**Expected Result:**

The Focus Session should start and the user should remain in the application.

**Actual Result:**

The application closes unexpectedly.

**Reproduction Rate:**

3 out of 10 attempts.

**Environment:**

* Application version: 2.5.1
* OS: Windows 11
* Device: [device]
* Network: Wi-Fi

**Evidence:**

* Screen recording attached
* Crash information attached, if available

This gives the developer a clear starting point for investigation.

---

# 3. Feature Request

A **feature request** proposes new functionality or an improvement that does not necessarily represent a defect.

For example:

```text
Title:
[Feature] Add an option to pause a Focus Session

Description:
Users should be able to temporarily pause an active Focus Session without ending it.

Expected Behaviour:
- User clicks "Pause".
- The session timer stops.
- User can resume the session later.
- The elapsed time is preserved.
```

The key difference is that a feature request asks the team to **add or change functionality**, rather than fix something that is already behaving incorrectly.

---

# 4. Technical Task

A **technical task** describes work that needs to be completed from a technical or engineering perspective.

It may not directly represent a user-facing feature or bug.

Examples include:

* Upgrade a dependency
* Improve test coverage
* Refactor a component
* Configure a CI/CD workflow
* Add automated API tests
* Improve logging
* Update documentation
* Optimize database queries

For example:

```text
Title:
[Technical Task] Add automated regression tests for authentication

Description:
Create automated tests covering the main authentication flows.

Requirements:
- Test successful login.
- Test invalid credentials.
- Test empty fields.
- Test session expiration.
- Add the tests to the CI pipeline.
```

---

# 5. Bug Report vs. Feature Request vs. Technical Task

| Type            | Purpose                                 | Example                        |
| --------------- | --------------------------------------- | ------------------------------ |
| Bug Report      | Report unexpected or incorrect behavior | App crashes during login       |
| Feature Request | Request new or improved functionality   | Add a pause button             |
| Technical Task  | Track technical work                    | Add automated regression tests |

Understanding the difference helps the team organize work correctly.

---

# 6. GitHub Labels

Labels help categorize and filter issues.

Examples include:

* `bug`
* `feature`
* `documentation`
* `testing`
* `enhancement`
* `technical-debt`
* `priority-high`
* `blocked`

For QA, labels can make it easier to find bugs and understand what type of work an issue represents.

Labels should be used consistently according to the team's conventions.

---

# 7. Milestones

A GitHub milestone groups issues around a larger goal, release, or deadline.

For example:

```text
Milestone: Release 2.5.0

Issues:
- Fix login error
- Test new dashboard
- Update onboarding
- Regression testing
```

Milestones help the team track progress toward a specific release or objective.

---

# 8. Assignees

An assignee identifies the person responsible for working on an issue.

For example:

```text
Issue → Fix login error
Assignee → Developer A
```

This makes ownership clearer and reduces the possibility of an issue being overlooked.

An issue should not necessarily be assigned to someone without following the team's workflow or ownership conventions.

---

# 9. GitHub Projects

GitHub Projects can provide a visual way to manage issues through a workflow.

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

This allows the team to see:

* What needs to be done
* What is currently being worked on
* What is waiting for review
* What has been completed
* Which work may be blocked

For QA, this is useful for tracking bugs from discovery through verification and closure.

---

# 10. Well-Written vs. Poorly Written Issues

### Poorly Written Issue

```text
Title:
Login broken

Description:
Login doesn't work. Please fix.
```

This issue does not provide enough information.

The developer does not know:

* Which environment is affected
* What credentials or conditions were used
* What happens after clicking Login
* What the expected behavior is
* Whether the issue happens every time
* Which version is affected
* Whether there is an error message

This will likely result in additional questions.

### Well-Written Issue

```text
Title:
[Bug] Login returns a server error with valid credentials

Environment:
- App version: 2.5.1
- Environment: Staging
- Browser: Chrome 140
- OS: Windows 11

Steps to Reproduce:
1. Open the login page.
2. Enter valid credentials.
3. Click "Log In".

Expected Result:
The user should be authenticated and redirected to the dashboard.

Actual Result:
The login request returns HTTP 500 and the user remains on the login page.

Reproduction Rate:
5/5 attempts.

Evidence:
Network request and response attached.
```

This issue is much more actionable because the developer can immediately start investigating the relevant request and environment.

---

# 11. Why Steps to Reproduce Matter

Steps to reproduce provide a clear path for developers to recreate the problem.

Without reproduction steps, a developer may not know:

* Which action triggers the issue
* What state the application needs to be in
* What data is required
* Which workflow is affected
* Where the failure occurs

Good reproduction steps reduce unnecessary investigation time.

They also make it easier for QA to verify whether the issue has been fixed.

For example:

```text
Step 1 → Open application
Step 2 → Navigate to Focus Sessions
Step 3 → Select a task
Step 4 → Start session
Step 5 → Observe application
```

After a fix is delivered, QA can follow the same steps and verify the result.

---

# 12. Writing a Crash Report for Focus Bear

If I discovered a Focus Bear crash, I would avoid writing only:

> "The app crashes."

Instead, I would provide the context necessary to investigate it.

### Example Crash Issue

**Title:**
`[Bug] Focus Bear crashes when starting a Focus Session`

**Description:**
Focus Bear occasionally closes unexpectedly when a user starts a Focus Session from the task screen.

**Steps to Reproduce:**

1. Open Focus Bear.
2. Navigate to the task list.
3. Select an existing task.
4. Start a Focus Session.
5. Observe the application.

**Expected Result:**

The Focus Session should start successfully and the application should remain open.

**Actual Result:**

The application closes unexpectedly.

**Reproduction Rate:**

2 out of 10 attempts.

**Environment:**

* Application version: [version]
* Operating system: [OS/version]
* Device: [device]
* Network: [network condition]

**Evidence:**

* Screen recording
* Screenshot, if applicable
* Crash report/logs, if available
* Approximate time of occurrence

If the crash cannot be reproduced consistently, I would explicitly state the reproduction rate rather than presenting it as a 100% reproducible issue.

---

# 13. What If a Developer Requests More Details?

If a developer asks for more information, I would treat this as an opportunity to improve the issue rather than as criticism.

I may have missed information such as:

* Application version
* Environment
* Device or browser
* Exact reproduction steps
* Test data
* Expected result
* Actual result
* Reproduction frequency
* Error message
* Logs
* Network information
* Screenshot or recording
* Timestamp

I would provide the missing information and update the GitHub issue so that the details are available to the whole team.

If the information is not available, I would clearly state that rather than guessing.

---

# 14. My QA Approach to Writing Issues

Before creating an issue, I would ask myself:

### Is the problem clear?

Can another person understand what is wrong without speaking to me?

### Can it be reproduced?

Have I provided enough information to reproduce it?

### Is the expected behavior clear?

Does the developer know what should happen?

### Is the actual behavior specific?

Have I described exactly what happened?

### Is the environment included?

Could the issue depend on a particular version, browser, device, or environment?

### Is there evidence?

Can I attach screenshots, recordings, logs, network information, or other useful evidence?

### Is the issue actionable?

Can the development team use the information to investigate the problem?

---

# 15. Personal Reflection

A good GitHub issue is more than a description of something that went wrong. It is a communication tool between QA, developers, and the rest of the team.

When reporting a defect, I would focus on providing enough information for another person to reproduce and investigate the problem without unnecessary back-and-forth communication.

I also learned that bug reports, feature requests, and technical tasks have different purposes and should be described accordingly.

Steps to reproduce are especially important because they provide a repeatable path from the initial state to the failure. They also make regression testing easier after the developer provides a fix.

If a developer asks for more details, I would review the issue and identify what information is missing instead of assuming that the developer has not understood the report.

My goal is to make every issue **clear, evidence-based, reproducible when possible, and actionable**.

---

# 16. Personal QA Principle

> **Write issues so that another person can understand, reproduce, investigate, and verify the problem without unnecessary back-and-forth.**
