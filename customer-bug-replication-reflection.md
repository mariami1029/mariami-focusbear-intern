# Customer Bug Replication & Hard-to-Reproduce Bugs — QA Reflection

## 1. Understanding Intermittent Bugs

An intermittent bug is an issue that does not happen every time the same steps are performed. It may occur only under specific conditions, making it difficult to reproduce consistently.

For example, a feature may work correctly nine times but fail on the tenth attempt.

Intermittent bugs can be especially difficult for QA and developers because the same environment and steps may produce different results.

---

## 2. Common Causes of Intermittent Bugs

There are many possible causes of bugs that occur only occasionally.

### Timing and Race Conditions

Two processes may execute in an unexpected order.

For example, a user may click a button before an API response has finished loading.

### Network Instability

Slow, interrupted, or unstable network connections can cause:

* Timeouts
* Failed requests
* Incomplete responses
* Duplicate requests
* Unexpected application states

### Resource Limitations

Problems may appear only when the device has:

* Low available memory
* High CPU usage
* Low storage
* Many applications running in the background

### Concurrency

Multiple users, requests, or processes may access the same resource at the same time and create unexpected behavior.

### Caching and Session State

Old cached data, expired sessions, cookies, or inconsistent local storage can cause a problem for some users but not others.

### Device or Browser Differences

A bug may occur only on:

* A specific operating system
* A particular browser version
* A specific device model
* An older device
* A particular screen size or configuration

### Data-Specific Conditions

The problem may depend on particular user data, account settings, task history, or application state.

### Backend or External Services

Temporary problems with APIs, databases, authentication services, or third-party integrations may cause intermittent failures.

---

## 3. Tools for Investigating Hard-to-Reproduce Bugs

QA can use several types of evidence to investigate intermittent issues.

### Browser Developer Tools

For web applications, browser DevTools can help collect:

* Console errors
* Network requests
* HTTP status codes
* Request and response data
* Request timing
* JavaScript errors
* Performance information
* Storage and cookie information

The Network tab is particularly useful when the problem may be related to API requests.

### Application Logs

Application logs can show what happened internally around the time of an error.

Useful information may include:

* Timestamp
* Error message
* Exception type
* Stack trace
* Request or transaction identifier
* User/session identifier when appropriate and permitted
* Service/component involved

Sensitive information such as passwords, authentication tokens, or personal data should not be unnecessarily included in logs or bug reports.

### Crash Reports

For mobile or desktop applications, crash reporting systems can provide:

* Crash timestamp
* Application version
* Operating system
* Device model
* Stack trace
* Error type
* Frequency of the crash
* Number of affected users

Crash information can be especially valuable when QA cannot reproduce the issue locally.

### Screenshots and Screen Recordings

Visual evidence can help show:

* The exact error message
* Unexpected UI behavior
* Application state before the failure
* What the user saw when the problem occurred

A screen recording can be especially useful for intermittent UI issues.

---

## 4. Strategies for Making Flaky Bugs More Reproducible

When a bug occurs only occasionally, QA should try to identify the conditions that trigger it.

### Repeat the Same Steps

Run the same scenario multiple times and record:

* Number of attempts
* Successful attempts
* Failed attempts
* Exact steps
* Time between actions

For example:

```text
Attempt 1: Passed
Attempt 2: Passed
Attempt 3: Failed
Attempt 4: Passed
Attempt 5: Failed
```

This helps establish the frequency of the problem.

### Change One Variable at a Time

Possible variables include:

* Browser
* Device
* Operating system
* Network condition
* User account
* Application version
* Amount of data
* Time spent in the application

Changing one variable at a time makes it easier to identify a pattern.

### Test Under Different Conditions

For example:

* Normal network
* Slow network
* Unstable network
* Offline/online transitions
* Low-memory conditions
* Older devices
* Different browsers

### Identify a Trigger

Try to determine whether the issue happens:

* After a certain amount of time
* After repeated actions
* After restarting the application
* After switching between screens
* After losing network connectivity
* After a particular API request
* With specific data

Finding a trigger can turn an intermittent bug into a reproducible bug.

---

## 5. Customer-Reported Bugs

Customer reports are valuable because customers use the product in environments that QA may not have access to.

However, customer reports may initially contain limited technical information.

For example:

> "The app crashed while I was using it."

This is useful information, but it is not enough to reproduce the problem reliably.

QA should work with customer support to collect additional details.

### Information QA Should Request

Depending on the issue, useful information may include:

* What exactly happened?
* What was the customer trying to do?
* What steps happened immediately before the issue?
* Did the issue happen once or multiple times?
* When did it happen?
* What date and approximate time?
* Application version
* Device model
* Operating system and version
* Browser and version for web issues
* Network conditions
* Screenshot or screen recording
* Exact error message
* Whether restarting the application helped
* Whether the issue still occurs
* Whether other users are affected
* Relevant account or environment information, when appropriate and permitted

QA should avoid requesting unnecessary personal information.

---

## 6. Investigating a Customer-Reported Crash

If a customer reports a crash that QA cannot reproduce, I would follow a structured investigation.

### Step 1: Collect Information

I would ask customer support for the exact details of the report.

### Step 2: Identify the Environment

I would determine:

* Application version
* Device
* Operating system
* Browser, if applicable
* Network conditions
* Account state
* Relevant application configuration

### Step 3: Check Crash Data

I would look for available crash reports, logs, stack traces, or error messages around the reported time.

### Step 4: Attempt Reproduction

I would try to reproduce the issue using the same or similar:

