# Understanding How to Do Manual QA

## Introduction

Manual QA is the process of evaluating software through human interaction, observation, reasoning, and investigation without relying on automated test execution as the primary testing method.

Manual testing is not simply following a checklist and marking test cases as passed or failed. A good manual tester needs to understand the product, identify risks, ask questions, investigate unexpected behaviour, and adapt the testing approach to the situation.

One important approach to manual QA is **Context-Driven Testing**, associated with the work of James Bach, Michael Bolton, and other context-driven testing practitioners.

The central idea is that testing should be adapted to the specific context of the product instead of blindly following a universal testing process.

---

## 1. What Is Manual QA Testing?

Manual QA involves a human tester interacting with software to determine whether it behaves as expected and whether there are risks or problems that could affect users.

A manual tester may:

* Analyse requirements.
* Design test scenarios.
* Create and execute test cases.
* Perform exploratory testing.
* Test positive and negative scenarios.
* Investigate edge cases.
* Reproduce defects.
* Check usability and accessibility.
* Analyse unexpected behaviour.
* Report and track bugs.
* Perform regression testing.
* Communicate risks and findings to the team.

Manual QA relies heavily on human judgement.

For example, an automated test can verify that a button is clickable. A manual tester can additionally ask:

> Is the button easy to find?

> Is its purpose clear?

> Does the workflow make sense?

> What happens if the user does something unexpected?

These questions require context and critical thinking.

---

## 2. Manual QA vs. Automated Testing

Manual and automated testing have different strengths.

| Aspect               | Manual QA                        | Automated QA                            |
| -------------------- | -------------------------------- | --------------------------------------- |
| Execution            | Human                            | Script/tool                             |
| Repetitive checks    | Less efficient                   | Highly efficient                        |
| Exploratory testing  | Excellent                        | Limited                                 |
| Human judgement      | Strong                           | Limited                                 |
| Usability evaluation | Strong                           | Limited                                 |
| Regression testing   | Possible                         | Excellent                               |
| Unexpected behaviour | Can investigate dynamically      | Usually limited to programmed scenarios |
| Adaptability         | High                             | Requires script changes                 |
| Initial setup        | Usually lower                    | Can require significant development     |
| Maintenance          | Test documentation and execution | Test code and infrastructure            |

Automation is valuable for predictable and repetitive checks, while manual QA is especially valuable where reasoning, exploration, observation, and adaptability are important.

A strong testing strategy uses both approaches appropriately.

---

# 3. Context-Driven Testing

Context-Driven Testing is an approach that argues that testing practices should be adapted to the specific circumstances of a project.

There is no single testing process that is equally appropriate for every product.

The context can include:

* Type of product.
* Users.
* Business goals.
* Product risks.
* Development methodology.
* Team structure.
* Available time.
* Available tools.
* Regulatory requirements.
* Technical architecture.
* Release frequency.
* Consequences of failure.

For example, testing a banking application and testing a productivity application should not necessarily follow exactly the same testing strategy.

A banking application may place extremely high emphasis on security, financial correctness, and data integrity.

A productivity application may place more emphasis on usability, workflows, performance, accessibility, and user experience.

The appropriate testing approach depends on what matters most in that particular context.

---

# 4. The Seven Principles of Context-Driven Testing

The Context-Driven School of Software Testing is commonly described through seven principles.

## Principle 1: The Value of Any Practice Depends on Its Context

A testing technique is not automatically good or bad.

Its value depends on where and how it is used.

For example, a detailed regression suite can be extremely valuable for a stable critical application, while spending large amounts of time maintaining low-value tests may be inefficient for rapidly changing experimental functionality.

---

## Principle 2: There Are Good Practices in Context, but There Are No Best Practices

A technique that works very well for one team may not be the best choice for another.

There is no universal "best testing process" that works perfectly everywhere.

Instead, testers should ask:

> "What approach makes sense for this product, team, risk, and situation?"

---

## Principle 3: People Working Together Are the Most Important Part of Any Project's Context

Testing is performed by people, and communication strongly affects quality.

Developers, testers, product managers, designers, and users can have different knowledge and perspectives.

Effective collaboration helps the team understand:

* What the product is supposed to do.
* What risks exist.
* What users need.
* Which problems are most important.

Tools and processes are useful, but they cannot completely replace human communication and judgement.

---

## Principle 4: Projects Unfold Over Time in Ways That Are Often Unpredictable

Requirements, priorities, technology, risks, and user expectations can change.

Therefore, a testing strategy should be capable of changing as the project changes.

A test strategy created at the beginning of a project should not necessarily remain unchanged throughout its entire lifecycle.

---

## Principle 5: The Product Is a Solution

Testing should consider whether the product actually solves the problem it was created to solve.

It is not enough to verify that the software follows technical requirements.

A feature can technically work while still failing to provide a useful experience.

For example, a Focus Bear feature could function correctly according to its implementation but still be confusing or inconvenient for users.

---

## Principle 6: Good Software Testing Is a Challenging and Intellectual Process

