---
layout: essay
type: essay
title: Developing Opinions, not Convictions!
# All dates must be YYYY-MM-DD format!
date: 2022-05-13
labels:
  - Software Engineering
  - Functional Programming
  - Design Patterns
---

Over the course of the semester, we've explored topics and concepts in software engineering in a breadth-first manner so that we got to experience many import aspect of software engineering. We've been asked to share our opinions via essays on a few of these topics, such as [UI frameworks](./ui-frameworks.md), [Coding Standards](./eslint-reflection.md), and [Design Patterns](./design-patterns.md), and gained hands-on experience by getting a glimpse at one tech stack for web application development (Meteor/ReactJS/Semantic-UI/MongoDB). 

My two big takeaways from this semester are that **functions are first class objects** in JS and that JS relies on **prototypal inheritance**. The following discusses these concepts more generally in the context of functional programming and design patterns.   

## Functional Programming

As described in my [first essay](./engineers-path-to-js.md), I greatly enjoy working with functional programming languages and have thus enjoyed working with JS this semester. In JS, functions are first class, which means that functions can be assigned to variables, passed as function arguments, and returned from a function. Developing with ReactJS this semester, I've greatly enjoyed and made heavy use of these three properties.

The following code is taken from the Messenger page from the final project that I was involved with. (See [this project](../projects/akamy-rent.md) for an animated overview of the Messenger and my contributions to the project.) The Messenger page consists of components in a two column grid, a list of groups in the left column from which one can select the active group, and a message display in the right grid for the currently selected grid. The Messenger page therefore needs to keep track of the currently selected group, pass this to its downstream components, and provide the downstream components in the left column a method for updating the group selection. Two react hooks are used to achieve these requirements and looking at the code example nicely illustrates the properties of functions as first class objects.
```js
// State to track selected group for displaying messages
const [group, setGroup] = useState();
const handleSetGroup = useCallback((groupSelection) => {
setGroup(groupSelection);
}, [group]);
```
The code shows the use of two React hooks, `useState` and `useCallback`. `useState()` is a function that returns the initial state passed to it, in this case `null`, and a function that allows us to update the state. So `group` is initialized here to `null` and the variable `setGroup` is assigned a function that allows us to update the `group` state. 
`useCallback` is another great example, because it demonstrates how we can pass a function and a dependency list as arguments to the `useCallback` function and then get a memoized function back that can be assigned to a variable, like the `handleSetGroup` variable. We can utilize this `handleSetGroup` function variable to pass it down to components such so that they can trigger events that would update the state in the parent component. The following code shows how `handleSetGroup` is passed down to the ChatFeed component, i.e. the group list in the left column. 
```js
<Grid.Column width={4} >
  <ChatFeed setGroupFn={handleSetGroup} groups={groups} groupid={group?._id} />
</Grid.Column>
```

Working with React Hooks is a lot of fun and motivated me to mostly rely on function declarations instead of class declarations for React components. To me, this approach makes the code more compact, easier to read, and more fun to write as it encourages me to think in functions and not in classes. 

## Design Patterns

The prototype design pattern and prototypal inheritance were emphasized in this semester. In contrast to the "cookie cutter" concept of classes in object-oriented languages like Java, prototypal inheritance is analogous to the concept of mitosis where cells divide and then evolve on their own. Not having the formal education and theoretical background in CS, I appreciated the introduction to design patterns like that of prototypes in JS, and other patterns like the MVC and Observer patterns that I explored in more detail in my [Design Pattern essay](./design-patterns.md).

From a graduate course, I personally would have preferred more in-class discussions on these software engineering concepts, rather than doing numerous individual in-class practice activities. Team discussions and clear communication of complex topics are a big part of a software engineers daily tasks, and I didn't see this skill sufficiently practices in this course. To add, coming from a more hands-on background, such discussions in a small course would have helped me to fill some of the theoretical knowledge gaps; it could also helps those considering to move on to a Ph.D. prepare for their comprehensive exam. Therefore, while hands-on is always fun and easy to do, some more discussions/lectures on design patterns and software engineering could be a great contribution to the ICS 613 curriculum.

## Developing Opinions, not Convictions!

Through the technical writing and hands-on learning experiences, we've been given the opportunity to form opinions on various software engineering principles and tools. While some may argue that it's "bad" to be opinionated, I believe that one should appreciate opinions because they indicate that one has spent enough time on a topic to even form an opinion. As always, one ought to be careful to not get stuck in one's opinions and to remain open to new concepts and ideas in an ever-evolving industry. Otherwise it becomes increasingly difficult to work in diverse teams where openness, a healthy discourse, and compromise are key to working together productively. 