* Device
* OS version
* Application version
* User state
* Network conditions
* Sequence of actions

### Step 5: Look for Patterns

I would compare the customer report with:

* Other crash reports
* Similar bug reports
* Device/OS combinations
* Application versions
* Recent releases or changes

### Step 6: Document the Findings

If the crash still cannot be reproduced, I would document what was tested rather than simply saying "Cannot Reproduce."

For example:

```text
Attempted reproduction:
- App version: 2.5.1
- OS: Windows 11
- Browser: Chrome
- Network: Normal
- Reproduction attempts: 10
- Result: Crash not reproduced

Customer environment:
- App version: 2.5.1
- Device/OS: [customer-reported information]
- Reported time: [timestamp]
```

This gives developers useful information for further investigation.

---

## 7. Using Logs, Screenshots, and Error Messages

Different types of evidence provide different information.

| Evidence                | What it can help identify           |
| ----------------------- | ----------------------------------- |
| Screenshot              | What the user saw                   |
| Screen recording        | Sequence of actions and UI behavior |
| Error message           | Immediate failure information       |
| Console log             | Client-side errors                  |
| Network request         | API/request failures                |
| Application log         | Internal application behavior       |
| Crash report            | Crash location and stack trace      |
| Timestamp               | Correlation with logs and events    |
| Environment information | Device/version-specific patterns    |

Combining multiple sources of evidence is often more useful than relying on only one.

---

## 8. When QA Should Recommend More Logging

QA should consider requesting additional logging when:

* The issue cannot be reproduced reliably.
* Existing logs do not show what happened.
* The issue occurs only in production.
* Only some users are affected.
* The problem appears to depend on timing or state.
* The issue involves multiple services or APIs.
* A crash occurs without enough diagnostic information.
* There is not enough evidence to identify the failing component.

The goal is not to log everything.

Additional logging should be **targeted and useful**.

### Examples of Useful Logging

Depending on the issue, useful information may include:

* Timestamp
* Application version
* Component or service name
* Request/transaction ID
* Operation being performed
* API endpoint and HTTP status
* Response/error type
* Relevant state information
* Exception and stack trace
* Performance/timing information

Sensitive information should be protected.

Logs should not expose:

* Passwords
* Authentication tokens
* API keys
* Payment information
* Unnecessary personal data
* Other confidential information

---

## 9. Handling "Cannot Reproduce" Bugs

"Cannot Reproduce" should not automatically mean that the issue is invalid.

It means that the issue could not be reproduced under the conditions currently tested.

When a developer marks a bug as "Not Reproducible," my next step would be to compare our testing conditions.

I would check:

1. Application version
2. Git branch/build
3. Environment
4. Device and OS
5. Browser
6. User/account state
7. Test data
8. Network conditions
9. Exact reproduction steps
10. Timing and frequency

If necessary, I would provide additional evidence such as:

* Screenshots
* Screen recordings
* Console logs
* Network logs
* Crash reports
* Timestamps
* Detailed reproduction attempts

If the issue still cannot be reproduced, I would collaborate with the developer instead of treating it as a disagreement.

For example, we could try reproducing the issue together using the customer's environment details.

---

## 10. Common Patterns: Why Only Some Users Are Affected

When only some users experience a bug, I would look for differences between affected and unaffected users.

Common patterns include:

* Different application versions
* Different operating systems
* Different devices
* Different browsers
* Different account permissions
* Different user data
* Different geographic locations
* Different network conditions
* Different configuration settings
* Different feature flags
* Different usage patterns
* Different amounts of stored data
* Different third-party integrations

A useful approach is to compare:

```text
Affected Users
      ↓
What do they have in common?
      ↓
Unaffected Users
      ↓
What is different?
      ↓
Possible triggering condition
```

This comparison can help narrow down the root cause.

---

## 11. How I Would Report an Intermittent Bug

If a bug only happens occasionally, I would clearly state its frequency instead of claiming that it happens every time.

For example:

```text
Reproduction Rate: 3/10 attempts

Steps:
1. Open the application.
2. Start a Focus Session.
3. Navigate to another section.
4. Return to the Focus Session.
5. Observe the session state.

Actual Result:
In 3 out of 10 attempts, the Focus Session stops unexpectedly.

Expected Result:
The Focus Session should continue running after navigating back to it.

Environment:
- Application version: [version]
- OS: [OS]
- Device/Browser: [device or browser]
- Network: [network condition]

Additional Evidence:
- Screenshot/screen recording attached
- Console/network logs attached if relevant
```

This gives developers a much clearer understanding of the problem.

---

## 12. My QA Approach

When investigating a hard-to-reproduce or customer-reported bug, I would avoid making assumptions.

My process would be:

**Collect → Reproduce → Compare → Investigate → Document → Collaborate**

I would first collect as much relevant information as possible, then attempt reproduction under the same conditions.

If reproduction is unsuccessful, I would compare affected and unaffected environments and look for patterns.

I would use screenshots, recordings, logs, network information, and crash reports when appropriate.

If the available evidence is insufficient, I would recommend targeted additional logging rather than asking developers to log everything.

For "Cannot Reproduce" issues, I would treat the status as a current testing result, not as proof that the customer or QA report is incorrect.

---

## 13. Personal QA Principle

> **When a bug is difficult to reproduce, don't guess — collect evidence, identify patterns, and investigate the conditions.**

A hard-to-reproduce bug can still have a significant impact on users. Good QA investigation should make the problem easier for the entire team to understand, reproduce, and ultimately fix.
