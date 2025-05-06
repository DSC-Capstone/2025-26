---
layout: page
title: "Lesson 5 – Ethics and Values"
nav_exclude: true
---

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Lesson 5 – Ethics and Values
{:.no_toc}

All lectures will be delivered as readings that you complete on your own time. Post questions with the lesson on Piazza.

Make sure to read this article before moving on to [Methodology Assignment 3](https://dsc-capstone.org/2024-25/assignments/methodology/03), which is due on Sunday, November 3rd.

{: .green }
**This lesson was prepared by [Professor David Danks](https://www.daviddanks.org), who is jointly appointed in Data Science and Philosophy. All project groups will be required to check in with Professor Danks in Quarter 2 to reflect on how the concepts and ideas below apply to their projects.**

As a reminder, the [Quarter 1 Project Checkpoint](https://dsc-capstone.org/2024-25/assignments/projects/q1) is due on **Monday, November 4th**.

---

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Overview

The past few years have seen story after story about ethically or societally problematic data science. People have been unethically denied loans or healthcare; self-driving modes on cars have made awful mistakes, even leading to fatalities; resume screeners have downgraded applicants from under-represented groups; racial and socioeconomic biases in our healthcare systems have been reinforced and worsened through data science; and many, many more examples across a range of sectors.

At the same time, we might naturally wonder about our obligations as data scientists in these kinds of situations. Of course, _someone_ should be worrying about these issues, but why should it be us? Presumably, none of us wants to contribute to some horrible, unethical data science project; for example, the people who worked on the data science projects mentioned in the previous paragraph were not consciously racist or sexist or wanting cars to hit people. We can be concerned about these problematic events, but also think that we shouldn’t necessarily do anything differently in our own data science. **The goal of this lesson is to convince you that this attitude is overly simplistic, and then provide you with the tools to start to do better. We will get more practice using some of these tools in Quarter 2 of the capstone**.

---

## Isn’t Data Science Just Math?

One common view is that data science, including a data science project, is simply some math and code, and that math and code are not the kinds of things where ethics and values matter. In particular, we might think that math and code are simply tools, and that ethics matters only for the ways that we **use** tools, not the tools themselves. On this picture, we data scientists wouldn’t need to worry about ethics when building a system or model; ethics would matter only when someone (perhaps not us) decides to use it.

Unfortunately, this common view is far too simplistic. Data science efforts such as your capstone projects are filled with choices and decisions that bring values into your system or model, long before it is used for any purpose. Here’s a simple example: imagine that you are building an autonomous car. You probably want it to embody values such as:
- Always obey traffic laws.
- Always minimize the probability of an accident (while still arriving in a timely manner).

The problem is that you cannot build an autonomous car that satisfies both of these. (Why not? Because you minimize the probability of an accident by driving a little slower than the traffic around you, but that might require speeding if everyone else is speeding even more.) **The crucial point here is that the math and code don’t care which of these two values is prioritized, or how we tradeoff between them. That decision must be made before we ever start building our car in the first place.**

Alternately, imagine that you are building a data analytic tool to diagnosis a medical condition such as cancer. This system will almost certainly not be perfect: there will be both false positives and false negatives. In fact, as we all know, you can almost always “tune” the system to have different ratios of false positives and false negatives (i.e., we can pick different points on the ROC curve). Again, the math and code don’t dictate what tradeoff to use. That choice comes from us, and depends on the relative costs and benefits of the different errors for the relevant people.

In general, a useful heuristic is: Values and ethics matter for every decision that is _not_ dictated by the math or code alone. There are going to be some decisions that you make that do not really have ethical or societal implications. But in practice, most of your choices will have some ethical impact.

---

## Sources of Values in Data Science Projects

It can be tempting to think that data science doesn’t involve values or ethics, not least because we spend so much time thinking and learning about the math and code. But as you start to work on full data science projects, it’s important to recognize all of the different value choices that you are making along the way. Here is an incomplete list of decisions where values enter your data science effort:

1. What problem or challenge are we trying to solve or address?
    - We cannot solve every problem, and so it is an ethical decision to use our limited time and resources on _this_ challenge rather than _that_ challenge. We have to decide which problems really matter, and that will inevitably require thinking about who benefits, who suffers, and so on.
1. Which constraints (temporal, financial, social, legal, etc.) actually matter? How do we resolve conflicts between those constraints?
    - Any real-world project inevitably faces many potential constraints on design, implementation, and deployment. Only some of those constraints will be _important_ enough to matter for our project, but that importance is not a purely technical matter. For example, we might be able to eliminate a computational constraint by spending more money, or we might be stuck with a small fixed budget. The math and code don’t tell us how to resolve the conflict, or even what those constraints are. Instead, we have to think about what matters to us, or other people who might be affected by what we do.
1. What counts as success for our effort? One specific version is: What loss function do we use for optimization?
    - All data science efforts have success conditions, either implicit or explicit. That is, every project has some understanding of what counts as success and what would be failure. We might, for example, want to predict who is likely to succeed in college, but that is a relatively vague target. We need something more precise for our data science effort, such as “predict who is least likely to drop out after one year” or “predict each person’s post-graduation starting salary” or many other possibilities. Our choice will build values into our data science effort, as it will determine what matters for the system. Or for a more impactful example, consider the choice by social networks to optimize for engagement rather than learning or civil discourse! Even something as seemingly simple as choosing to optimize for “minimize squared error” vs. “minimize variance of error” is introducing values into our data science effort, as this choice implies that some aspects of errors are more important than others.
1. What counts as an outlier? What counts as an error (that should be addressed)?
    - Even something as technical as outlier detection and removal can introduce values into our data science project. The decision that some datapoint is an outlier is fundamentally about saying “that datapoint should not matter for our model.” Of course, that might be the correct decision; if I have a datapoint that says someone’s age is 417 years old, then something has clearly gone wrong in data collection. But matters are rarely so clear, and so we have to make value choices about which datapoints are too “bizarre” to include.

As mentioned above, this is a partial list; we could give many other examples of choices where values enter our data science effort. In fact, if you examine all of the decisions that must be made in the lifecycle of a data science project, then you will find that very few of them are dictated by the math and code. At almost every point, there will be multiple possibilities, and the decision to choose one (rather than another) is a way of saying “this one matters more,” which is fundamentally an ethical choice. You should not think of ethics as something extra that happens at the end or if you are feeling virtuous. **We are all (as data scientists) already doing ethics!**

---

## Who Are the Stakeholders? What Are Their Values?

If we are all already doing ethics, then we should be asking “how can we do it better?” In previous sections, we repeatedly used the term ‘value’, and you might be wondering what that word means in this context. In general, values are the things that matter to us, that we would be willing to pay some cost to advance or protect. For example, you might value being a good student: academic success might be something that matters to you, and that you are willing to work to achieve. 

All of us value many different things. For instance, in addition to valuing academic success, you might also value being a good friend. Of course, it might not feel like much of a “cost” to spend time with your friends, but that decision nonetheless reflects your priorities. As this example shows, values are not necessarily self-centered. I can value being a member of a thriving community, or value my child’s health, or many other values that are primarily understood in terms of someone else’s success. What makes these count as my values is that they matter to me, and I will act in ways to try to advance them.

One of the core questions in ethics is: what should I do when my values conflict with one another? There will inevitably be times when I cannot advance all of my values simultaneously; for example, I might have to choose between spending time with friends and studying for an exam. One function of ethical theories (e.g., utilitarianism, deontology, virtue ethics, and other labels you might have seen before) is to help you resolve these conflicts; they essentially help to provide decision procedures. 

(Another core question is: which values should I have? While this is an important (and hard!) question, we won’t try to answer it here. For almost all of the capstone projects, it will be clear what values we, or others impacted by the effort, should have.)

At the same time, we often do not need to use a specific ethical theory to know how to resolve the conflict. For example, I value having money and I value not breaking the law, but these can come into conflict if I consider robbing a bank. However, every ethical theory is going to agree that I should resolve this conflict in favor of not breaking the law (unless there are incredibly strange circumstances). 

We can now better understand how different values are implemented or advanced in our data science efforts. The decision to predict which students will get good grades vs. which students will have a high post-graduation salary indicates something about what matters to us (or the client, if we are doing the data science for someone else); it says that some values are more important than others. Or if we design our self-driving car to always follow the law (even if that behavior would increase the chances of an accident), then we are again prioritizing some values over others. That is, we are making ethical choices.

Of course, not everyone’s values matter for a particular data science effort. Instead, we need to focus on the values of key _stakeholders_: essentially, those individuals or groups who will be impacted by this data science effort. Importantly, the key stakeholders are not only end-users or clients, but can include people who never directly interact with the data science system themselves. For example, if I use data science to guide promotion decisions at my company, then my employees are key stakeholders, even if they don’t know that the system is being used at all.

The values of key stakeholders will almost always be different from one another. The things that matter for my employees are going to be different from what matters for me. This _value pluralism_ is very common, but also does not necessarily pose a challenge for data scientists. The mere fact that we have different values does not imply that we face an intractable problem. For example, I have different values than other drivers on the road, and yet we (mostly) can work together so everyone can get to their destination.

The problematic cases are those of _value conflicts_, where the ideal data science effort for one stakeholder is different from the ideal for another stakeholder. For example, the ideal search recommendation engine for users will be different than for the company (since the company wants to maximize engagement, advertising, and other profit-related measures). In these situations, we (or perhaps our clients or managers) are going to have to pick “winners” and “losers.” It is wonderful when we can do our data science in ways that advance everyone’s values, but those cases are unfortunately rare. And we have a professional obligation to openly address these conflicts so we can make intelligent decisions about how to resolve them.

---

## Using What You’ve Learned

The process of resolving value conflicts can be long and difficult, and this lesson is not the place to discuss negotiation skills and other talents that you (or someone) will need. In fact, you (as a data scientist) might never be directly involved in these decisions. However, you will almost certainly need to do two things:
1. Identify data science efforts where significant value conflicts could arise.
1. Provide information to the key decision-makers.

On the first point, you need to think about whether some key stakeholders are likely to have their values be significantly harmed, given the current plan for your data science effort. On the second point, you need to understand the breadth of potential impacts so that you can convey those to relevant decision-makers.

In both cases, the first step is to actually identify the key stakeholders, as well as their (relevant) values. Many times, stakeholder identification will be relatively easy, if you simply stop and think about it. Conversations with other people, ideally from different backgrounds, can also be quite helpful, as they may be able to point out additional communities that might be impacted by your data science effort.

Value identification for those stakeholders can be much trickier. You should definitely _not_ assume that you can identify others’ values simply by thinking hard about it. Almost always, you will need to do some further investigation, such as structured interviews with those stakeholders, large-scale surveys (for groups), focused co-design, or many other strategies. The most important point here is that you do not need to invent these methods yourself! People have built entire careers around designing, testing, and implementing ways to elicit and understand stakeholder values. So don’t reinvent the wheel here, but instead, collaborate with (and learn from) others with different skill sets than you. 

Having said that, what about your capstone project, which may not have someone with these skills? Your mentor should be able to provide some assistance with identifying stakeholder values, and then finding ways to address conflicts between them. Some of the capstone TAs have experience with these issues, and could also help. And Prof. David Danks is available as a resource for every capstone team, as you start to think about ethical issues. (In fact, as mentioned at the start of the lesson, you'll all need to meet with him in Quarter 2!) You do not have to figure out these issues by yourself; right now, the most important thing is to recognize that data science inevitably involves ethical decisions (even if you might wish that it didn’t!).

---

## But What About Bias, Trust, Responsibility, Explainability, ...?

As we come to the end of the lesson, you might be wondering why we haven’t talked about many of the “standard” topics in data and AI ethics. We didn’t really discuss **algorithmic bias** or **injustice**, either in the abstract or in terms of methods to fix it. We didn’t talk about what it might mean (in practice) to do data science **responsibly**. Or consider the many methods that have been developed to produce **explainable** (in some sense) models - how do we decide if/when we should use one of those?

These are all interesting and important topics. At the moment, though, the important thing is that these all presuppose that we understand the key stakeholders and their values. You simply should not be asking “how do we address algorithmic bias here?” unless you know what matters for whom (and who is relevant to this project). The proper response to algorithmic bias will depend on why the bias occurs, what we think our model _should_ do, and the relative impacts of different kinds of mistakes on different individuals or groups. That is, we need to know stakeholders and their values.

That being said, some of you might be doing capstone projects that connect with some of these concepts. If so, then you should talk with your mentor about the relevant concepts, measures, and methods, building along the way on what you know about the relevant stakeholder values.
