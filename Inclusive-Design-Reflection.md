# Inclusive Design Reflection

## 1. What Are Vulnerable Populations?

Vulnerable populations are groups of people who may face additional barriers, risks, or disadvantages when interacting with products, services, or digital environments.

Examples can include:

* People with disabilities
* Neurodivergent individuals
* Older adults
* Children
* People with limited digital literacy
* People with language or communication barriers
* People experiencing mental health difficulties
* People with limited access to technology or reliable internet

In a digital product, these users may experience difficulties that are not obvious to people without the same challenges.

For example, a complex interface, unclear instructions, excessive notifications, or unpredictable behaviour can increase cognitive load and frustration.

---

## 2. Ethical Considerations When Designing for Neurodivergent Users

When working with neurodivergent users, the goal should not be to force everyone to interact with a product in the same way.

Important considerations include:

* Use clear and predictable navigation.
* Avoid unnecessary complexity.
* Reduce cognitive load.
* Avoid overwhelming users with too many choices.
* Provide clear and understandable feedback.
* Avoid shame-based or judgmental language.
* Respect different sensory preferences.
* Make important information easy to find.
* Give users appropriate control over notifications and interruptions.
* Avoid assuming that every person with ADHD or Autism has the same needs.

Accessibility should be considered as part of good product design rather than as an additional feature.

---

## 3. Making Content More Accessible for ADHD and Autistic Users

Some useful approaches include:

### Clear language

Use simple and direct language instead of unnecessarily complicated instructions.

### Predictable navigation

Users should be able to understand where they are and what will happen when they perform an action.

### Reduced cognitive load

Avoid presenting too many actions, options, or pieces of information at once.

### Visible next steps

When possible, make it clear what the user can do next instead of making them figure it out themselves.

### Customisation

Different users may have different needs, so allowing customisation of notifications, sounds, schedules, and other features can improve accessibility.

### Non-judgmental feedback

Missing a task or breaking a routine should not make users feel that they have failed as a person.

---

## 4. Supporting Neurodivergent Team Members

The same principles can apply to communication and collaboration within a team.

I can support teammates by:

* Communicating clearly and directly.
* Providing important instructions in writing.
* Giving enough context when assigning tasks.
* Avoiding unnecessary ambiguity.
* Respecting different working styles.
* Allowing reasonable flexibility when possible.
* Not assuming that silence means disagreement or lack of interest.
* Giving people time to process complex information.
* Asking teammates what communication style works best for them.

The important point is that neurodivergent people are individuals, so I should avoid making assumptions based only on a diagnosis or label.

---

# First-Person Account

## 5. What I Learned From an ADHD Experience

I read a first-person account by Joseph Oranagwa, an ADHD-diagnosed software builder, describing his experiences with productivity tools.

One important point from his experience was that many traditional productivity systems created additional pressure instead of reducing it. He described trying tools such as Notion, Todoist, Things, Asana, Linear, and others. In his experience, seeing a large list of tasks could become overwhelming rather than motivating.

He also described how traditional systems often assume that a person has the same cognitive capacity every day and can consistently prioritise tasks from a fixed list.

This made me think differently about productivity software. A feature that appears useful from a traditional productivity perspective can have the opposite effect for some users.

Source: *My Brain Isn't Broken. The Tools Were.* by Joseph Oranagwa, August 19, 2026.

The main lesson I took from this account is:

> A productivity tool should reduce unnecessary cognitive effort rather than create more decisions and pressure.

---

# Reflection

## 6. How I Can Adjust My Communication Style

When communicating with neurodivergent users or teammates, I should:

* Be clear about what I am asking.
* Avoid vague instructions when a specific explanation is possible.
* Break complicated information into smaller parts.
* Avoid unnecessary urgency.
* Give people enough time to process complex information.
* Use written instructions when details are important.
* Ask whether additional clarification is needed instead of assuming.
* Focus on solving the problem rather than blaming the person.

For example, instead of saying:

> "You need to fix this."

A more supportive approach would be:

> "It looks like this part is not behaving as expected. Could you check the behaviour described in the requirements and let me know if you need any clarification?"

---

## 7. Potential UX and Communication Pitfalls

Some potential problems that could make Focus Bear less accessible include:

### Too many options at once

A screen with too many settings or choices can increase cognitive load.

### Overly complicated instructions

Long or unclear instructions can make it difficult to understand what action the user should take.

### Shame-based feedback

Messages that make users feel guilty about missed tasks or broken routines may discourage them from continuing.

### Excessive notifications

Frequent notifications can become distracting instead of helpful.

### Unclear system states

If users cannot easily understand whether an action succeeded, they may become confused or repeatedly perform the same action.

### Unexpected behaviour

Unexpected app restarts, changes, or interruptions can be particularly frustrating for users who depend on predictable routines.

---

# Practical Improvement

## 8. One Design Improvement for Focus Bear

One improvement I would recommend is providing a **simple "What's next?" view** that shows only the most relevant next action instead of presenting the user with a large amount of information.

For example:

**Your next step**

> Focus on: Complete your 20-minute study session.

Then provide one clear primary action:

**Start Focus Session**

Additional tasks and information could remain available, but they would not immediately compete for the user's attention.

This could reduce cognitive load and make task initiation easier for users who struggle with executive functioning.

---

# Supportive User Response

## 9. Hypothetical User Situation

### User:

> "I know I need to work, but I can't seem to start. I keep looking at my task list and getting overwhelmed."

### My Response:

> "That's okay. You don't have to complete everything right now.
>
> Let's make the next step smaller. Choose just one task you want to work on and focus on starting it rather than finishing it.
>
> If the task feels too large, try breaking it into the smallest possible first action. For example, instead of 'finish the report', the first step could simply be 'open the report and write the title'.
>
> You can then start a short Focus Session and reassess when it ends. There's no need to solve the entire task list at once."

This response is intended to be patient, supportive, and non-judgmental. It focuses on reducing the immediate cognitive load instead of suggesting that the user simply needs more discipline.

---

# My Practical Change

## 10. What I Will Do Differently

As a QA intern, I will consider accessibility and cognitive load when testing Focus Bear.

In addition to asking:

**"Does this feature work correctly?"**

I will also ask:

**"Could this behaviour unnecessarily confuse, overwhelm, or frustrate a user?"**

For example, I will pay attention to:

* The amount of information shown at once.
* Whether instructions are clear.
* Whether actions have understandable feedback.
* Whether navigation is predictable.
* Whether notifications or interruptions could become excessive.
* Whether error messages are supportive and understandable.
* Whether the product provides a clear next step.

I will also avoid assuming that a behaviour is problematic for every neurodivergent user. Different users have different needs, so accessibility testing should consider flexibility and user choice.

---

# Key Takeaways

1. Accessibility is not only about technical accessibility; cognitive and emotional usability also matter.
2. Neurodivergent users should not be treated as one homogeneous group.
3. Clear communication and predictable interfaces can reduce unnecessary cognitive load.
4. Productivity tools should support users without creating additional pressure or shame.
5. As a QA tester, I should consider both functional correctness and the user's experience.
6. AI, research, and user feedback can help generate ideas, but real user needs and product evidence should guide final decisions.

## Personal Rule

> **Make the next step clear, reduce unnecessary cognitive load, and never assume that one workflow works for everyone.**
