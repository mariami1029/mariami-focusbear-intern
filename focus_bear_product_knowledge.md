# Focus Bear – Product Knowledge Before Testing

## Introduction

Before starting QA work, I reviewed the Focus Bear Help Centre to better understand how the product is intended to behave. Understanding the expected behaviour is important because it gives me a baseline against which I can compare the actual application behaviour during testing.

I focused on features that are particularly relevant to Focus Bear's main purpose: task management, focus sessions, blocking, routines, and breaks.

---

## 1. To-Do List and Task Management

The To-Do List is integrated with Focus Blocks. When starting a focus block, the user can select an existing task or create a new one.

Tasks can also be organized and prioritized using categories such as important and urgent. Focus Bear also provides an Eisenhower Matrix to help users decide whether a task should be done, decided on, delegated, or deleted.

### Why this is useful for QA

When testing tasks, I should verify that:

* Users can create and select tasks before a Focus Block.
* Created tasks appear in the task list.
* Task information is preserved correctly.
* Task prioritization works as expected.
* The displayed task status and information are consistent across the application.

---

## 2. Block Lists and Website/App Blocking

Focus Bear uses Block Lists to control which applications and websites are allowed or blocked during Focus Sessions or Blocking Schedules.

Different Block Lists can be created for different purposes, such as work, studying, or creative activities. Block Lists can contain websites, URLs, subdomains, keywords, and applications.

The application also supports different blocking modes. For example, users can allow selected applications or block distracting websites while keeping other applications available.

### Why this is useful for QA

When testing blocking functionality, I should check:

* Whether the selected applications and websites are actually blocked.
* Whether the correct Block List is active.
* Whether changes to a Block List are saved.
* Whether different blocking modes behave differently.
* Whether blocking permissions affect the expected behaviour.

---

## 3. Blocking Schedule

Blocking Schedule allows Focus Bear to automatically block selected applications and websites at specific times without requiring the user to manually start a Focus Session.

Users can configure the days, start and end times, Block List, and strictness level. Different strictness levels provide different amounts of control over pausing or changing the blocking behaviour.

For example, a user could schedule social media blocking during working hours or create a distraction-free study period.

### Why this is useful for QA

Important test areas include:

* Correct start and end times.
* Correct days of the week.
* Correct Block List being applied.
* Behaviour when a schedule is paused.
* Behaviour under different strictness levels.
* Whether the schedule continues to work after restarting the application.

---

## 4. Habits and Routines

Focus Bear allows users to customize their habits and routines. Users can configure morning and evening routine times, activity durations, priorities, and the days on which activities should occur.

Activities can be marked as **Must Do** or **Optional**. Must Do activities are treated as higher priority, while Optional activities provide more flexibility.

The Help Centre also explains that users should save their changes and restart the application when required after editing habits.

### Why this is useful for QA

When testing habits, I should pay attention to:

* Whether edited times are saved correctly.
* Whether the correct habits appear on the correct days.
* Whether activity durations are respected.
* Whether Must Do and Optional activities behave differently.
* Whether changes remain after an application restart.

---

## 5. Meeting Mode and Break Behaviour

Focus Bear includes a dedicated Meeting mode. The Help Centre states that Focus Bear can detect meetings and automatically suspend break reminders. Users can also customize which applications and websites are allowed during meetings.

The Help Centre also distinguishes between different types of breaks, including Pomodoro breaks and Micro Breaks. The Knowledge Base describes Pomodoro breaks as five-minute breaks with more freedom to use applications and websites.

### Why this is useful for QA

This gives me several areas to test:

* Whether meeting detection behaves correctly.
* Whether break reminders are suspended during meetings.
* Whether allowed applications and websites work correctly in Meeting mode.
* Whether different break types behave according to their intended purpose.
* Whether break settings remain consistent across different focus activities.

---

# Reflection

## What I Learned

Before reviewing the Help Centre, I mainly understood Focus Bear as a productivity application that blocks distracting websites and applications.

After reviewing the documentation, I learned that the product is broader than simple website blocking. It combines several mechanisms, including Focus Sessions, tasks, Block Lists, scheduled blocking, habits and routines, breaks, and Meeting mode.

I also learned that many features depend on their configuration. For example, the behaviour of blocking can change depending on the selected Block List and strictness level. This means that when I find unexpected behaviour during testing, I should first check the configuration before deciding that the feature is defective.

Another important point is that some features have dependencies or platform-specific behaviour. For example, the Help Centre contains different instructions for Windows, Mac, Android, and iOS for some features.

---

# Help Centre vs. Current App

During testing, I noticed that some terminology and behaviour in the application can differ from what I might initially expect based on the documentation.

One example is task status terminology. In the task creation/editing interface, statuses such as **Not Started**, **In Progress**, and **Completed** are used, while another part of the application displays corresponding statuses as **To Do**, **Doing**, and **Done**.

The behaviour can still be understandable once the mapping is identified, but the difference in terminology could potentially cause confusion for a new user.

This is a useful reminder for QA that documentation and the current product should both be considered when establishing expected behaviour.

I would also continue checking Help Centre articles against the current application during future testing, especially when an article contains platform-specific instructions or references older interface names.

---

# Key Takeaways for My QA Testing

After reviewing the product documentation, I will use the following principles when testing Focus Bear:

1. **Understand the feature's purpose before testing it.**
2. **Check configuration before reporting unexpected behaviour.**
3. **Consider platform-specific differences.**
4. **Verify that saved settings persist when relevant.**
5. **Compare related parts of the application for terminology and behaviour consistency.**
6. **Use the Help Centre as a reference, but verify that the documented behaviour matches the current application.**

This research gives me a better baseline for exploratory testing because I now have a clearer understanding of how the main Focus Bear features are intended to work.
