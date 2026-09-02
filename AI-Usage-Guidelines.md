# AI Usage Guidelines

## 1. AI Tools Commonly Used in QA

AI tools can be useful in software testing and quality assurance. Some common use cases include:

* Generating test case ideas and test scenarios
* Creating test data
* Helping analyse requirements
* Generating or improving test scripts
* Explaining error messages and technical concepts
* Helping with SQL queries and API testing
* Summarising documentation
* Identifying potential edge cases
* Improving bug report wording
* Supporting test automation development

AI should be treated as an assistant rather than a replacement for QA knowledge and judgement.

---

## 2. Benefits of Using AI in a Professional Setting

AI can provide several benefits for QA work:

* **Productivity:** It can reduce the time needed for repetitive tasks.
* **Brainstorming:** It can suggest additional test scenarios and edge cases.
* **Learning:** It can explain unfamiliar technical concepts.
* **Test coverage:** It can help identify scenarios that might otherwise be missed.
* **Documentation:** It can help structure test cases, bug reports, and other QA documentation.
* **Automation support:** It can provide examples or suggestions for automation scripts.

---

## 3. Risks of Using AI

AI also introduces risks that need to be considered:

* AI-generated information can be incorrect or outdated.
* AI may misunderstand requirements or product behaviour.
* Generated test cases may miss important business rules.
* Over-reliance on AI can weaken problem-solving and testing skills.
* Sensitive or confidential information could be exposed if entered into an external AI tool.
* AI-generated code may contain security vulnerabilities or incorrect assumptions.
* AI output can sound convincing even when it is wrong.

Therefore, AI output should always be reviewed critically.

---

## 4. Information That Should Never Be Entered Into AI Tools

I should not enter confidential or sensitive company information into AI tools unless the company has explicitly approved the tool and the specific use case.

Examples include:

* Passwords and authentication credentials
* API keys, access tokens, and secrets
* Private encryption keys
* Personal information of customers or employees
* Confidential company documents
* Non-public source code
* Internal security information
* Private database records
* Unreleased product information
* Private customer data
* Information covered by a confidentiality agreement

When asking AI for help, sensitive information should be removed or replaced with safe, anonymised examples.

---

## 5. Fact-Checking AI-Generated Content

AI-generated information should not automatically be considered correct.

I will validate AI output by:

1. Checking official documentation and trusted sources.
2. Comparing the information with project requirements.
3. Testing technical suggestions in a safe environment.
4. Checking generated code before using it.
5. Verifying important facts independently.
6. Looking for contradictions or assumptions in the response.
7. Asking a developer, QA lead, or other team member when something is unclear.

For security-related or business-critical information, additional verification is especially important.

---

# Reflection

## 6. When Should I Use AI?

I can use AI when it helps me work more efficiently without replacing my own judgement.

Examples include:

* Brainstorming additional test cases
* Improving the structure of documentation
* Explaining technical concepts
* Generating sample test data
* Helping understand an error message
* Suggesting possible edge cases
* Reviewing the clarity of a bug report
* Getting ideas for automation approaches

AI is particularly useful when I already understand the problem and want additional perspectives.

---

## 7. When Should I Rely on My Own Skills?

I should rely on my own testing skills when making important decisions about product quality.

For example:

* Deciding whether a behaviour is actually a bug
* Understanding the user's expected experience
* Determining test priority
* Evaluating business requirements
* Making the final decision about test results
* Assessing the severity and impact of a defect
* Performing exploratory testing
* Validating whether a feature works correctly

AI can suggest possibilities, but the final QA judgement should come from the tester.

---

## 8. Avoiding Over-Reliance on AI

To avoid becoming dependent on AI, I will:

* Try to solve problems independently before asking AI for help.
* Use AI for suggestions rather than blindly copying answers.
* Verify important information myself.
* Practice QA skills without AI regularly.
* Understand any code before using it.
* Compare AI suggestions with requirements and actual product behaviour.
* Treat AI as a second opinion rather than the final authority.

My goal is to use AI to improve my capabilities, not replace them.

---

# Practical Experiment

## 9. Task Improved Using AI

I used an AI tool to help brainstorm additional test scenarios for a hypothetical task creation feature in a productivity application.

The initial test scenarios covered basic task creation, such as:

* Creating a task with valid information
* Creating a task without a title
* Editing a task
* Deleting a task

I asked the AI to suggest additional edge cases.

It suggested scenarios involving:

* Very long task names
* Special characters
* Empty or whitespace-only values
* Different due date combinations
* Unexpected input values
* Repeatedly creating and editing tasks

### Critical Review

The AI-generated suggestions were useful for brainstorming, but they required review.

Not every suggested scenario was necessarily relevant to the actual product requirements. Some scenarios would need to be adjusted based on the application's real functionality and expected behaviour.

This showed me that AI can help expand test coverage, but the QA engineer must decide which scenarios are actually valid and important.

---

# Best Practice

## 10. My AI Best Practice at Focus Bear

**Never enter confidential or sensitive company information into an AI tool, and always verify AI-generated information before using it in my work.**

I will use anonymised examples when asking AI for assistance and will make my own QA judgement based on requirements, product behaviour, and reliable sources.

### Personal Rule

> **Use AI for ideas, not for unquestioned answers.**
