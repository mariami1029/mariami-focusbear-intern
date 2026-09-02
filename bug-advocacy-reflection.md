# Bug Advocacy — Reporting Bugs Effectively

## 1. What Is Bug Advocacy?

Bug advocacy is the practice of communicating software defects clearly and effectively so that the development team understands the problem, its impact, and why it may need attention.

A QA tester should not simply report that something is broken. Good bug advocacy means providing enough evidence and context for the team to make an informed decision.

The goal is not to force developers to agree with QA. The goal is to make the problem visible, understandable, and actionable.

A strong bug report should answer:

* What is the problem?
* How can it be reproduced?
* What should happen?
* What actually happens?
* Who is affected?
* How often does it happen?
* What is the impact?
* What evidence supports the report?

---

## 2. What Makes a Good Bug Report?

A good bug report should be:

* Clear
* Specific
* Reproducible when possible
* Evidence-based
* Neutral and professional
* Focused on user or business impact
* Actionable

Important information can include:

* Clear title
* Description
* Preconditions
* Steps to reproduce
* Expected result
* Actual result
* Environment
* Application version/build
* Reproduction rate
* Severity or impact
* Screenshots or recordings
* Logs or network information when relevant
* Additional context

A good report allows a developer to begin investigating without having to ask many basic questions first.

---

## 3. Poor vs. Effective Bug Report

### Poor Bug Report

```text id="z3j8p1"
Title:
Login broken

Description:
The login doesn't work. Please fix it.
```

This report is too vague.

It does not explain:

* Which version is affected
* Which environment was used
* What steps cause the problem
* Whether the issue happens every time
* What the expected behavior is
* What actually happens
* Whether an error message appears
* How users are affected

### Effective Bug Report

```text id="p8q2mv"
Title:
[Critical] Valid users cannot log in after submitting the login form

Environment:
- Application version: 2.5.1
- Environment: Production
- Browser: Chrome
- OS: Windows 11

Steps to Reproduce:
1. Open the login page.
2. Enter valid credentials.
3. Click "Log In".

Expected Result:
The user should be authenticated and redirected to the dashboard.

Actual Result:
The login request fails with HTTP 500 and the user remains on the login page.

Reproduction Rate:
5/5 attempts.

Impact:
Affected users cannot access their accounts or use the application.

Evidence:
Network request/response and screenshot attached.
```

This report gives the development team a clear starting point.

---

## 4. Making Bugs Easier to Reproduce

A bug is much easier to fix when developers can reproduce it.

To improve reproducibility, I would provide:

### Exact Steps

Steps should be numbered and written in the order they need to be performed.

### Preconditions

For example:

* User must be logged in.
* A specific task must already exist.
* The application must be connected to the internet.

### Test Data

If specific data is required, I would explain what type of data was used without exposing sensitive information.

### Environment

I would include:

* Application version
* Build number when available
* Browser
* Operating system
* Device
* Environment

### Reproduction Rate

For intermittent bugs, I would provide the frequency.

For example:

> Reproduced 3 out of 10 attempts.

### Evidence

Useful evidence can include:

* Screenshots
* Screen recordings
* Console logs
* Network requests
* Crash reports
* Error messages

This information can significantly reduce investigation time.

---

# 5. UI Glitch vs. Critical Login Failure

Not every bug should be communicated in exactly the same way.

The report should reflect the potential impact of the problem.

## UI Glitch

For a minor visual problem, I would focus on:

* Where the problem appears
* Which screen or component is affected
* Which device/browser is affected
* Expected appearance
* Actual appearance
* Screenshot
* Whether functionality is affected

Example:

```text id="4czxv7"
Title:
[UI] Save button is misaligned on the Settings page

Expected Result:
The Save button should be aligned consistently with the other controls.

Actual Result:
The button is shifted approximately 10px to the right on smaller screen sizes.

Environment:
Chrome / Windows 11

Impact:
The issue affects visual consistency but does not prevent users from saving their settings.

Evidence:
Screenshot attached.
```

## Critical Login Failure

For a login failure, I would provide much more emphasis on:

* Number of affected users
* Reproduction rate
* Application version
* Error code
* Network/API evidence
* Business impact
* Whether users are completely blocked

Example:

```text id="j5f0as"
Title:
[Critical] Users cannot log in with valid credentials

Expected Result:
Valid users should successfully log in and access the dashboard.

Actual Result:
The login request returns HTTP 500 and the user cannot access the application.

Reproduction Rate:
5/5 attempts.

Impact:
Users are completely blocked from accessing their accounts.

Evidence:
Network request, response, timestamp, and screenshot attached.
```

The second issue should receive significantly more attention because it blocks a critical user journey.

---

# 6. Bug Severity vs. Bug Priority

Severity and priority describe different things.

### Severity

Severity describes **how serious the consequences of a defect are**.

For example:

* Critical
* High
* Medium
* Low

A critical login failure may prevent users from accessing the entire application.

A minor visual alignment issue may have low severity because the functionality still works.

### Priority

Priority describes **how urgently the team should address the defect**.

For example:

* High priority
* Medium priority
* Low priority

Priority can depend on:

* User impact
* Business impact
* Number of affected users
* Release timing
* Customer commitments
* Available resources
* Risk
* Effort required

---

## 7. Severity and Priority Are Not Always the Same

A high-severity bug is not automatically the highest-priority item in every situation.

