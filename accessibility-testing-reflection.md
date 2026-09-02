# Accessibility Testing — QA Reflection

## 1. What Is WCAG?

WCAG stands for **Web Content Accessibility Guidelines**. It is a set of recommendations for making web content and digital products more accessible to people with disabilities.

WCAG is organized around four main principles, often remembered as **POUR**:

### Perceivable

Information and user interface components should be presented in ways that users can perceive.

Examples include:

* Sufficient color contrast
* Text alternatives for meaningful images
* Captions for relevant audio or video
* Content that can be resized
* Information that is not communicated only through color

### Operable

Users should be able to interact with the interface.

Examples include:

* Keyboard navigation
* Visible focus indicators
* Enough time to complete tasks
* Avoiding problematic flashing content
* Accessible controls and navigation

### Understandable

The interface and information should be understandable and predictable.

Examples include:

* Clear instructions
* Consistent navigation
* Helpful validation messages
* Predictable behavior
* Clear form labels

### Robust

Content should work reliably with different browsers, technologies, and assistive technologies.

This includes compatibility with screen readers and other accessibility tools.

---

## 2. Accessibility Conformance Levels

WCAG commonly defines three levels of conformance:

* **A** — minimum level
* **AA** — commonly targeted level for many products
* **AAA** — highest level

For practical QA testing, WCAG Level AA is often a useful target because it addresses many important accessibility barriers without requiring every AAA criterion.

Accessibility testing should still consider the actual users and context of the product rather than treating WCAG compliance as the only goal.

---

## 3. Screen Readers

A screen reader is assistive technology that converts information displayed on a screen into speech or other output that a user can navigate.

Examples include:

* **NVDA** — commonly used on Windows
* **VoiceOver** — built into Apple devices
* **TalkBack** — built into Android devices

Screen readers can read:

* Headings
* Buttons
* Links
* Form labels
* Text
* Notifications
* Navigation landmarks
* Error messages

Users can also navigate by different elements, such as headings or form controls.

### How QA Can Test with Screen Readers

A QA tester should perform important user workflows using a screen reader.

For example:

1. Start the screen reader.
2. Open the application.
3. Navigate through the main interface.
4. Move through headings and controls.
5. Check whether buttons have meaningful names.
6. Navigate through forms.
7. Enter information into fields.
8. Trigger validation errors.
9. Check whether errors are announced.
10. Complete important workflows without relying on visual information.

The goal is to determine whether a user can understand and operate the application using the screen reader.

---

## 4. Common Accessibility Issues

Common accessibility problems include:

### Missing Labels

Form controls may not have accessible names, making it difficult for screen reader users to understand their purpose.

### Poor Color Contrast

Text or UI elements may be difficult to see when there is insufficient contrast between foreground and background.

### Color-Only Information

If an application communicates status only through color, users with color vision deficiencies may not understand the information.

For example, using only red and green to indicate failure and success is problematic.

### Missing Alternative Text

Meaningful images may not have useful alternative text.

Decorative images should generally not create unnecessary noise for screen reader users.

### Keyboard Inaccessibility

Some controls may only work with a mouse or touch input.

### Missing Focus Indicator

Users navigating with a keyboard should be able to see which element currently has focus.

### Incorrect Focus Order

The focus order should follow a logical sequence.

### Unclear Error Messages

Error messages should explain what went wrong and how the user can correct it.

### Small Click Targets

Small controls can be difficult to operate for users with motor challenges.

### Unexpected Motion or Animation

Excessive animation can make interfaces harder to use for some users.

### Inconsistent Navigation

Important controls should behave consistently throughout the application.

---

## 5. Keyboard Navigation and Focus Management

Keyboard accessibility is important for users who cannot or prefer not to use a mouse.

### Keyboard Navigation Testing

I would test the application using only the keyboard.

Common keys include:

* `Tab` — move forward through interactive elements
* `Shift + Tab` — move backward
* `Enter` — activate controls
* `Space` — activate appropriate controls
* Arrow keys — navigate certain widgets where applicable
* `Esc` — close appropriate dialogs or menus

I would verify that all important interactive elements can be reached and operated.

### Focus Management

Focus should move logically and predictably.

I would check:

* Whether focus is always visible
* Whether the focus order makes sense
* Whether focus gets trapped unexpectedly
* Whether focus moves into newly opened dialogs
* Whether focus returns to an appropriate element after closing a dialog
* Whether disabled elements behave correctly
* Whether users can reach every important control

For example, if a modal dialog opens, keyboard focus should normally move into the dialog so the user does not have to navigate through the entire page to reach it.

---

## 6. Automated Accessibility Testing Tools

Automated tools can identify many common accessibility issues quickly.

Useful tools include:

### Lighthouse

Chrome Lighthouse can perform accessibility audits and identify certain accessibility problems.

### axe DevTools

axe DevTools can scan web pages for many common accessibility violations.

### WAVE

WAVE is another tool that can help identify accessibility issues directly in web pages.

### Accessibility Tree

Browser Developer Tools can expose an accessibility tree that helps QA understand how elements are interpreted by assistive technologies.

### Important Limitation

Automated accessibility testing cannot detect every accessibility problem.

For example, a tool may detect that an image has alternative text but cannot always determine whether the alternative text is actually meaningful.

