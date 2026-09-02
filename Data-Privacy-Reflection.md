# Data Privacy Reflection

## 1. Focus Bear Privacy Policy – Key Takeaways

I reviewed the Focus Bear Privacy Policy to understand what types of personal data may be collected, why it is processed, how it is protected, and who may have access to it.

Focus Bear states that personal data should be processed fairly, lawfully, and transparently, and that only data necessary for specific purposes should be collected. The company also aims to comply with GDPR requirements.

Some of the main categories of data described in the Privacy Policy include:

* Identification data, such as email address and phone number.
* Social and lifestyle data, such as habits created in the app.
* Academic and professional data.
* Marketing and communication data.
* Technical data, such as operating system and device type.
* Financial information related to subscriptions.
* Profile data, such as feedback, surveys, and purchase history.
* Aggregate data such as cookies and general statistics.
* Special categories of personal data, including certain health-related information.

Focus Bear states that habit data is double encrypted and that sensitive survey information is handled in an aggregated or anonymised way where applicable.

The Privacy Policy also states that Focus Bear does not store users' card details itself. Payment information is handled by payment providers such as Stripe.

---

# 2. What Data Should Be Considered Confidential?

As a QA intern, I should treat any non-public information related to users, employees, the company, or its systems as potentially confidential.

Examples include:

* User personal information.
* Email addresses and phone numbers.
* User habits and productivity information.
* Health-related or neurodiversity-related information.
* Authentication credentials.
* Passwords.
* API keys and access tokens.
* Internal source code.
* Internal bug reports containing personal information.
* Private logs.
* Database records.
* Internal documentation.
* Unreleased product information.
* Company security information.
* Private conversations or screenshots containing sensitive information.

Even if information does not look highly sensitive by itself, combining several pieces of information can potentially reveal more than intended.

---

# 3. Best Practices for Handling Confidential Data

I will follow these practices when working with confidential information:

### Access

Only access information that is necessary for my assigned work.

### Storage

Store sensitive information only in approved company systems and repositories.

I will avoid keeping confidential information in personal cloud storage, public GitHub repositories, or unsecured local files.

### Sharing

Only share sensitive information with authorised people who need it.

I will verify recipients before sending information.

### Screenshots

Before sharing screenshots in bug reports or documentation, I will check whether they contain:

* Email addresses
* User information
* Passwords
* Tokens
* Personal messages
* Private URLs
* Internal information

If sensitive information is not necessary for demonstrating the issue, I will remove or redact it.

### Passwords and Secrets

I will never include passwords, API keys, access tokens, or other secrets in bug reports, screenshots, commits, or chat messages.

---

# 4. Responding to a Suspected Data Breach

If I suspect that confidential information has been exposed, I should act quickly instead of ignoring it.

My approach would be:

1. Stop further sharing or exposure if I can safely do so.
2. Do not delete evidence that may be needed for investigation.
3. Avoid discussing the incident publicly.
4. Inform the appropriate supervisor or security/privacy contact immediately.
5. Provide the relevant facts, such as what information may have been exposed, where it was exposed, and when I noticed it.
6. Follow Focus Bear's internal incident-response instructions.
7. Do not attempt to investigate beyond my responsibilities unless instructed.

The Focus Bear Privacy Policy specifically includes security breach management and states that potential personal data breaches may need to be evaluated, managed, and reported in accordance with GDPR requirements.

---

# 5. My Daily Data Security Practices

As a QA intern, I can reduce privacy risks by making security part of my normal testing workflow.

Before sharing a bug report or test evidence, I will ask:

* Does this screenshot contain personal information?
* Does this log contain credentials or tokens?
* Am I sharing more data than necessary?
* Is the person receiving this information authorised to see it?
* Can I reproduce the issue using test or anonymised data instead?

I will also keep my development and work environments secure and avoid copying confidential information into external tools unless the use of that tool is explicitly authorised.

---

# 6. Safe Storage, Sharing, and Disposal

## Storing

Sensitive information should be stored only in approved systems with appropriate access controls.

I will avoid storing confidential information in:

* Public repositories
* Personal cloud drives
* Unprotected text files
* Personal messaging applications
* Unauthorised third-party tools

## Sharing

When sharing information, I will:

* Verify the recipient.
* Use approved communication channels.
* Share only the minimum necessary information.
* Check attachments and screenshots before sending them.

## Disposal

When sensitive information is no longer required, I will follow the company's approved retention and deletion procedures.

I will not simply keep unnecessary copies of confidential data.

The Focus Bear Privacy Policy states that personal data is generally retained only for the time necessary to fulfil the purpose for which it was collected, subject to legal and other applicable requirements.

---

# 7. Common Privacy Mistakes

Common mistakes that can cause privacy problems include:

### Accidentally committing secrets to Git

An API key or password can accidentally be included in source code and pushed to a repository.

**Prevention:** Check files before committing and use appropriate secret-management practices.

### Sharing screenshots without checking them

A screenshot can unintentionally expose user information, tokens, emails, or internal data.

**Prevention:** Review and redact screenshots before sharing.

### Using real user data for testing

Real personal information is usually unnecessary for ordinary testing.

**Prevention:** Use test, synthetic, or anonymised data whenever possible.

### Sending information to the wrong person

A simple recipient mistake can expose confidential information.

**Prevention:** Verify recipients before sending.

### Copying confidential information into external tools

External AI or other third-party services may process information outside the company's systems.

**Prevention:** Do not enter confidential company or user information unless the tool and use case are explicitly approved.

---

# 8. My Practical Security Habit

## "Check Before I Share"

One security habit I will adopt is:

> **Before sharing any screenshot, log, bug report, or file, I will check whether it contains information that the recipient does not need to see.**

This is especially important in QA because screenshots, logs, API responses, and bug reports can unintentionally contain personal or confidential information.

If the information is not required to demonstrate the defect, I will remove or anonymise it.

---

# 9. Key Learning

My main learning from reviewing the Privacy Policy is that privacy is not only about passwords and account credentials.

Productivity applications can process information that may be personal or sensitive. For example, Focus Bear's Privacy Policy explains that users can create habits that reveal lifestyle information and that optional surveys may include information related to ADHD or autism.

As a QA tester, this means I need to think about privacy when creating test data, collecting evidence, writing bug reports, and sharing screenshots or logs.

---

# 10. My Commitment

During my internship, I will:

* Use only the data necessary for my work.
* Prefer test or anonymised data.
* Protect credentials and secrets.
* Check screenshots and logs before sharing them.
* Use approved tools and communication channels.
* Avoid putting confidential information into unauthorised external services.
* Report suspected privacy or security incidents promptly.
* Follow company policies and instructions when handling sensitive information.

## Personal Rule

> **If someone does not need to see it, I should not share it.**
