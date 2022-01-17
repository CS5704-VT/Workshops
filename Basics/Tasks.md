# Task Management

In software engineering work, there are often many intangible sets of things _todo_ that have to be captured, assigned, prioritized, and tracked. Sticky notes are not going to cut it! Here are a few useful tools to help with managing tasks for software development.

## Issue Trackers

**Issue trackers** are systems to create, update, and resolve reported issues by customers or developers. An **issue** is a unit of work to accomplish an improvement in a system. This includes:
–a bug
–a requested feature
–a patch
–missing documentation, ... 

Popular issue tracking systems such as Bugzilla and JIRA originated as a bug reporting tools. A project hosted on GitHub comes with an issue tracker too. Anyone can report an issue, add labels, and any team member(s) can be assigned to an issue. Nowadays, developers also use issues as a lightweight task management tool. For this usecase, it best works for smaller projects.

See open issues: https://github.com/ottomatica/docable-notebooks/issues

See closed issues: https://github.com/ottomatica/docable-notebooks/issues?q=is%3Aissue+is%3Aclosed

Features:
* You can create task lists: https://github.com/blog/1375%0A-task-lists-in-gfm-issues-pulls-comments
* You can use labels to filter issues.
* You can add pictures, code snippets, etc. as comments. GitHub issues support markdown formatting.
* You can assign multiple people as an owner of issue.
* You can reply to a comment on an issue via email.

## 📝 Activity: Create an Issue

Create a new GitHub issue on the workshop repository (**_not_** _your Basics repository_) to report any issues on any of the topics covered in this SE Basics Workshop. This includes any errors or problems you faced, typos, or suggestions for improvements. Please do not create an issue saying there are no issues. Make sure it has a good title and description, an appropriate label, and assign the instructor (chbrown13) to the issue. To report multiple issues, create a task list for each one. 

## Kanban Boards

Tools such as [Trello](https://trello.com/) and [GitHub Projects](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/about-project-boards) serve as a planning tool that support kanban and agile methods.

![Project Board](https://miro.medium.com/max/4976/1*_St3BrB36V05JAuFIC3utQ.png)

### Boards, Lists, Cards

![image](https://cloud.githubusercontent.com/assets/742934/15636941/eb418154-25db-11e6-9814-5a3c835c0c11.png)

![image](https://cloud.githubusercontent.com/assets/742934/15635646/cbe2b4fa-25b2-11e6-8dc9-e6cafca6629c.png)

In kanban, you have a “visual” pipeline for transitioning ideas into a delivered product. With these tools, you can move a card (often representing a task) between lists, which are on a single board. Many options recently, such as [GitHub projects](https://docs.github.com/en/issues/organizing-your-work-with-project-boards/managing-project-boards/about-automation-for-project-boards), allow for further customization and automation of task management for projects based on your workflow (i.e. opened and closed issues, pull requests, etc.).

Recommended Pipeline:

* High-level goals: What do you want to accomplish?
* This Week: What actions can you do to accomplish those goals.
* Doing: What are you doing *today*
* Waiting: What is blocked.
* Done: What have you completed.

### Signs of a bad Kanban board

* Empty
* Only high-level goals
* Too many things
* Items sticking around not making progress.

Instead of saying "Do analysis" => a more suitable task might be "Find R package for doing peak detection". This is more concrete and actionable.

## 📝 Activity: GitHub Projects

On your SE Basics repository, navigate to the Projects tab to create a GitHub Projects board. Follow the instructions to add a project to your repository and select the "Basic kanban" template option(`TODO`, `In Progress`, `Done` columns). Once your project board is created, create cards to represent upcoming tasks related to this class including this workshop, HW0, finding a project group, and any more you can think of. Move the tasks to the appropriate column (i.e. this workshop is _In Progress_). Don't forget to update the workshop task to Done whenever you finish!

## Scrum

Scrum is another agile process for managing tasks. The most popular aspect people use is the daily stand-up meeting. In a daily standup, people report the progress and status of their tasks. The idea is that by standing up, you won't try taking too long to talk.

The main things covered in a scrum:

* What I did.
* What I need to do next.
* What is blocking me.

## 📝 Activity: Scrum Meeting

Find 1 or 2 other students in class to complete a standup meeting. You should be standing up together to answer the three questions above about the tasks you added to your Kanban board in the previous activity. If you are not able to do this in class, you may complete the stand-up virtually. In your SE Basics repository README, add the name(s) and email IDs of the students you completed the standup meeting with.


🥳 Congrats! You have completed the CS5704 SE Basics Workshop! You have started to master a great set of foundational skills preparing your for real software engineering work.