Therefore, automated checks should be combined with:

* Manual testing
* Keyboard testing
* Screen reader testing
* Visual inspection
* Real user feedback where possible

---

## 7. Testing Focus Bear with a Screen Reader

To test Focus Bear with a screen reader, I would first identify the most important user journeys.

I would test workflows such as:

* Opening the application
* Logging in
* Navigating the dashboard
* Creating a task
* Editing a task
* Completing a task
* Managing habits
* Starting a focus session
* Reading notifications or status messages
* Changing settings

For each workflow, I would check whether:

* Every interactive element has a meaningful accessible name
* Buttons are announced correctly
* Form fields have labels
* Headings provide useful structure
* Navigation is understandable
* Current state is communicated
* Error messages are announced
* Dynamic content changes are communicated appropriately
* The user can complete the workflow without relying only on visual information

I would perform the same workflows using a keyboard where possible.

---

## 8. Accessibility Barriers for Users with ADHD or Autism

Accessibility is not limited to screen readers or physical disabilities. Cognitive accessibility is also important.

Some users with ADHD or Autism may be affected by:

### Excessive Information

Too many visual elements, notifications, or choices can increase cognitive load.

### Unclear Priorities

If everything appears equally important, it can be difficult to determine what action should be taken next.

### Unexpected Changes

Unexpected UI changes, automatic navigation, or sudden interruptions can make the interface harder to understand.

### Excessive Notifications

Frequent or unnecessary notifications can become distracting.

### Complex Workflows

Long or complicated workflows can increase the effort required to complete a task.

### Inconsistent Interface

Changing terminology, layouts, or interaction patterns can make the application less predictable.

### Time Pressure

Short time limits or unexpected timeouts can create additional difficulty.

### Excessive Animation

Movement or visual changes may be distracting or uncomfortable for some users.

### Unclear Feedback

Users should be able to understand whether an action succeeded, failed, or is still processing.

For a productivity application like Focus Bear, reducing unnecessary cognitive load and providing clear, predictable interactions can be particularly valuable.

These considerations should not be treated as assumptions about every person with ADHD or Autism. Users have different needs, so accessibility testing should combine established guidelines with user research and feedback.

---

## 9. If a Developer Says "This Doesn't Impact Most Users"

I would explain that accessibility issues should not be evaluated only by how many users experience them.

I would approach the discussion professionally and provide evidence.

First, I would explain:

* Which users are affected
* What task they cannot complete or what difficulty they experience
* How severe the impact is
* Whether there is an accessible alternative
* Whether the problem prevents access to an important feature
* Whether the issue creates legal, ethical, usability, or reputational risks where relevant

I would also demonstrate the problem using a screen reader, keyboard-only navigation, or another appropriate accessibility technique.

Instead of saying:

> "We must fix this because accessibility is important."

I could say:

> "This issue prevents keyboard users from reaching the Save button, which means users who cannot use a mouse cannot complete this workflow. I can reproduce it consistently, and the fix would make this critical task accessible."

This makes the discussion evidence-based rather than personal.

Accessibility should be treated as part of product quality, not as an optional feature for a small group of users.

---

## 10. Example Accessibility Test Checklist

| Area            | Test                          | Expected Result                                  |
| --------------- | ----------------------------- | ------------------------------------------------ |
| Keyboard        | Navigate with `Tab`           | All important controls are reachable             |
| Keyboard        | Activate button with keyboard | Button works without a mouse                     |
| Focus           | Open modal                    | Focus moves to an appropriate element            |
| Focus           | Close modal                   | Focus returns logically                          |
| Screen Reader   | Navigate buttons              | Buttons have meaningful accessible names         |
| Forms           | Navigate inputs               | Fields have clear labels                         |
| Forms           | Submit invalid data           | Errors are clear and accessible                  |
| Contrast        | Check text and controls       | Sufficient contrast                              |
| Color           | Check status indicators       | Information is not communicated by color alone   |
| Images          | Check meaningful images       | Appropriate text alternatives exist              |
| Navigation      | Move through main sections    | Navigation is logical and consistent             |
| Cognitive UX    | Complete important workflow   | Steps and feedback are clear and predictable     |
| Dynamic Content | Trigger status change         | Important changes are communicated appropriately |

---

## 11. Personal Reflection

Accessibility testing is an important part of QA because a product cannot be considered high quality if some users cannot effectively access or operate it.

I would test Focus Bear using both automated tools and manual methods. Automated tools such as Lighthouse, axe DevTools, and WAVE can help identify common issues, while keyboard and screen reader testing can reveal problems that automated tools may miss.

For screen reader testing, I would focus on important user journeys and verify that controls, forms, headings, errors, and dynamic content are communicated correctly.

For users with ADHD or Autism, I would pay particular attention to cognitive load, predictable navigation, clear priorities, unnecessary notifications, complex workflows, unexpected changes, and clear feedback. I would avoid assuming that every user has the same needs and would use accessibility principles together with user feedback.

If a developer says that an accessibility issue does not affect most users, I would advocate for the fix using evidence. I would demonstrate the impact, identify the affected users and workflow, explain the severity, and show how the issue can be reproduced.

My personal principle is:

**"Accessibility is part of quality, and every important user journey should be usable by as many people as reasonably possible."**
