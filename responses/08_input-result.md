## Take a 👀 at what you made!

Great Job 👍 making those changes @{{user.login}}.  I will take just a moment to walk you through what happened.

If you look at the screenshot below you will see a very similar output to what your results should show.  If you'd like you can open your own [Actions tab]({{actionsUrl}}) to follow along.


![results from using input](https://i.imgur.com/QFKqDb2.png)


Your Action now says hello to **Learning Lab User** which was the specified value for the `first-greeting` input parameter which was added to the `my-workflow.yml` file.

What's interesting though, is that we also see **Mona the Octocat** and if you recall that is the value of the `second-greeting` parameter in the `action.yml` file.

Why do we see the value of the `second-greeting` 🤔

If you remember, we made the `second-greeting` input parameter **required**.  This means that even if it is not specified in `my-workflow.yml` it will be executed by the `main.js` code using whatever value was set as **default**.  It cannot be ignored like our `third-greeting` was.

Circling back to the `fist-greeting` you may have noticed that you were able to overwrite the **default** value of `Hubot` by being explicit in the `my-workflow.yml` file.

Had you been explicit with `third-greeting` in the `my-workflow.yml` file then the `if` statement in the `main.js` file would have executed and you would have three inputs.
