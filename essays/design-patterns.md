---
layout: essay
type: essay
title: Connecting theory to practice
# All dates must be YYYY-MM-DD format!
date: 2022-04-28
labels:
  - Design Patterns
  - Software Engineering
---

## Learning while doing

My first two posts illustrated my personal path from writing my [first line of code](./engineers-path-to-js.md), to working as a [fullstack engineer](./software-engineering.md) on production systems in a small company. In one of my jobs at the University of Hawaii during my undergraduate studies, sometime around 2015-16, I was asked to develop a concept for developing a web application for the UH Faculty Senate election system. Only having had used WordPress for Web Applications up until that time, my colleague and I set out to look for some cool framework to use. We happened to come across the Phoenix Framework and were intrigued by its claims of fault tolerance and the concurrency that the Erlang VM brings to Elixir, we chose it for the concept and proposal. Not knowing much about web application development, and never having heard of "design patterns", I perceived MVC to be a key feature of the Phoenix Framework and listed it as a selling point without realizing how commonly it is used. I eventually set out to learn the Elixir language and developed my first web applications with the Phoenix framework, the [HICSS system](../projects/hicss-cms.md). It however took many more years and learning experiences with other frameworks to realize how commonly MVC is used in web application development.

## Ubiquituous patterns

This example shows that some design patterns, such as MVC, are just too commonly used to not come across them when learning web application development. The question is however: does one have the technical and theoretical background to identify and name patterns, or, like in my case, does one just uses it without question/understanding the pros and cons of said design pattern? A lot of personal examples fall into the latter category, which makes it very enjoyable to now link theoretical concepts to some of my personal experiences from the last years. Coming from a practical background, I would like to see more graduate level coursework on these software engineering concepts, like design pattern, either in a course like ICS 613, or its own dedicated course.

Another good example for connecting theory to practice is the Observer design pattern, and more specifically, the PubSub pattern. I've used this design pattern extensively hands-on; that is, I used the MQTT protocol for [IoT application development](../projects/iot-application-development.md). Similarly to before, I used this pattern in my work and projects long before knowing what an Observer design pattern is. Having used the design patterns frequently made it easier to grasp the concept. In fact, learning about the Observer pattern reminded me of an ongoing project of mine, in which we'll eventually have to implement the Observer pattern to meet the requirement of notifying external services on a platform when some user data changes.
