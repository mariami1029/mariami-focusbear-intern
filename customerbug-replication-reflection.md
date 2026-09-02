# Customer Bug Replication – QA Reflection

## 1. What Should QA Do When a Customer-Reported Bug Is Hard to Reproduce?

When a customer reports a bug that I cannot reproduce immediately, I would not simply mark it as "Cannot Reproduce" and stop investigating.

First, I would try to understand exactly what the customer experienced and collect as much information as possible.

I would check:

* What exactly happened?
* What was the customer trying to do?
* What steps were taken before the problem occurred?
* How often does the problem happen?
* When did it first happen?
* Is it still happening?
* What device and operating system were being used?
* What application/browser version was being used?
* Was the customer online, offline, or using an unstable connection?
* Did anything unusual happen immediately before the issue?

I would then try to reproduce the same scenario using the closest possible environment.

If I still cannot reproduce it, I would investigate the available logs, screenshots, recordings, crash reports, and other technical evidence.

A "Cannot Reproduce" result should be treated as a current investigation status, not necessarily as proof that the customer is wrong or that there is no bug.

---

## 2. What Information Should QA Request From Customer Support?

Customer Support can often provide information that QA does not have directly.

I would ask for:

* Customer's device model
* Operating system and version
* Focus Bear version
* Browser and browser version if relevant
* Approximate time and date of the issue
* User actions immediately before the problem
* Exact error message
* Screenshots or screen recordings
* Whether the issue happens every time or only sometimes
* Whether restarting the application changes the behaviour
* Whether the problem occurs on another device
* Network conditions if the issue may be network-related
* Any recent changes, such as an app update or device update

I would also ask Support to preserve the customer's original wording where useful. Sometimes the way a customer describes a problem provides an important clue about what they actually experienced.

---

## 3. How Logs, Screenshots, and Error Messages Help

Different types of evidence provide different information.

### Logs

Logs can show what the application was doing around the time of the problem.

They can reveal:

* Errors
* Exceptions
* Failed requests
* Authentication problems
* Unexpected application states
* Crashes
* Timing information

Logs are especially valuable when the issue happens only occasionally.

### Screenshots

Screenshots can show:

* The exact UI state
* Error messages
* Unexpected layouts
* Missing elements
* Incorrect data
* Device-specific rendering problems

A screenshot may also provide clues that the customer did not mention in their description.

### Screen Recordings

A recording can be especially useful for interaction-related bugs because it shows the sequence of actions leading to the issue.

For example, if a customer says that a button "sometimes doesn't work," a recording could show exactly what happens before and after the click.

### Error Messages

Exact error messages can provide useful search terms and clues about the underlying problem.

I would prefer the exact message rather than relying on a customer's interpretation of what the error means.

---

## 4. When Should QA Recommend Additional Logging?

I would recommend additional logging when:

* The issue is difficult or impossible to reproduce consistently.
* The existing logs do not contain enough information.
* The problem occurs only for a small number of users.
* The issue appears to depend on a particular device or environment.
* A crash occurs without a useful crash message.
* The problem happens only under specific timing or network conditions.
* There is not enough information to determine which part of the application failed.

The additional logging should be targeted rather than simply logging everything.

For example, if a synchronization problem occurs only occasionally, useful logs might include:

* Start and completion of the sync operation
* Request status
* Response status
* Retry attempts
* Relevant timestamps
* Device/app version
* Error information
* State transitions related to synchronization

Sensitive information should not be logged unnecessarily. Logs should avoid exposing passwords, authentication tokens, personal data, or other confidential information.

---

## 5. Handling "Cannot Reproduce" Bugs

I think a good approach to "Cannot Reproduce" bugs is to treat them as investigations rather than simply closing them.

A useful process would be:

**Customer Report → Gather Details → Reproduce → Collect Evidence → Compare Environments → Investigate Logs → Ask for More Data → Re-test**

If the issue still cannot be reproduced, the team can document:

* What environments were tested
* What steps were attempted
* What evidence was reviewed
* How frequently the customer experiences the issue
* What information is still missing

This creates a useful investigation history.

If new evidence becomes available later, the bug can be investigated again without starting completely from the beginning.

---

# Reflection

## 6. If a Customer Reports a Crash but I Cannot Reproduce It

If a customer reports a crash and I cannot reproduce it, my first step would be to avoid assuming that the crash is not real.

I would collect the exact environment and circumstances of the crash.

I would want to know:

1. What device was being used?
2. What OS version was installed?
3. What application version was being used?
4. What was the customer doing immediately before the crash?
5. Does it happen every time or occasionally?
6. When did it happen?
7. Is there a screenshot or recording?
8. Are crash reports or logs available?
9. Does the issue affect other users?
10. Does changing the environment make a difference?

I would then try to reproduce the scenario using the same or a similar device and application version.

If the crash still cannot be reproduced, I would compare the customer's environment with environments where the application works correctly.

I would also look for patterns in other reports. If several customers report similar crashes, that would increase my confidence that there is an underlying issue even if I cannot reproduce it locally.

---

## 7. When Should I Ask Developers to Add More Logging?

I would involve developers when the information currently available is not enough to understand what is happening.

For example, if a crash occurs randomly but there is no useful error information, I might ask for additional logging around the part of the application where the crash appears to happen.

I would be specific about what information would help rather than simply asking developers to "add more logs."

Useful information could include:

* Timestamps
* Application state before the failure
* Function or operation being executed
* API request/response status
* Exception details
* Retry attempts
* Device and OS information
* Relevant state transitions
* Whether a particular operation succeeded or failed

I would also consider the cost and privacy implications of additional logging. More logs are not automatically better if they create unnecessary noise or expose sensitive data.

---

## 8. Common Patterns in Bugs That Affect Only Some Users

Some bugs may depend on differences between users or environments.

Common patterns include:

### Device-specific behaviour

A problem may only happen on a particular phone model or hardware configuration.

### OS version

A feature may behave differently on an older or newer operating system.

### Application version

A bug may only exist in a specific release.

### Account or data state

Two users may follow the same steps but have different data, settings, permissions, or account states.

### Network conditions

Slow, unstable, or interrupted connections can cause intermittent failures.

### Timing and race conditions

Some bugs occur only when actions happen very quickly or simultaneously.

### Permissions

A feature may fail when a required permission has been denied or changed.

### Resource limitations

Low memory, limited storage, high CPU usage, or battery-saving modes can sometimes affect application behaviour.

### Feature flags or configuration

Different users may have different configurations or feature flags enabled.

Recognizing these patterns can help QA narrow down the conditions under which the problem occurs.

---

## 9. My Approach to Customer-Reported Bugs

Customer-reported bugs are especially valuable because they represent real-world usage.

A customer may use the application in a way that was not included in the original test scenarios. Their report can therefore reveal an environment, workflow, or combination of conditions that QA did not consider.

I would approach these reports with curiosity rather than immediately trying to prove or disprove them.

My investigation would be based on evidence:

**Observe → Question → Reproduce → Collect Evidence → Compare → Investigate → Report**

If I cannot reproduce the problem, I would document what I tried and identify what additional information would help.

## Key Takeaway

A "Cannot Reproduce" bug is not necessarily a "Not a Bug" situation.

Sometimes the missing piece is a specific device, OS version, account state, timing condition, network situation, or piece of diagnostic information.

Good QA means continuing the investigation, asking useful questions, collecting evidence, and working with developers and customer support to reduce uncertainty.

My QA principle is:

**"If I can't reproduce the bug, I investigate the conditions — I don't dismiss the report."**
