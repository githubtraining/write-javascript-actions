## Using input parameters

Earlier I asked you to install the `@actions/core` package using `npm`.  We did this so that we can expand our Action to make it more flexible.

A "Hello World" message is great, but let's personalize it a little bit.  We will do this by adding an **input** parameter to the `action.yml` and `main.js` files.

Although this example may seem a little lightweight input parameters have a very flexible use case.  Consider a scenario where you need to access secret API key with your Action, or when you need to specify the path to a given file.  Inputs allows for these problems to be easily solved.

#### A quick example

To add inputs we need to add the `inputs:` parameter to the `action.yml` file.  The `inputs:` parameter has a few parameters of its own.  Let's look at those before seeing how it fits into the `action.yml` file.

**input parameter**

The structure of an input looks like this

![input parameter screenshot](https://i.imgur.com/qgtZL6x.png)


The above examples shows that we can have more than one input for our Action, as well as drop any optional parameters we may not need, such as setting a `default:` value for the input parameter.

Let's take a look at how this fits into an `action.yml` file.

**action.yml**
![action.yml with input parameters](https://i.imgur.com/dRzUFS0.png)

The placement of your `inputs:` is not strictly enforced, however it has become commonplace to ensure the `runs:` statement is defined after your `inputs:` and `outputs:` in your `action.yml` file.

For our case, adding `inputs:` directly after the `description:` will work just fine 😄

So what is actually happening here?  Well, in the `my-workflow.yml` file we could specify values for inputs named:

- first-greeting
- second-greeting
- third-greeting

Or we could leave them out and rely on their default values.  The example below demonstrates a mix of both:

**my-workflow.yml**
![workflow file example](https://i.imgur.com/d8iWVHa.png)

And in our `main.js` file we would need to account for the inputs that are now a part of the Actions metadata.

![](https://i.imgur.com/IF7w5th.png)

By using `getInput()` we can specify the string of any input parameter we have placed inside of the `action.yml` file.

The `@actions/core` package brings a few more methods along with it to help us interact with the Actions platform.  If writing Actions is something you plan to continue doing it's work reading the [documentation](https://github.com/actions/toolkit/tree/master/packages/core) about this package.

---

📖Read more about the [input parameter](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/metadata-syntax-for-github-actions#inputs)