Testing requires reasoning.

A tester should:

* Analyse information.
* Identify patterns.
* Ask questions.
* Develop hypotheses.
* Investigate risks.
* Make decisions based on evidence.

Testing is therefore more than executing instructions.

---

## Principle 7: Only Through Judgement and Skill Exercised Cooperatively Throughout the Project Do We Do the Right Things at the Right Times to Effectively Test Our Products

This principle emphasizes the importance of judgement, skill, timing, and collaboration.

Testers must decide:

* What to test.
* How deeply to test it.
* When to test it.
* Which risks deserve attention.
* When testing is sufficient.
* When additional investigation is necessary.

The goal is not to perform testing mechanically but to make effective decisions based on the current context.

---

# 5. Why Context Matters in Testing

Context determines what "good testing" means.

Imagine two applications.

### Application A: Banking Software

Important risks may include:

* Incorrect financial calculations.
* Security vulnerabilities.
* Unauthorized access.
* Data corruption.
* Transaction failures.

Testing would need strong emphasis on security, data integrity, accuracy, and reliability.

### Application B: Productivity Application

For an application such as Focus Bear, important areas may include:

* Usability.
* Task and habit workflows.
* Accessibility.
* Notifications.
* Application state.
* Performance.
* Cross-device behaviour.
* User experience.

The same testing strategy should not automatically be applied to both products.

This is why a tester needs to understand the product before deciding how to test it.

---

# 6. How Testing Focus Bear May Differ From Testing Another App

Focus Bear is a productivity application designed around user routines, focus, habits, and tasks.

Therefore, I would pay particular attention to areas such as:

* Task creation and management.
* Habit workflows.
* Focus sessions.
* Scheduling.
* Application state and persistence.
* Notifications and reminders.
* Usability.
* Accessibility.
* Performance.
* Interactions between features.
* Behaviour after application restart.
* Different user workflows.

For another application, the priority could be completely different.

For example:

* An e-commerce application → checkout, payments, inventory.
* A banking application → authentication, transactions, security.
* A healthcare application → privacy, data accuracy, safety.
* A game → gameplay, performance, graphics, device compatibility.

The context determines where testing effort should be concentrated.

---

# 7. Exploratory Testing vs. Scripted Testing

Manual QA can include both exploratory and scripted testing.

## Exploratory Testing

Exploratory testing combines learning, test design, and execution.

The tester does not rely exclusively on predefined test cases.

A tester can:

* Explore new functionality.
* Follow unexpected behaviour.
* Try unusual inputs.
* Investigate suspicious results.
* Change the testing strategy based on discoveries.

Exploratory testing is especially useful when requirements are incomplete, the feature is new, or the risks are not fully understood.

## Scripted Testing

Scripted testing follows predefined instructions and expected results.

It is useful when:

* Requirements are clear.
* Functionality is stable.
* Repeatability is important.
* Regression testing is required.
* Multiple testers need consistent procedures.

Neither approach is universally superior.

The correct choice depends on context.

---

# 8. How Manual Testing Can Be Structured and Adaptable

Manual testing does not have to be completely unstructured.

A tester can create structure while maintaining flexibility.

For example:

### Structured Part

Define:

* Testing objective.
* Scope.
* Environment.
* Important requirements.
* High-risk areas.
* Initial test scenarios.
* Time limit.

### Adaptive Part

During testing:

* Follow unexpected behaviour.
* Add new test ideas.
* Change priorities.
* Investigate suspicious results.
* Ask for clarification.
* Explore related functionality.

A useful model is:

**Plan → Explore → Observe → Adapt → Investigate → Document**

This provides enough structure to maintain direction without preventing useful discoveries.

---

# 9. Testing a New Focus Bear Feature Without a Predefined Script

If I received a completely new Focus Bear feature without predefined test cases, I would not immediately start clicking randomly.

I would first build enough context to understand what I am testing.

### Step 1: Understand the Purpose

I would ask:

> What problem is this feature supposed to solve?

### Step 2: Identify the Main User

I would consider:

> Who will use this feature?

### Step 3: Identify the Main Workflow

I would determine:

> What should a normal successful interaction look like?

### Step 4: Identify Risks

I would ask:

* What could go wrong?
* Could user data be lost?
* Could the feature affect existing functionality?
* Does it interact with other features?
* Is it related to critical user workflows?

### Step 5: Test the Happy Path

I would first verify the basic intended workflow.

### Step 6: Explore Variations

I would then investigate:

* Empty input.
* Invalid input.
* Boundary values.
* Repeated actions.
* Unexpected navigation.
* Interrupted workflows.
* Application restart.
* Network problems where relevant.
* Different environments.

### Step 7: Investigate Unexpected Behaviour

If I discover something unusual, I would stop and investigate it instead of ignoring it simply because it was not part of my original plan.

### Step 8: Document Findings

I would record:

* What I tested.
* What I discovered.
* What remains uncertain.
* Bugs found.
* Evidence collected.
* Areas requiring further testing.

This approach allows me to test effectively even without a predefined script.

