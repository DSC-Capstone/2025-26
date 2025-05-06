---
layout: page
title: "Lesson 9 – Project Management"
nav_exclude: true
---

# Lesson 9 – Project Management
{:.no_toc}

All lectures will be delivered as readings that you complete on your own time. Post questions with the lesson on Piazza.

{: .red }
**While this lesson doesn't have an associated Methodology Assignment, you should read it before you finalize the [Schedule component of your Quarter 2 Project Proposal](https://dsc-capstone.org/2024-25/assignments/projects/q2-proposal#schedule-graded-by-your-mentor), due on Monday, December 2nd.<br><br>Also, please fill out both the official [Student Evaluations of Teaching](https://academicaffairs.ucsd.edu/Modules/Evals/) (by Saturday 11/30). Thank you for your feedback!** 

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

In Quarter 2, you will work on **everything** in groups. This makes it important that your group is able to work well together; you only have 10 weeks to execute your project, which is not very long. To encourage your groups to work as productively as possible, we're going to:
1. Require that all groups meet weekly _outside_ of discussion section.
1. Require that all groups maintain a running meeting notes Google Doc that their mentor, TA, and your instructor all have access to; this will allow us to maintain a paper trail of who is doing (and saying) what. This document is also where each group will answer their weekly participation questions (which, as you guessed it, will also be answered in groups).

We'll talk more about the specifics how Quarter 2 will work at the start of the quarter. For now, this lesson will cover a few principles to follow, particularly in the context of developing software, so that you make the most of your meetings with your group and maximize your chances of successfully executing your Quarter 2 Project Proposal.

---

## Agile Software Development

**Agile** is a product management technique that we recommend you follow this quarter when executing your project. Before we discuss the details of Agile development (yes, [Agile is a proper noun in this context](https://www.scrum.org/resources/blog/agile-and-scrum-entwined-and-related)) and how you'll use it in your workflow, let's discuss how Agile came to be. 

### History of Software Development

Before the 1960s, software as we know it today didn't exist. At the time, computer programs were inseparable from the hardware they were written for. It was common for projects to be localized to a single computer, and as such, there was no need for programmers to think about how to organize their code so that others could use it.

<center><img src="assets/old-computer.png" width="50%"></center>

Then, in the 1970s, hardware-agnostic programming languages – such as C – began to gain traction. This decoupling of software from hardware accelerated the growth of programming as a career, and the size of software projects dramatically increased.

This led to an interesting confluence – programmers were writing code that _could_, in theory, be run on others' computers, but since they hadn't been paying attention to the [robustness or organization of their code](https://en.wikipedia.org/wiki/Cowboy_coding), their code often _couldn't_ run on others' computers. Most code didn't work when shipped, which meant that programmers would have to spend time fixing someone else's code before they could get it to run on their own machine. Unfortunately, in some ways, data science [is still in this phase](https://twitter.com/emollick/status/1597733433765433344?s=20&t=8tR_rzjUe6nIPdwltz62-Q), which is why one the goals of the methodology portion of the capstone is to have you write and maintain your code in such a way that others can obtain and run your code without any additional setup.

One proposed strategy for managing the development of large group software projects was **waterfall development**, which is still in use today in some organizations. In waterfall development, _before_ work begins on a project, the team clearly states:
- What steps are required to execute the project.
- What needs to be completed in order to move from step N to step N + 1, for N = 1, 2, 3, ...

Then, the team works in on these steps in series – that is, the team finishes step 1, then once step 1 is finished, the team finishes step 2, and so on.

<center><img src="assets/waterfall.png" width="40%"><br>(<a href="https://medium.com/@joneswaddell/the-cascading-costs-of-waterfall-5c3b1b8beaec">source</a>)</center>

While this process can work in some settings, there are clear pitfalls:
- Not each team member has the same set of skills, and so often each will be assigned to a single step. This results in a lots of wasted time – what are your team members supposed to do while you're working on your step?
- If the project requirements change in, say, step 5, the entire process needs to be restarted.

### Agile Development

In 2001, a group of developers wrote the [_Manifesto for Agile Software Development_](https://agilemanifesto.org):

> We are uncovering better ways of developing
software by doing it and helping others do it.
Through this work we have come to value <center>
<b>Individuals and interactions</b> over processes and tools
<br> <b>Working software</b> over comprehensive documentation
<br> <b>Customer collaboration</b> over contract negotiation
<br> <b>Responding to change</b> over following a plan</center>
<br> That is, while there is value in the items on
the right, we value the **items on the left** more.

Agile development is centered around having a working product (i.e. working code) at each stage of the project development process. This is in stark contrast to the waterfall method, in which the project only "works" at the very end. Agile development also emphasizes flexibility, which is **crucial** in data science projects. Plans change often, and by working incrementally and reflecting frequently (in your weekly meetings), you'll be able to quickly shift the trajectory of your project without wasting any time.

The following video does a good job of providing intuition for the difference between Agile and waterfall development.

<center><iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/QLvBK9stdoM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></center>

### Agile Development in the Capstone

As mentioned earlier, you're encouraged to follow the principles of Agile development when working on your projects this quarter. Waterfall development will **not** work – there is simply no time for you to sit idle for weeks while your partners work. All group members need to be active each week.

When creating the [**schedule for your Quarter 2 Project Proposal**](https://dsc-capstone.org/2024-25/assignments/projects/q2-proposal#schedule-graded-by-your-mentor), you should create a list of tasks that each group member will do each week. Write your schedule in such a way that:

- **Each group member can work in parallel.** That is, Person B should not have to wait for Person A to finish a task before they can start working. If Person B is working on a feature that depends on Person A's output, Person B can use synthetically-created data (or something similar) as a placeholder for Person A's output until it is finalized. (For a concrete example, Person A may be writing scripts that clean raw data, and Person B may be building a machine learning model.)
- **Each group member is working on a different task than in the previous week.** It's totally fine if a particular task takes two weeks to complete, but the description of that task in your schedule should be different for both weeks, to reflect the breakdown of that task into smaller subtasks.
- **Each group member knows what everyone else is actively working on.** Not only will this held each group member accountable, but it'll also give other group members the opportunity to help resolve issues with tasks that weren't initially assigned to them.
- **The team, as a unit, produces code that is fully buildable and runnable.** All group members should regularly merge their code into the `main` branch of the repo, which will ensure that the `main` branch always contains a "complete" project.  It **should not** be the case that your group's codebase only runs in Week 7.  (Using the example from the embedded video above: your repo should always contain a fully-constructed house. The number of rooms and hallways of that house can change as the weeks go on, but it should always be a complete house.). **Note what we said in [Lesson 6 (Git) regarding version control in DSC 180B](https://dsc-capstone.org/2-24-25/lessons/06/#version-control-next-quarter-in-dsc-180b).**
- **The team, as a unit, decides what the plan for the next week is, and if any part of the existing schedule needs to change.**

To achieve all of these goals, it will be necessary to be in regular communication with your group, not just in section, but in your (required) separate weekly meetings and asynchronously.

{: .green }
**At the start of Quarter 2, we'll announce the due dates for all project deliverable checkpoints (e.g. poster checkpoint, code checkpoint, report checkpoint); at that point, you may need to modify your schedule slightly. You'll also need to modify it each week in the event anything changes. Keep things flexible and be AGILE!**