For example, a critical defect might affect only a very small number of users in an unsupported environment.

Meanwhile, a medium-severity defect could affect thousands of users every day.

The second issue may receive higher priority because of its broader impact.

However, certain categories such as security vulnerabilities, data loss, or serious production failures may require immediate attention regardless of normal prioritisation calculations.

QA should therefore provide evidence and explain impact rather than assuming that severity alone determines priority.

---

# 8. Bug Advocacy When a Developer Dismisses a Bug

If a developer says:

> "This bug isn't important."

I would avoid responding emotionally or treating the discussion as a disagreement between QA and development.

Instead, I would ask questions and provide evidence.

For example:

* How many users are affected?
* How frequently does the issue occur?
* Does it affect an important workflow?
* Does it cause data loss or incorrect data?
* Does it affect a supported environment?
* Does it create accessibility problems?
* Does it affect customers or business processes?
* Is the issue likely to become more expensive to fix later?

I would then explain the impact clearly.

For example:

> "The visual issue does not break the workflow, but it occurs on the main dashboard for approximately 1,000 weekly users and makes an important action difficult to identify. The attached screenshots show the affected layout."

This is stronger than simply saying:

> "I think this bug should be fixed."

The discussion should focus on **evidence and impact**, not personal opinions.

---

# 9. Evidence in Bug Advocacy

Evidence makes a bug report more convincing and easier to investigate.

### Screenshots

Screenshots can show:

* Incorrect UI
* Error messages
* Unexpected states
* Layout problems

### Screen Recordings

Recordings can demonstrate:

* The exact sequence of actions
* Timing-related issues
* Animations
* Intermittent behavior
* Unexpected navigation

### Logs

Logs can provide technical information such as:

* Exceptions
* Stack traces
* Error messages
* Timestamps
* Component information

### Network Information

Network logs can help identify:

* Failed API requests
* HTTP status codes
* Incorrect responses
* Slow requests
* Timeouts
* Authentication failures

Evidence should be relevant and should not expose sensitive information such as passwords, authentication tokens, API keys, or unnecessary personal data.

---

# 10. Using Impact to Advocate for a Bug

When advocating for a bug, I would explain its impact in practical terms.

Instead of:

> "This is a bad bug."

I would describe:

> "Users cannot complete the task because the Save action fails after submitting the form."

Instead of:

> "This UI is confusing."

I would describe:

> "The primary action is difficult to identify because the button has insufficient visual contrast compared with surrounding elements."

Impact can involve:

* Users being blocked
* Lost or incorrect data
* Security risks
* Accessibility barriers
* Poor usability
* Customer complaints
* Increased support workload
* Business or revenue impact
* Increased technical risk

---

# 11. When a Bug Cannot Be Reproduced

If a developer cannot reproduce the issue, I would not immediately assume that either side is wrong.

I would compare:

* Application version
* Git branch/build
* Environment
* Browser/device
* Operating system
* User/account state
* Test data
* Network conditions
* Exact steps
* Timing
* Reproduction frequency

I would provide any available evidence.

If necessary, I would attempt to reproduce the issue together with the developer.

For intermittent or production-only issues, additional logs or monitoring may be necessary.

The goal is to investigate the conditions under which the bug occurs rather than simply arguing whether it exists.

---

# 12. Bug Advocacy and Professional Communication

Effective bug advocacy should remain professional.

I would:

* Focus on the product, not the person.
* Use neutral language.
* Provide evidence.
* Explain user impact.
* Ask questions when something is unclear.
* Avoid exaggerating the severity.
* Distinguish facts from assumptions.
* Be open to new information.
* Accept when evidence shows that a bug is lower priority.

For example, instead of:

> "You didn't test this properly."

I would say:

> "I was able to reproduce the issue on the staging environment using these steps. Could we compare the environment and build versions to identify why it behaves differently on your side?"

This creates a collaborative discussion.

---

# 13. My QA Approach to Bug Advocacy

My approach would be:

**Observe → Reproduce → Collect Evidence → Explain Impact → Report → Discuss → Follow Up**

First, I would confirm the behavior and collect evidence.

Then I would create a clear bug report with exact reproduction steps, expected and actual results, environment information, and relevant evidence.

I would explain the impact without exaggerating it.

If a developer disagrees with the priority, I would use evidence such as reproduction frequency, affected users, business impact, and technical risk to support the discussion.

If new information changes the situation, I would update my assessment rather than defending my original position just because it was my initial conclusion.

---

# 14. Personal Reflection

A UI glitch and a critical login failure should not be communicated in exactly the same way.

For a UI glitch, I would focus mainly on the affected component, visual inconsistency, environment, and screenshot.

For a critical login failure, I would provide detailed reproduction steps, error information, reproduction rate, affected environment, and clear user impact because the issue can block users from accessing the product.

If a developer dismissed a bug as unimportant, I would not try to persuade them through personal opinion. I would explain the evidence and impact and ask questions that help the team evaluate the issue.

Screenshots, logs, and screen recordings are particularly valuable because they turn a description into observable evidence. They can help developers understand exactly what happened and reduce the time required to reproduce and investigate the defect.

I also learned that effective bug advocacy is not about reporting the largest possible severity. It is about communicating the problem accurately and giving the team enough information to make a good decision.

---

# 15. Personal QA Principle

> **Advocate for the bug with evidence, explain the impact clearly, and collaborate on the solution without blaming people.**
