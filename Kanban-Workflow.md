# Agile Workflows & Kanban

## 1. What is a Kanban Board?

A Kanban board is a visual tool used to manage work and track the progress of tasks.

Tasks are represented as cards and placed in different columns according to their current status.

A Kanban board makes the workflow visible to the whole team. It helps team members understand:

* What work needs to be done.
* What work is currently in progress.
* What work is blocked.
* What work is waiting for review.
* What work has been completed.

A simple Kanban workflow can look like:

`Backlog → Not Started → In Progress → Ready for Review → Approved by Bot → Done`

The exact columns can be adapted to the team's workflow.

---

## 2. Kanban Board Columns

Different columns represent different stages of the workflow.

### Backlog

The Backlog contains tasks that may need to be completed in the future but have not yet been selected for active work.

### Not Started

Tasks that are ready to be worked on but have not been started yet.

### In Progress

Tasks that are currently being worked on.

A task should normally move here when I actually begin working on it.

### Blocked

Tasks that cannot currently progress because something is preventing further work.

For example, a task could be blocked because:

* Information is missing.
* A dependency has not been completed.
* A required environment is unavailable.
* Another team member needs to provide information.

### Ready for Review

The task has been completed by the person working on it and is waiting for review.

For a documentation task, this could mean that the Markdown file has been created and is ready for someone to check.

### Approved by Bot

The task has passed the required automated or bot-based checks.

This stage is useful when the repository uses automated review or validation.

### Done

The task has completed all required steps and no further action is needed.

---

# 3. How Tasks Move Through the Board

Tasks move from one column to another as their status changes.

For example:

`Not Started → In Progress → Ready for Review → Approved by Bot → Done`

The person working on the task is generally responsible for keeping its status accurate.

If I start working on a task, I should move it to **In Progress**.

When I finish my work and it is ready to be checked, I should move it to **Ready for Review**.

After the required review or automated checks are completed, the task can move to the next appropriate status.

The important principle is that the board should reflect the **actual state of the work**, not the state I would like the work to be in.

---

# 4. Work In Progress (WIP)

WIP means **Work In Progress**.

A WIP limit restricts the number of tasks that can be actively worked on at the same time.

For example, if the WIP limit for `In Progress` is 2, I should avoid having five tasks simultaneously marked as In Progress.

## Benefits of WIP Limits

### Reduces overload

Limiting active tasks helps prevent trying to do too many things at once.

### Improves focus

Working on fewer tasks makes it easier to concentrate and finish them.

### Helps identify bottlenecks

If many tasks accumulate in `Ready for Review`, it may indicate that the review process is becoming a bottleneck.

### Encourages finishing work

Instead of constantly starting new tasks, the team is encouraged to finish existing work before starting more.

### Improves predictability

A controlled amount of work in progress can make it easier to understand how much work the team can realistically handle.

---

# 5. How Kanban Helps Manage Priorities

Kanban makes priorities visible.

Tasks can be ordered according to their importance, urgency, dependencies, or business value.

For example, a critical bug may need to be handled before a lower-priority documentation task.

Kanban also helps avoid overload because I can see how much work I already have in progress.

Instead of starting another task immediately, I can finish an existing task first.

This supports the idea of:

**"Stop starting, start finishing."**

---

# 6. My Kanban Workflow

For my Focus Bear work, I can use the following workflow:

`Not Started → In Progress → Ready for Review → Approved by Bot → Done`

I can also use `Blocked` when a task cannot progress.

This workflow gives me a clear view of what I am currently working on and what still needs attention.

For example:

* **Not Started:** Task has not been started.
* **In Progress:** I am actively working on it.
* **Ready for Review:** My work is complete and ready to be checked.
* **Approved by Bot:** Automated checks have passed.
* **Done:** All required work and verification are complete.
* **Blocked:** Progress is temporarily prevented.

---

# 7. Task I Moved Through the Kanban Process

I moved one of my Focus Bear tasks through the Kanban workflow.

The task started as:

**Not Started**

Then, when I began working on it, I changed it to:

**In Progress**

After completing the required work and documentation, I moved it to:

**Ready for Review**

After the required review/checks were completed, I moved it to:

**Approved by Bot**

Finally, once all requirements were satisfied, I moved it to:

**Done**

This helped me understand that changing a task's status should represent a real change in the state of the work.

---

# 8. Improving My Task Tracking

One way I can improve task tracking is by **keeping task statuses updated immediately when the state of the work changes**.

For example, if I start working on a task but leave it marked as `Not Started`, the board no longer accurately represents my workload.

I should therefore update the status when:

* I start working.
* I encounter a blocker.
* My work is ready for review.
* Review/checks are completed.
* The task is fully finished.

I can also add short comments when a task is blocked or when additional context is important.

---

# 9. Reflection

The main thing I learned from Kanban is that the board is not just a list of tasks. It is a visual representation of the team's workflow.

Kanban helps me understand what I should work on next, what I am currently doing, and where work may be getting stuck.

For my QA role, this is especially useful because testing work can change depending on development progress and priorities. For example, I may need to switch between testing a new feature, verifying a bug fix, performing regression testing, and documenting findings.

Using Kanban principles can help me avoid starting too many tasks at once and encourage me to finish work before taking on additional tasks.

My personal Kanban principle is:

> **Keep the board accurate, limit work in progress, and focus on finishing before starting more work.**
