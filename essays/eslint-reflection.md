---
layout: essay
type: essay
title: No Excuses - Use ESLint!
# All dates must be YYYY-MM-DD format!
date: 2022-02-10
labels:
  - Software Engineering
  - Quality Assurance
---

## No Excuses for Not Using a Linter

I have used ESLint in both individual and team projects that were Typescript-based. I generally use it in a more passive way in that I don't highlight linting errors during development in the VSC editor; instead, I either run the linter manually before committing changes, or as a pre-commit hook to avoid failing build pipelines. In addition, I oftentimes use `prettier`, or ESLint with the `--fix` parameter to automatically fix all issues that can be fixed by a "machine". This way I still get the benefit of learning from more significant linting issues that require "human" attention. So far, I've found this process very pleasant. During development I'm not getting distracting by formatting issues and once I'm done with the bulk of development, I am "enforced" to inspect any linting issues prior to the commit.

Having used ESLint in the IntelliJ IDEA over the past week has been an interesting experience. I've honestly found it distracting to have all linting issues highlighted as errors. More specifically, I've gotten used to the `semi: ['error', 'never']` rule for example, so I've received lots of errors this week for leaving out semi colons with the default `eslint-config-airbnb` rules. I will need to look more into the various configuration options in IntelliJ IDEA to make linting error highlighting less obtrusive. While I do think it's important for programmers to care about readability and aesthetics of their code; they should not feel interrupted by it or waste their time on correcting for syntactic errors. These can and should be fixed by machines.

Irrespective of the many ways that ESLint can be added and used in various IDEs, I strongly believe that ESLint should be part of any Javascript/Typescript project. At minimum, one gets free and consistent code formatting without having to do any additional work. At best, one benefits from many productivity gains through automatic enforcement of coding standards that go beyond simple formatting. For example, I've found that `no-explicit-any`, in the case of TS, has forced me to be more considerate in using the `any` type. In a project where we have a class for logging error and info in a specific format, the `no-console` rule has been very useful to make sure that no developer debug statements leak into the source code. (I've had to correct this error quite a bit on that project.)

## Are Coding Standards the Most Important Software Engineering Technique?

I'm not sure what constitutes a software engineering technique and where the difference lies between a software engineering technique and just a common workflow practice. While I strongly feel that using ESLint should be a default configuration step of any JS/TS project, I'm not sure if I would agree that it's the most important one.

ESLint provides the option to disable rules for lines or sections of code. This means that without enforcement of the 4-eye principle, i.e. Code Review, a team member may circumvent ESLint rules to cut corners. While disabling rules is a necessity in certain situations depending on how strict the rules are laid out, the option to do so should not be abused. That said, in multi-person and multi-verion software engineering projects (see [Software Engineering at Google Talk](swe-at-google.md)), I wouldn't want to edit or review unformatted and inconsistent code. So a linter like ESLint is really a basic prerequisite for productive work environments and there is no good reason not to implement and enforce coding standards.
