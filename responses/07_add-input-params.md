## Using input parameters

Earlier I asked you to install the `@actions/core` package using `npm`. We did this so that we can expand our action to make it more flexible.

A "Hello World" message is great, but let's personalize it a little bit. We will do this by adding an **input** parameter to the `action.yml` and `main.js` files.

Although this example may seem a little lightweight input parameters have a very flexible use case. Consider a scenario where you need to access secret API key with your action, or when you need to specify the path to a given file. Inputs allows for these problems to be easily solved.

#### A quick example

To add inputs we need to add the `inputs:` parameter to the `action.yml` file. The `inputs:` parameter has a few parameters of its own.

| Parameter      | Description                                                        | Required                      |
| -------------- | ------------------------------------------------------------------ | ----------------------------- |
| `description:` | String describing the purpose of the input                         | True                          |
| `required:`    | Boolean value indicating if the input parameter is required or not | False (Default value is True) |
| `default:`     | String representing a default value for the input parameter        | False                         |

Let's take a look at how this fits into an `action.yml` file.

**action.yml**

```yaml
name: "my hello action"

description: "say hello with actions"

inputs:
  first-greeting:
    description: "who would you like to greet in the console"
    required: true
    default: "Hubot"

  second-greeting:
    description: "another person to greet"
    required: true
    default: "Mona the Octocat"

  third-greeting:
    description: "a third greeting"
    required: false
```

_The placement of your `inputs:` is not strictly enforced, however it has become commonplace to ensure the `runs:` statement is defined after your `inputs:` and `outputs:` in your `action.yml` file._

## So what is actually happening here?

Well, in the `my-workflow.yml` file we could specify values for inputs we just created:

- first-greeting
- second-greeting
- third-greeting

Or we could leave them out and rely on their default values.

The example below demonstrates a mix of both:

**my-workflow.yml**

```yaml
name: "JS Actions"

on: [push]

jobs:
  action:
    runs-on: "ubuntu-latest"
    steps:
      - uses: actions/checkout@v1

      - name: "hello-action"
        uses: ./.github/actions/hello-world
        with:
          first-greeting: "Learning Lab User"
```

Now that there are inputs in the action's metadata we can use the `@actions/core` package to handle them within our `main.js` file.

**main.js**

```javascript
const core = require("@actions/core");

const firstGreeting = core.getInput("first-greeting"):
const secondGreeting = core.getInput("second-greeting");
const thirdGreeting = core.getInput("third-greeting");

console.log(`Hello ${firstGreeting}`);
console.log(`Hello ${secondGreeting}`);
if (thirdGreeting) {
    console.log(`Hello ${thirdGreeting}`);
};
```

By using `core.getInput()` we can specify the string of any input parameter we have placed inside of the `action.yml` file.

The `@actions/core` package brings a few more methods along with it to help us interact with the GitHub Actions platform. If writing actions is something you plan to continue doing it's work reading the [documentation](https://github.com/actions/toolkit/tree/master/packages/core) about this package.

---

📖Read more about the [input parameter](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/metadata-syntax-for-github-actions#inputs)
