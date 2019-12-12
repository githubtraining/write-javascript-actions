## Files? 🤔

Yes... files... plural. As you probably know, in JavaScript and other programming languages it is common to break your code into modules so that it is easier to read and maintain going forward. Since JavaScript Actions are just programs written in JavaScript that run based on a specific trigger we are able to make our Action code modular as well.

To do so we will create two files. One of them will contain the logic to reach out to an external API and retrieve a joke for us, the other will call that module and print the joke to the Actions console for us. We will be extending this functionality in our third and final Action.

**Joke API**

The first file will be `joke.js` and it will fetch our joke for us. We will be using the [icanhazdadjoke API](https://icanhazdadjoke.com/api) for our Action. This API does not require any authentication, but it does however that we set a few parameters in the [HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers). I'll point out what those are when we get to the code, however it is outside of the scope of this course to cover HTTP in any depth.

When we make our request to this API we will get back a JSON Object in the response. That Object looks like this:

```
{
  id: '0LuXvkq4Muc',
  joke: "I knew I shouldn't steal a mixer from work, but it was a whisk I was willing to take.",
  status: 200
}
```

It contains 3 key:value pairs of data that we can use in our own program or service. In our case, we are only interested in the `joke` field.

**Joke Module**

We will create a file named `joke.js` and it will reside in the `.github/action/joke-action` directory.

The joke module will look like this:

![screenshot of joke.js file](https://i.imgur.com/GklnbKN.png)

We first bring in the `request-promise` library that we installed earlier using `npm`.

Next we define a set of `options` that the `request-promise` library will use when it makes the request.

📖Read more about [request-promise](https://github.com/request/request-promise/blob/master/README.md)

Inside of the `options` block we add a key named `headers`. This defines the HTTP headers that the **icanhazdadjoke** API expects in each request that comes it's way.

**icanhazdadjoke** cares the most about the keys, **Accept** and **User-Agent**, so we need to make sure we fill them in.

Next we define an **asynchronous JavaScript function** to make the request for us, storing the JSON Object that is returned in a variable named `res`.

Lastly, we `return` the `res.joke` which is only the value associated with the `joke` key of the JSON Object. This value will be random every time our Action runs because of how we are interacting with the **icanhazdadjoke** API.

This file finishes up by exporting the newly created function so that we can use it in our `main.js` file.

**Main Module**

We will also create a file named `main.js` that resides inside of the `.github/actions/joke-action` directory.

That file will look like this:

![screenshot of main.js file](https://i.imgur.com/oo7WkvE.png)

Like we did in the `joke.js` file, we are first going to bring in our dependencies. Only this time, our dependencies include something we wrote! To do that we simply use `require()` to point to the location of the file we wish to bring in.

We also bring in `@actions/core` so that we can set the output of our Action.

Next we write another **asynchronous JavaScript function** that stores the return value of `getJoke()` in a variable called **joke**.

Then we log the joke to the console.

Finally we finish the function with by setting the contents of the joke as the value of the `joke-output` output parameter. We will use this output later in the course.

Don't forget to call the `run()` function.

### :keyboard: Creating the javascript files for your new Action.

1. Add the following contents to the `.github/actions/joke-action/joke.js` file:

   ```javascript
   const request = require("request-promise");

   const options = {
     method: "GET",
     uri: "https://icanhazdadjoke.com/",
     headers: {
       Accept: "application/json",
       "User-Agent":
         "Writing JavaScript Action GitHub Learning Lab course.  Visit lab.github.com or to contact us."
     },
     json: true
   };

   async function getJoke() {
     const res = await request(options);
     return res;
   }

   module.exports = getJoke;
   ```

2. Save the `joke.js` file.
3. Add the following contents to the `.github/actions/joke-action/main.js` file:

   ```javascript
   const getJoke = require("./joke");
   const core = require("@actions/core)

   async function run() {
     const joke = await getJoke();
     console.log(joke);
     core.setOutput("joke-output", joke)
   }

   run();
   ```

4. Save the `main.js` file.
5. Commit the changes to the `action-two` branch:
   `git add .`
   `git commit -m 'creating joke.js and main.js'`
6. Push the changes to your repository:
   `git push`

---

I'll respond in this pull request when you have completed these tasks.
