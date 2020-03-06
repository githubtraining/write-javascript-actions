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

![screenshot of a pull request in the course with instructions on how to fetch a joke from the API, a second screenshot of a workflow running and outputting the joke: "Guy told me today he did not know what cloning is. I told him, that makes 2 of us."](https://user-images.githubusercontent.com/16547949/76105870-cce3a380-5fa3-11ea-8882-7138319b4100.png)

In this course you will build three actions that each accomplish different tasks designed to demonstrate the flexibility of creating and consuming JavaScript Based Actions.

First, you will start with the traditional "Hello World!" program which will teach you where to find the output of a workflow run. You will then modify this "Hello World!" action to accept `input` parameters which allow the action to be more dynamic. 

Second, you will write an action that call upon an external API to retrieve a fact about cats and prints it to the workflows output. You will then modify this cat fact action to set the retrieved data as `output` for another action in the workflow to consume.

Lastly, you will write a third action that will open an issue in your repository making the cat fact available to everyone. You will learn how to use the `output` of previous actions as `input` for current actions in this step.

## Prerequisites

We first recommend taking the following courses:
- [Hello, GitHub Actions!](https://lab.github.com/github/hello-github-actions!) to learn the basics of how GitHub Actions work
- [GitHub Actions: Continuous Integration](https://lab.github.com/githubtraining/github-actions:-continuous-integration) to dive deeper into a workflow file

## Projects used

This makes use of the following open source projects. Consider exploring these repos and maybe even making contributions!

- [GitHub Actions Toolkit](https://github.com/actions/toolkit), a multipurpose JavaScript library for writing actions

## Audience

Developers, DevOps Engineers, students, teams
