# Testing as an Investigative Process

## 1. Testing as Investigation

The more I learn about QA, the more I realize that testing is not simply about following a list of steps and checking whether each expected result appears.

A good tester has to be curious.

When something behaves differently from what I expected, I should not immediately move on. I should ask myself why it happened, whether I can reproduce it, whether it happens under different conditions, and what else might be affected.

This makes testing feel more like an investigation. I start with an observation, form questions and hypotheses, collect evidence, and then decide what to investigate next.

I think this mindset is especially important when requirements are incomplete. If I only test what is explicitly written, I can easily miss problems that a real user might encounter.

---

## 2. How Exploratory Testing Can Find Bugs Scripted Tests Miss

Scripted testing is useful because it gives us repeatable and predictable coverage. However, it also has limitations.

If I always follow exactly the same steps, I may only discover problems that those steps were designed to detect.

Exploratory testing allows me to change my approach based on what I observe.

For example, if I am testing a task creation feature, I would not only create one normal task and check that it appears in the list.

I could also ask:

* What happens if I create several tasks very quickly?
* What happens if I leave some fields empty?
* What happens if I enter an unusually long task name?
* What happens if I change the task while another operation is still processing?
* What happens if the network connection is interrupted?
* What happens after restarting the application?
* What happens if I repeatedly perform the same action?

These questions can reveal issues that a predefined happy-path test might never encounter.

---

## 3. Questions I Would Ask When Testing a New Focus Bear Feature

When testing a new feature for the first time, I would start by understanding its purpose.

I would ask:

### Understanding the feature

* What problem is this feature supposed to solve?
* Who is expected to use it?
* What is the most important user workflow?
* What should happen when everything goes normally?

### Looking for boundaries

* What happens with empty input?
* What happens with the minimum and maximum values?
* What happens with unusually long input?
* What happens with invalid data?
* What happens when the user changes something after saving?

### Thinking about states

* What happens before the feature is used?
* What happens while an operation is processing?
* What happens after success?
* What happens after failure?
* What happens if the user leaves and returns later?

### Thinking about interruptions

* What happens if the network connection disappears?
* What happens if the application is restarted?
* What happens if the user clicks multiple times?
* What happens if another action occurs at the same time?

### Thinking like a user

* Is the feature understandable without additional explanation?
* Does the interface behave as I would expect?
* Could a user misunderstand what a button or message means?
* Does the feature create unnecessary steps or confusion?

These questions help me explore beyond the basic acceptance criteria.

---

## 4. How Uncertainty and Curiosity Can Make Me a Better Tester

I think uncertainty can actually be useful in testing.

If I am completely convinced that I already know how a feature works, I might stop investigating too early.

Instead, when I notice something unexpected, I can think:

**"I wonder what would happen if..."**

That question can lead to another test, which can lead to another observation.

Curiosity also helps when I do not immediately understand a behaviour. Instead of assuming that something is either a bug or expected behaviour, I can investigate the evidence first.

At the same time, curiosity needs structure. Randomly clicking around without a goal is not necessarily effective testing.

I would combine curiosity with a clear investigation process:

**Observe → Question → Hypothesize → Test → Collect Evidence → Analyse → Follow the Lead**

---

## 5. Techniques for Investigating Software Behaviour

There are several techniques I can use when investigating a feature.

### Boundary Value Analysis

I can test values around boundaries instead of only testing normal values.

For example, if a field accepts values from 1 to 100, I would consider values such as:

* 0
* 1
* 2
* 99
* 100
* 101

### Equivalence Partitioning

I can divide possible inputs into meaningful groups and test representative values from each group.

### Error Guessing

Based on experience, I can think about common ways the feature could fail.

For example:

* Empty input
* Duplicate actions
* Invalid characters
* Unexpected navigation
* Very fast interaction
* Network interruption

### State-Based Testing

I can investigate how the application behaves when moving between different states.

For example:

**Not Started → In Progress → Completed**

I would test whether each transition works correctly and whether unexpected transitions are handled safely.

### Change One Variable

When investigating a complicated issue, I can change one condition at a time.

For example, if a bug only occurs sometimes, I could compare:

* Same device + different browser
* Same browser + different device
* Same data + different account
* Same environment + different network

This makes it easier to identify which condition may be responsible.

### Follow the Data

If something looks wrong in the UI, I can follow the data through the application.

For example:

**User Action → API Request → API Response → Frontend Processing → UI**

This can help determine where the unexpected behaviour begins.

---

## 6. How Questioning Skills Help Find Hidden Issues

Questioning is one of the most important skills I want to improve as a tester.

A simple question like:

**"What happens if the user does this twice?"**

can reveal a completely different class of bugs.

Other useful questions include:

* What happens if the user does this very quickly?
* What happens if the operation fails halfway through?
* What happens if the user loses their connection?
* What happens if the user comes back later?
* What happens if the data is different?
* What happens on another device?
* What happens after an application restart?
* What happens if two actions happen almost simultaneously?
* Is this behaviour actually intended?
* What would happen to a user who does not understand this screen?

These questions help me move from simply checking functionality to understanding behaviour.

---

## 7. Testing When Requirements Are Unclear

When requirements are unclear, I would avoid immediately making assumptions about everything.

First, I would identify what is clear and what is uncertain.

For example:

**Known:** The user can create a task.

**Unclear:** What should happen if the user enters an extremely long task name?

Instead of silently deciding what the expected result should be, I would investigate the existing behaviour, look for related requirements or patterns elsewhere in the product, and ask the appropriate team member when the uncertainty affects an important behaviour.

I think this is especially important because unclear requirements can create two opposite risks:

* Reporting expected behaviour as a bug.
* Accepting incorrect behaviour because I assumed it was intended.

When there is no clear requirement, I would document my assumption and communicate the uncertainty rather than hiding it.

---

# Reflection

## 8. What Would I Do If a Bug Is Difficult to Reproduce?

If a bug is difficult to reproduce, I would try to turn the uncertainty into smaller questions.

First, I would determine:

* How often does it happen?
* What exact action triggers it?
* Does timing matter?
* Does it happen on every attempt?
* Does it happen only with particular data?
* Does it depend on the browser or device?
* Does it depend on network conditions?
* Does restarting the application change anything?

Then I would change one variable at a time.

For example, if a task sometimes disappears after being saved, I could compare different network conditions, different task data, different devices, and different sequences of actions.

I would also use evidence such as:

* Screenshots
* Screen recordings
* Browser DevTools
* Network requests
* Console errors
* Application logs

If I find a pattern, I would use it to create a more focused reproduction scenario.

---

## 9. My Biggest Takeaway

The biggest lesson for me is that a tester should not stop at **"Does it work?"**

A better question is:

**"How does it behave, and why?"**

A tester needs to be comfortable with not immediately knowing the answer. Instead of seeing uncertainty as a problem, I can use it as a reason to investigate further.

I also think curiosity is one of the most valuable qualities a QA tester can have. A small unexpected detail can be the clue that leads to a significant bug.

At the same time, good investigation should be structured. I should not test randomly; I should form questions, make hypotheses, change conditions deliberately, collect evidence, and document what I discover.

My QA principle is:

**"Don't stop when the feature works — ask what else could happen."**
