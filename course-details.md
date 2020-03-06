[GitHub Actions](https://github.com/features/actions) is a powerful platform that empowers your team to go from code to cloud all from the comfort of your own repositories.

Over the duration of this course, approximately 1 hour, you will learn the skills needed to begin using and customizing GitHub Actions to fit your unique workflow scenarios.

## What you'll learn

In this course you will learn how to:

- Consume actions within a workflow file
- Create custom JavaScript based actions
- Publish your newly created action to the marketplace

You'll know the answers to questions like:

- What is a workflow?
- What are actions?
- What is action metadata?
- What are GitHub Actions capable of?

## What you'll build

In this course you will build three actions that each accomplish different tasks designed to demonstrate the flexibility of creating and consuming JavaScript Based Actions.

First, you will start with the traditional "Hello World!" program which will teach you where to find the output of a workflow run. You will then modify this "Hello World!" action to accept `input` parameters which allow the action to be more dynamic. 

Second, you will write an action that call upon an external API to retrieve a fact about cats and prints it to the workflows output. You will then modify this cat fact action to set the retrieved data as `output` for another action in the workflow to consume.

Lastly, you will write a third action that will open an issue in your repository making the cat fact available to everyone. You will learn how to use the `output` of previous actions as `input` for current actions in this step.

## Prerequisites

We will be using Node.js to build our action and GitHub to consume our action. This presents us with a hybrid environment, the Node.js runtime environment and the virtual machine used by GitHub Actions, that you may not be used to if you've taken other Learning Lab courses.

Before we can get started there are a few things you need to setup on your **local machine**

- Install [Node.js](https://nodejs.org/en/) for your operating system.
- Ensure you have a text editor installed. I'll be using Visual Studio Code, and although you are free to use your editor of choice.
  - [Visual Studio Code](https://code.visualstudio.com/) (**recommended**)
  - [Atom](https://atom.io/)
  - [Sublime Text](https://www.sublimetext.com/)
- Lastly, you're going to need a local installation of [Git](https://git-scm.com/) so that you can interact with this repository as you write code.

It is also worth noting that this course is one of many in a GitHub Actions Learning Path. It is recommended that you complete this learning path in order to get the most out of your Learning Lab experience.

## Projects used

- [GitHub Actions Toolkit](https://github.com/actions/toolkit), a multipurpose JavaScript library for writing actions
- [JavaScript](https://www.javascript.com/), JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions.
- [Node.js](https://nodejs.org/en/), Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.

## Audience

Developers, DevOps Engineers, students, teams
