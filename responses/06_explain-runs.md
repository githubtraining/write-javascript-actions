## Runs

As you have learned `runs:` defines the command necessary to execute your action.

In our current case `runs:` takes 2 arguments

- `using:`
- `main:`

These are specific to JavaScript actions.  It is our way of telling the runner to run the `main.js` file using `node12`

This is no different than running a local JavaScript file using Node like you see below:
![node example](https://media.giphy.com/media/W1kCFFsaoYlsmpVtxv/giphy.gif)

Which means that the value of `main:` would be different if your file was not named `main.js`.  
![different filename example](https://media.giphy.com/media/H7CCHqH06pVbQeWmlb/giphy.gif)
In this scenario our metadata block would look like this:
```yaml
runs:
  using: 'node12'
  main: 'bread.js'
```

#### From our workflows perspective

This execution is visible from within your workflow.  To save time I have included a screenshot of what your workflow currently looks like.  As always, you can follow along in the [Actions tab]({{actionUrl}}).

![A look into the failed run](https://i.imgur.com/nJtqEct.png)

Look 👀, now we have a new error!  We are totally making progress here!  What we can reason from this output is that our `action.yml` file was found and read.  Since we defined the `main:` parameter to point to a file named `main.js` the workflow looked for that file in the root of the `hello-world` directory, but since it couldn't find it the workflow fails.

Let's fix this next!

---

Keep this in mind because later we will be referencing a file that is not in the same directory of the `action.yml`