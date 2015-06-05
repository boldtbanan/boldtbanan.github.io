---
layout: post
title:  "Telling Stories"
comments: true
categories: [product owner, agile]
---

User stories are the backbone of agile's todo-list-driven development model. Whether you use kanban, scrum, xp, or any hybrid, user stories are the basis for communicating what you want to build to the people who will build it.

I'm not going to talk about how to write a good user story. I mean, I love talking about that, and I'm sure I'll write a long article about it someday, but for *this post* I want to take a step back and talk about at how to use them.

##What's in a story?

Most training on user stories tells you to write something like this:

**As a [user role] I can [activity] so that [business value].**

That's a powerful structure. It puts focus on your users and what they are trying to accomplish by using the feature you want to build. It narrows focus to a manageable piece of work that should be (relatively) easy to complete. And it gives you a simple foundation on which to build your spec.

But if that's all you're using them for, you're missing the forest for the trees.

##Choose your own adventure

When you build software, you don't have a blueprint to follow. Sure, you have *parts* of a blueprint: how to create a database table, how to build a file uploader, etc. But the end result, the exact combination of business rules and UX that you are pulling out of thin air, has never existed before in the history of the world!

So if you're building something that never existed, how do you get there?

If you follow waterfall methods, you spend a lot of time up front writing a spec. Then you start building, things start going off plan wrong, the spec becomes useless but everyone still tries to follow it, and the project flounders.

With agile methods, you get someone to be the voice of your users/customers. That person (the Product Owner or whatever you call him) is the spec. User stories are a tool for controlling the flow of work from his head to the dev teams so you end up with something that solves the right problem at the right time and can be accomplished with the people available.

The flow control aspect of user stories is extremely powerful. 

##Telling Stories

Writing user stories is a creative process. You're basically creating all these little vignettes and blending them together into a cohesive experience. Many techniques from creative writing apply as well.

###Story Arcs

Story arcs are a great way to identify general user experiences at the feature level. From there you can start thinking about the different pieces that go into making things happen the way you want, and identify the individual user stories to pull out. You might call these Themes or Epics, but all stories ultimately have an arc to them.

Looking at stories as an arc of events with exposition (How did I get here?), rising action (How do I do what I want?) and climax/denoument (What do I get for my efforts?) makes it easier for your team to relate to the user's experience. That means you'll have more meaningful feedback on your stories, and better engagement from the team during grooming. 

Another thing I love about story arcs is that they help you describe the context in which your users are making decisions. [Airbnb has a great example of using storyboards](https://www.sequoiacap.com/grove/posts/ezem/visualizing-the-customer-experience) (essentialy a story arc with pictures) to help visualize the "frames" of the customer experience they were trying to serve.

##Maximize the work not done

When you have a context for decisions, you start to ask different questions. Instead of "how do we build this," you start asking "is this the right thing to build." That scares some Product Owners who are used to traditional boss/worker relationships. And it scares some developers who are used to being told what to do. But a core tenet of Toyota Manufacturing, from which agile principles are gleaned, is that anyone can, *and should*, stop the assembly line if they spot a problem so it can be fixed early. That might mean solving the problem in a different way, or not solving the problem at all. Remember, you want to [maximize the amount of work not done](http://agilemanifesto.org/principles.html).

Story arcs are great for breaking work down into smaller deliverables. You define the main (usually happy-path) way you want the user to accomplish their task, and start identifying alternate routes and edge cases, which are ideal candidates for enhancement stories. Following this pattern, I always make validation rules an enhancement story because then I can get the happy path case (user enters perfect data) verified and tested and demo-able much faster. 
It's not always something I *want* to release to production, but I *can* if I decide that validation is less important than other things. Now users (testers, product owners, UX) can look at the big picture experience earlier, which leads to a better system, and more unnecessary work that doesn't need to be done in the first place.

A question I often hear from teams new to agile is "how detailed should my user stories be?" Well, at what level of detail do you want to tell people *not* to do something? A really effective way to identify what *not* to do is to create a story for it, talk about it in grooming, and say that you'll prioritize it seperately. Maybe you'll never do it. But you called it out, and now the team knows that it's on someone's radar.

##Rapid prototyping


User stories are great for rapid prototyping. 


> If I were given one hour to save the planet, I would spend 59 minutes defining the problem and 1 minute resolving it. *~ Albert Einstein*



Building software is a lot like writing a **Choose Your own Adventure** novel. You come up with 



[Magic school bus "take chances, make mistakes" quote]

What I want to talk about is what user stories are good for, and why you should spend more time on them than you do.

User stories are the main tool a Product Owner has for flow control. They are your way to decide what pieces of a system are the most important and which should be worked on first. This is hugely important when you start considering minimum viable product, and working to deliver value early. What are the tasks to add value? Do you really need validation at this time, or can you add that after you launch? Do you need to handle 5 different OAuth providers, or is one sufficient for now, and which one?  

User stories are the breadcrumb trail to minimum viable product.
Don't talk about infrastructure in the story.

##How do you manage flow?

The way you break down stories defines how much control you have over your flow. 

* Story arcs
* Iterative value
* Communicate intent, not action
* User stories are iterative

Stories are promises to have a conversation about a problem. 



##Story arcs

##Understand your audience

User stories are targeted to a user role, but you need more than that, and you need to communicate that to the team.

* Is this a checkbox feature (need it to check a box on buying requirements) for a buyer?
* Will someone run into this 10% of the time, or 100%. Will it save them 1 minute or 2 days?
* How big is the potential market? How influential are they within their organization?
* 

##It's a creative process

Play with your stories. Move them around. Break them down in different ways. Try to package the most value in the minimum amount of effort. Have an idea for how much effort it takes. That's why Product Owners need to estimate with the team, to internalize a gut feeling for how much it costs to build things.

Stories are really cheap to write. It's one sentence. Use that low cost to come up with multiple plans for implementing larger features and see which fits best. Run your ideas by the team, but come prepared.

There is no "right" answer. Take your best guess, but measure the impact and adapt to new knowledge.



Like an actor: what's my motivation



- Value of user stories to product owners

- How to write a good story?
- How to create the right slices
- How to identify all of the stories
- What stories are useful for

##Choose your own adventure

##Think backwards

Sometimes it's better to do the last step first. For example:

List of orders (with sorting, filtering, etc).
View an order
Store orders in the database
