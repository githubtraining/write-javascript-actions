## Who's there?

GitHub Actions... thats who!

The next action we write is going to reach out to an external API and fetch data for consumption. Although your action is bound to a step, which is bound to a workflow within your repository it is NOT bound to an isolated network. This means that we can leverage APIs from our favorite cloud providers, favorite pizza shops, social media or whatever API our developers need.

### What is an API

If you ask this question to anyone in the industry you'll likely get the obvious answer of "Application Programming Interface", which although true, doesn't exactly explain what one **is** or **does**.

Let's do a thought experiment to help understand the concept of an API.

I think most people are familiar with a 🚗 either through personal experience or some form of media. I also think it's safe to say that most people understand the concepts behind driving a car. By examining how we drive a car we can understand how APIs work in a fun way.

**Car Components**
When driving a car there are a few components of the car that the driver interacts with directly. This wont be an all inclusive list, and each car varies to some degree, but so does each API. We will use the following components for our example:

- Gas pedal
- Brake pedal
- Steering wheel
- Gear shift

As the driver of the car when we push one of the pedals, move the gear shift position or turn the steering wheel the car responds. Most of us don't know **exactly** how it responds though. We actually don't even think about the system that is in place to amplify the force applied to the steering wheel when we make a turn. We probably don't know if our vehicle has a hydraulic, electro-hydraulic or fully electric power steering system. What we do know is that when we turn the steering wheel the car responds by turning.

The steering wheel has become an API between the driver and the inner workings of the power steering system and the systems that it communicates with. You see, steering the car eventually turns the wheels of the car and that takes place through further interconnected systems that are abstracted away from the driver.

The same is true with the gear shift. When we move our car into a different state using the gear shift a series of events take place throughout the car to reflect that change. This could be going from a stopped position to driving forward. It could be going from forward motion to reverse. It could even be cycling through gears in the case of a manual transmission. Ultimately, by moving the gear shift we tell the car what to do when we apply the gas pedal.

Very simply the gas pedal changes the speed of our car. We press it down to go faster or lift pressure off of it to stop going faster. What about if we want to fully stop? The gas pedal, gear shift and steering wheel wont exactly help us do that, hence the need for a brake pedal.

All of these systems, these APIs designed to help a human drive a car, are constantly communicating with one another to produce a moving vehicle. The driver didn't have to concern themselves with the implementation, platform, architecture, complex queries or manufacturer differences of each car. No, the driver just needed to concern themselves with how a steering wheel, gas pedal, brake pedal and gear shift work.

What gets even better is that the API for a car is pretty standard from one car to the next. Once you learn one steering wheel you pretty much know them all!

**Standard API Types:**

This concept is also prevalent in real world APIs. There are many **standard** types of APIs and if you understand each standard then you ultimately understand how to use that API to your advantage.

The most common types of API at the time this course was written are:

- REST
- SOAP
- XML-RPC
- JSON-RPC

Going into detail about each standard is beyond the scope of this course, however it's important to understand that there are many standards out there. Although there are many standards the purpose of each API is to give your program or service the ability to communicate easily with another program or service without the need to know the implementation details.

APIs also give you, the developer, the ability to give others access to specific functionality or resources within your own program or service.

### What about our action?

We are now going to write an action that reaches out to a service through its API to get us a random joke. We will then display that joke on the [Actions tab]({{actionsUrl}}).

For our purposes the API we use will not require authentication, however that is a limitation of the course content and not the GitHub Actions platform. If you need to store secrets, like API keys, for your workflow to use you will need to configure [secrets](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets) as inputs.

We are also going to demonstrate having multiple files make up an action as well as importing other external libraries for your action to use.

What are we waiting for, let's get started 😉
