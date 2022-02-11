---
layout: essay
type: essay
title: When "Clever" is an Accusation.
# All dates must be YYYY-MM-DD format!
date: 2022-02-08
labels:
  - Software Engineering
  - Tech Talks
---

## Software Engineering at Google

In the ACM talk ["Software Engineering at Google"](https://event.on24.com/wcc/r/3575531/4C344A986E282927530C2ADB81F1F8CC?partnerref=vip), presenter Titus Winters and moderator Hyrum Wright pitch their book [Software Engineering at Google: Lessons Learned](https://www.amazon.com/Software-Engineering-Google-Lessons-Programming/dp/1492082791). In said book, authors Winters, Manshrek, and Wright present the concepts of time, scale, and tradeoff that they've identified to be integral to increasing software engineering productivity at Google. 

## "Software Engineering is Programming Integrated Over Time"
Winters motivates his talk by establishing that in software engineering–defined as "the Multi-Person Construction of Multi-Version Programs"–there is no one single practice that can provide a productivity gain of 10x and that as a result, teams should look for a variety of guiding principles to improve productivity. 

The life expectancy of code is relevant as it provides context for what differentiates programming from software engineering. Time separates the novice programmer, whose programs have a short code life expectancy, from startups with an expectancy of a few years, and software engineering projects that last from multiple years to decades (e.g. Linux). The time component of long-term engineering projects thus brings its challenges:
- fewer qualified engineers with the needed expertise and commitment to stay on the project for a long time;
- higher onboarding costs to develop expertise;
- software updates that affect many people down the line;
- a multiplicative difficulty of maintaining the system without affecting functionality that users depend on, establishing policies and experience, avoiding larger than usual updates. 

I found the authors categorization into programming and software quite fascinating as I hadn't thought of it like this before. As my personal projects don't count as software engineering due the lack of "multiple people", I can say that I've only reallt worked on one software engineering project at a startup with a code life expectancy around the 3-5 year mark. On that project, decisions had to be constantly made in anticipation of current and future requirements; that is, a) do we prioritize existing customers requests for custom functionality, or do we generalize to a product that works for many customers down the line, or b) can we update an API endpoint without affecting a partner that may rely on that functionality. 

## "Resources Should Never Scale Super-linearly"
Winters makes a clear point, that as a project grows, ideally super-linearly, the project resources, e.g. build time or human resources, should ideally scale sub-linearly. He illustrated this with the examples of code deprecations and trunk-based development. In the latter example, he described his experience on a team where feature-based branching schemes required frequent merge meetings and even designated engineers to plan merges.

From my own experience, I fully agree with the presenter's recommendation for trunk-based development. I've made mistakes on personal projects where I let feature branches drift from the master branch and then had problems down the line in the merge process. I've experienced working in a team that employed trunk-based development with atomic commits. It made code review and commit merges more pleasant for the team. 

I further appreciated the elaborate explanations on the shortcomings of existing deprecation schemes. I'm most familiar with the scheme of implementing a new version and marking the existing one as deprecated. While this has been a convenient method in development for me, I can understand the presenter's arguments on how this can cause issues when integrated over time. However, the alternative approach of putting the bulk of the work on the team implementing the update, not the users, didn't really go into specifics on what that would look like. Therofore, I didn't fully understand if the suggested approach implied that the customer-facing interfaces would remain the same or be upadted under such an approach.

## Evidence-Based Decision Making 

The last concept was described more briefly than the prior two. My main takeaway from it was that one should always evaluate possible options and make evidence-based decisions. Winters points out that "because person X said so" is never a good enough reason in the decision-making process and that as situations evolve, one can and should always reevaluate based on the current status quo.

I fully agree with the presenter's point of view. From an outsiders perspective, I would have appreciated more specific examples of what type of "evidence" is used at Google in the decision making process and how that process takes place. That is, how many people are involved and what types of data are being looked. Given the brevity and scope of the talk, I however understand that the presenter is referring to the book for details.

Overall, the talk presented some very interesting principles that need to be considered in software engineering projects. It presented many interesting definitions and criteria that one can use to differentiate between software engineering and plain programming. The best definition was given as a closing remark and having watched the, I believe to understand what the is pointing at with this definition:

> It's programming if "clever" is a compliment. 
> 
> It's software engineering if "clever" is an accusation. 

