## Create and edit the third actions action.yml file

Like our "hello world" action, this action will require at least one `input:` parameter. We need this parameter so that our JavaScript for this action has access to the `output:` from the joke action.

If you recall, in the `my-workflow.yml` file, we stated this action would take a specific input named `joke:` and we set it's value to the output of the previous action.

```yaml
- name: create-issue
  uses: ./.github/actions/issue-maker
  with:
    joke: {% raw %}${{steps.jokes.outputs.joke-output}}{% endraw %}
```

Because of this, we need to define `joke:` as one of our `inputs:` for this action. Remember when we did this with the first action? It looked a little like this:

```yaml
inputs:
  first-greeting:
    description: who you would like to greet in the console
    required: true
    default: Hubot
```

Now, we will do something similar so that our action matches what our workflow expects.

### :keyboard: Activity: Create the final metadata file

💡All of the following steps take place inside of the `.github/actions/issue-maker` directory.

We will use the `joke-output`, as well as an issue title, in in this portion of the course so we need to accept `inputs:` for our action.

1. Create a file named `action.yml` with the following contents:
    ```yaml
    name: "I have issues"

    description: "consume the output of the previous action and create a new issue in the repository"

    inputs:
      joke:
        description: "This will become the body of the created issue"
      issue-title:
        description: "Every issue needs a title, it's nice to supply one, even though you could do this dynamically within your code"
        default: "a joke for you"
        required: true

    runs:
      using: "node12"
      main: "index.js"
    ```
2. Save the `action.yml` file
3. Commit the changes and push them to GitHub:
   ```shell
   git add action.yml
   git commit -m 'create action.yml'
   git push
   ```



---

I will respond when you commit to this branch.