---

# 10. Deciding What to Test Without Detailed Requirements

When detailed requirements are unavailable, I would not assume that testing is impossible.

Instead, I would gather context from available sources.

These could include:

* Product documentation.
* Existing features.
* UI design.
* Existing test cases.
* Related GitHub Issues.
* Previous bugs.
* Product managers.
* Developers.
* Other testers.
* User expectations.
* Existing application behaviour.

I would then create a set of assumptions and questions.

For example:

| Question                                    | Why It Matters                 |
| ------------------------------------------- | ------------------------------ |
| What is the feature supposed to accomplish? | Defines the primary objective  |
| Who uses it?                                | Helps identify user risks      |
| What data does it affect?                   | Helps identify integrity risks |
| What happens when it fails?                 | Helps assess impact            |
| Which features interact with it?            | Helps define regression scope  |
| What are the important edge cases?          | Helps guide exploration        |
| What behaviour is considered acceptable?    | Defines expected results       |

If something important remains unclear, I would raise the question instead of silently making a risky assumption.

---

# 11. Testing as an Investigation

A manual tester should approach unexpected behaviour as evidence rather than immediately dismissing it.

A useful investigative cycle is:

**Observe → Question → Hypothesize → Test → Gather Evidence → Analyse → Report**

For example:

### Observation

A task appears to have different behaviour after restarting the application.

### Question

> Is the task state being persisted correctly?

### Hypothesis

> The application may not be saving the state correctly before restart.

### Investigation

Repeat the workflow under controlled conditions and compare the results.

### Evidence

Collect:

* Screenshots.
* Screen recordings.
* Logs.
* Network information.
* Reproduction rate.
* Relevant test data.

### Conclusion

Determine whether the behaviour is reproducible and whether it represents a defect or an intended behaviour.

This investigative mindset is an important part of effective manual QA.

---

# 12. Skills of a Strong Manual Tester

A good manual tester needs more than knowledge of test case syntax.

Important skills include:

### Curiosity

Wanting to understand why something behaves the way it does.

### Critical Thinking

Questioning assumptions rather than accepting everything at face value.

### Observation

Noticing small changes, inconsistencies, and unexpected behaviour.

### Communication

Clearly explaining problems and their impact to developers and stakeholders.

### Risk Assessment

Knowing which areas deserve the most testing attention.

### Adaptability

Changing the testing strategy when new information appears.

### Technical Knowledge

Understanding enough about applications, APIs, databases, logs, browsers, operating systems, and other technical areas to investigate problems effectively.

### Persistence

Continuing an investigation when a problem is difficult to reproduce.

### User Empathy

Thinking about how real users might experience the software.

### Judgement

Knowing what to test, how deeply to test it, and when enough evidence has been collected.

---

# 13. Reflection

## Why is context important in testing, and how might testing Focus Bear differ from testing another app?

Context determines which risks matter most.

For Focus Bear, I would pay particular attention to productivity workflows, user experience, accessibility, task and habit management, application state, notifications, and interactions between features.

For a banking application, security and financial accuracy would probably dominate the testing strategy.

For an e-commerce application, checkout, payments, inventory, and order processing might be the highest-risk areas.

Therefore, I should understand the product and its users before deciding what "good testing" looks like.

---

## How can manual testing be both structured and adaptable at the same time?

I can begin with structure by defining the testing goal, scope, environment, risks, and initial scenarios.

However, I should remain flexible during execution.

If I discover unexpected behaviour, I can change direction and investigate it. If new information changes the risk assessment, I can reprioritize my testing.

This gives me a balance between consistency and exploration.

---

## How would I approach testing a new feature in Focus Bear without a predefined test script?

I would first understand the purpose of the feature and identify its expected primary workflow.

Then I would identify risks and test the happy path before exploring negative cases, boundaries, unusual inputs, interruptions, persistence, and interactions with existing functionality.

I would document my observations and create formal test cases for important stable scenarios discovered during exploration.

---

## How do I decide what to test when no detailed requirements are provided?

I would gather context from documentation, existing behaviour, related functionality, previous issues, developers, product stakeholders, and other available sources.

Then I would identify assumptions and risks.

If an important requirement remains unclear, I would ask for clarification rather than inventing expected behaviour.

Where clarification is not immediately available, I can test reasonable scenarios while clearly documenting the assumptions behind my testing.

---

# Conclusion

Manual QA is not simply the manual execution of predefined test cases.

It is a combination of:

**Observation + Critical Thinking + Investigation + Risk Assessment + Communication + Adaptability**

Context-Driven Testing reinforces the idea that testing practices should be selected according to the specific product, people, risks, resources, and circumstances.

Exploratory testing provides flexibility and discovery, while scripted and regression testing provide repeatability and confidence in known functionality.

The strongest manual tester knows when to follow a plan, when to investigate something unexpected, when to ask questions, and when to change the testing strategy.

My QA principle is:

> **Understand the context first, test according to risk, question what seems unclear, and adapt when the evidence tells me to change direction.**
