# Agile Principles at Focus Bear

## 1. What is Agile?

Agile is a way of working that focuses on delivering value continuously, adapting to change, and collaborating closely with customers and team members.

Unlike traditional project management approaches, where requirements and plans are often defined in detail at the beginning and followed sequentially, Agile allows teams to adjust their plans as they learn more.

### Traditional project management

A traditional approach often follows a more sequential process:

1. Define requirements
2. Plan the project
3. Develop the product
4. Test the product
5. Release the product

Changing requirements later in the project can be expensive or difficult.

### Agile approach

Agile works through shorter cycles of planning, development, testing, feedback, and improvement.

The team can reprioritize work when requirements, customer needs, or business priorities change.

For QA, this means testing and providing feedback throughout the development process rather than waiting until the very end.

---

## 2. Agile Manifesto

The Agile Manifesto is based on four core values:

1. **Individuals and interactions over processes and tools**
2. **Working software over comprehensive documentation**
3. **Customer collaboration over contract negotiation**
4. **Responding to change over following a plan**

This does not mean that processes, documentation, contracts, or plans are unimportant. It means that the items on the left are valued more when there is a conflict between the two sides.

### Important Agile principles

Some Agile principles that are particularly relevant to QA include:

* Deliver valuable software frequently.
* Welcome changing requirements, even late in development.
* Developers and business stakeholders should work together regularly.
* Build projects around motivated individuals and give them the support they need.
* Working software is the primary measure of progress.
* Continuous attention to technical excellence and good design improves agility.
* Teams should regularly reflect on how to become more effective and adjust their behaviour accordingly.

---

# 3. Scrum vs Kanban

Scrum and Kanban are both Agile approaches, but they organize work differently.

| Aspect              | Scrum                                                | Kanban                                                      |
| ------------------- | ---------------------------------------------------- | ----------------------------------------------------------- |
| Work structure      | Fixed-length sprints                                 | Continuous flow                                             |
| Planning            | Sprint planning                                      | Work is selected based on priority and capacity             |
| Roles               | Defined roles such as Scrum Master and Product Owner | No mandatory roles                                          |
| Work limits         | Usually limited by sprint commitment                 | Uses Work In Progress (WIP) limits                          |
| Changes during work | Changes are generally avoided during a sprint        | Work can be reprioritized more easily                       |
| Meetings            | Usually includes defined Scrum events                | Meetings are flexible and depend on team needs              |
| Delivery            | Often associated with sprint increments              | Continuous delivery                                         |
| Best suited for     | Teams working in regular iterations                  | Teams with changing priorities and continuous incoming work |

## Scrum

Scrum organizes work into fixed periods called **sprints**, commonly lasting one to four weeks.

At the beginning of a sprint, the team selects work from the backlog. During the sprint, the team works toward a specific goal.

Scrum also defines specific roles and events, such as sprint planning, daily Scrum, sprint review, and retrospective.

## Kanban

Kanban focuses on **visualizing work and maintaining a continuous flow**.

Work is usually represented on a board with columns such as:

`To Do → In Progress → Review → Done`

A key Kanban concept is the **Work In Progress (WIP) limit**. This limits how many tasks can be worked on at the same time and helps prevent bottlenecks.

Unlike Scrum, Kanban does not require fixed sprints. New work can enter the workflow when there is available capacity.

---

# 4. Why Kanban Can Be Useful for Focus Bear

Focus Bear's work can involve changing priorities, bug reports, improvements, research tasks, and other work arriving at different times.

A Kanban-style workflow can therefore be useful because it allows the team to:

* Prioritize the most important work.
* React quickly when priorities change.
* Handle bugs and urgent issues without waiting for the next sprint.
* Visualize the current state of work.
* Avoid taking on too many tasks simultaneously.
* Continuously deliver improvements.

For a QA intern, this means that testing work can also change depending on what the team needs most at a particular moment. For example, I may need to test a new feature, investigate a bug, verify a fix, or perform exploratory testing depending on the current priorities.

---

# 5. Benefits of Agile

I think the biggest benefits of Agile are:

### Faster feedback

Testing and feedback happen throughout development. This can help identify problems earlier.

### Adaptability

Requirements and priorities can change without requiring the entire project plan to be rewritten.

### Better collaboration

Developers, QA, product, and other team members communicate more frequently.

### Continuous improvement

Teams can learn from their previous work and improve their processes over time.

### Customer focus

Agile encourages teams to focus on delivering useful functionality and responding to customer needs.

---

# 6. Challenges of Agile

Agile also has some challenges.

### Changing priorities

Frequent changes can make it difficult to maintain a stable plan and can sometimes interrupt ongoing work.

### Communication requirements

Agile depends heavily on communication. If information is unclear or team members do not communicate effectively, misunderstandings can occur.

### Difficult estimation

When requirements are changing, it can be difficult to predict exactly how long work will take.

### Risk of losing focus

If priorities change too frequently, team members may start many tasks without finishing them.

### Requires discipline

Agile does not mean "work without a plan." Teams still need prioritization, clear communication, documentation where useful, and accountability.

---

# 7. How Agile Principles Apply to My QA Role

Agile principles can improve my responsibilities as a QA engineer in several ways.

First, I should not think of QA as something that happens only after development is finished. I can contribute earlier by reviewing requirements, identifying risks, asking questions, and thinking about possible edge cases.

Second, I should communicate issues clearly and early. If I find a blocker or a potentially serious bug, it is better to communicate it rather than waiting until the end of a task.

Third, I should be comfortable with changing priorities. A new critical bug may become more important than the feature I was originally testing, so I need to adapt.

Finally, I should continuously improve my testing process by learning from previous bugs, feedback, and testing results.

---

# 8. My Chosen Agile Principle

The Agile principle I think will be most useful in my work is:

> **"Welcome changing requirements, even late in development."**

As a QA engineer, I think this principle is important because software rarely remains exactly as originally planned.

A requirement may change because of user feedback, a newly discovered problem, technical limitations, or a business decision. Instead of treating every change as a problem, I should understand why the change is happening and adapt my testing accordingly.

For example, if a feature changes shortly before release, I should update my test cases, identify the affected areas, perform regression testing where necessary, and communicate any risks I discover.

This mindset can help me become a more flexible and useful member of the team.

---

# 9. Personal Reflection

The main thing I learned from this research is that Agile is not simply about having fewer plans or more meetings. It is mainly about **delivering value, communicating effectively, getting feedback, and adapting when circumstances change**.

I also learned that Scrum and Kanban solve similar problems in different ways. Scrum provides a more structured framework with fixed sprints and defined roles, while Kanban focuses more on continuous flow and flexibility.

For my work at Focus Bear, I think the Kanban approach is particularly useful because QA tasks can vary significantly. One day I may be working on exploratory testing, while another day I may need to verify a bug fix or test a new feature.

My personal Agile principle is:

**"Communicate early, adapt to change, and focus on delivering useful results."**
