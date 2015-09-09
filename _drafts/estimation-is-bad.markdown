---
layout: post
title:  "Estimation is harmful"
comments: true
categories: [product management, estimation, risk]
---

Nobody sets out to fail. Nobody approaches a project with the intent to miss the deadline by 6 months, cost double what was expected and only deliver half of the features they planned at the start. How can our estimates be so bad that a significant percentage of projects fail?

##What is an estimate?

Fundamentally, an estimate is a guess as to how much time/effort/money it takes to do something. At it's best, it's an *educated* guess as to how much time/effort/money it takes to do something. 

Let's start with something simple:

##Flipping coins

If you have a fair coin and you flip it, there is a 50% chance it will come up heads, and a 50% chance that it will come up tails. If you flip it 10 times, you will see somewhere between 0 and 10 heads. How likely you are to see a certain number can be represented by a probability distribution.

**[Insert probability distribution]**

Now, if I ask you to estimate how many heads you will see before you ever flip the coin, what would you say? Five seems like a pretty good answer. It's definitely the most common result and works pretty intuitively…if I have a 50% chance of getting a result, I'd expect to see .5 * 10 = 5 heads for a given sample. 

Now let's take a look at another chart that represents the percent of total results.

**[Insert cumulative distribution]**

If you draw a line at 5 heads and include everything below that (0 through 4 heads), you have about 60% of the cases covered, but that still leaves 40% of the cases where you will see more heads than you estimated. I think you see where I'm going here.

But building software isn't random, right? It's a controlled process with intelligent people working toward a known goal.

For the sake of argument, let's say that I agree with that. You will still have things that pop up and cause delays: sick days, production issues that distract devs from the current feature, changing priorities, hard drive crashes, etc. 

**[Insert sum of random things]**

Those delays won't happen every time, and they won't happen the same way, and that adds a random delay to your perfect system. When you start looking at all the things that can affect the core development (e.g.: bugs in the first version, deciding that the UI is too confusing and needs rework), the process of building software starts to look like a chaotic mess, and that's just for one task.

##All estimates are not created equal

Estimating development tasks obscures the inherent risk in the system. It reduces that probability distribution to a single number and it's not clear what number to pick.

On top of that, distributions come in many forms, and can have dramatically different effects on your deliverable.

**[Narrow peaked distribution]**

Estimates are pretty good for tasks with a narrow distribution. There is a lot of work like this: setting up a new machine. Adding simple data to a database.

**[Broad peaked distribution]**

Simple tasks with a 

**[Bimodal distribution]**

Sometimes you have a case where you have a decent idea of how long something will take if everything goes well, but there is a significant chance that one issue will fire and that will add days or weeks to the original task.

##Central Limit Theorem to the rescue!

Those of you versed in statistics might be thinking, "what about the Central Limit Theorem!" 

For the rest of you, the [Central Limit Theorem](https://en.wikipedia.org/wiki/Central_limit_theorem) says that if you take a bunch of independent probability distributions and sample them, the sum of the results will have a roughly normal distribution (bell curve) based around the sum of the means of the component distributions. There are a bunch of caveats around to that, but if you throw in a few corrolaries to the base theorem, it applies reasonably well to software estimation. 

Another nice aspect of the Central Limit Theorem is that as the number of samples you take gets larger, the variance of the resulting distribution gets smaller. In other words, if you take 100 samples, their sum will probably be closer to the expected value (as a percentage) than if you only took 10. 

That brilliant little concept forms the mathematical basis for most project management estimation techniques. When you break the work down into smaller tasks, and estimate each of those, you have more sampling points, and each point has a narrower distribution (i.e. it's more predictable), so your overall estimate should be more predictable. And it really works in a lot of cases, particularly if you have a lot of repeatable, well established tasks like CRUD operations, simple forms, config changes…stuff like that.

But not all estimation errors are created equal.

##How wrong can you be? - Long tails

I hope by now I've managed to convince you that the time it takes to complete a task can be represented by a probability distribution. An estimate is just an attempt to condense that distribution into a single number that you can use to plan. But how wrong can you be?

On the low end, you can't take less than zero time to complete the task. So if your estimate is 3 days, the earliest you can be done is 3 days early. 

Conversely, there is no limit to how wrong you can be on the high end. Sure, the probability of a task taking infinitely long is zero (unless you're estimating impossibile tasks, in which case, I feel sorry for your team). 

That doesn't really matter much if you're estimating how many defects you'll have in a batch of 10 million plastic toys. But when you're trying to coordinate multiple team schedules on a software project, it turns out to be a really big deal. Now that single delay can cascade across teams, snowballing into a much bigger delay something much bigger, because *estimates are not  independent.*

This is where our simple model starts to break down. In order to get the improved accuracy and expectations that the Central Limit Theorem says we should get, we need independent distributions. But building software is full of dependencies: if I can use this library, it will be easier to finish this task; if team A has their stuff done, testing will be easier for team B. In practice, that means the distributions for any task are continually changing. That's why Scrum says to always verify your estimates when you take stories into a sprint. And it also means we're going to have a bit of a mess to deal with regarding schedule dependencies.

Ok, so let's just add some buffer time and fill it with some minor UI cleanup. Oh, and that silly refactoring that developers keep wanting to do. How about 20%? That seems like a reasonable buffer amount.

##We have plenty of time left - Parkinson's law

Way back in 1955, C. Northcote Parkinson published an essay in The Economist titled [Parkinson's Law](http://www.economist.com/node/14116121). It was a humourous look at the inefficiences of bureaucracies and started with this gem:

>It is a commonplace observation that work expands so as to fill the time available for its completion. - C. Northcote Parkinson

As a devout procrastinator myself, I can firmly attest to the accuracy of this observation. And in practice, it's truth is enshrined in all of our management truths. We set deadlines (real or arbitrary) for ourselves and others to make sure work gets done. We apply pressure by hovering about asking "Is it done yet?" a dozen times a day. We build multi-year roadmaps, and talk about commitments so people feel personally responsible for meeting everything laid out in the plan.

But people are really good at figuring out if a deadline is arbitrary, and they ignore it. They know low-priority "filler" tasks when they see them and assign them the appropriate low priority. All of these "hacks" to increase the sense of urgency work…until they don't. And then you're left back where you're started, except now people don't trust the real deadlines either, and question whether that "really important" task is really important, or something that won't actually be used. 

On top of that, management *knows* there was a buffer, and over time it fills with unplanned tasks, because hey, it was buffer space to begin with. No matter how big you make that buffer, it won't be big enough because it's not real and everyone knows it.

Oh, and your estimate was way off to begin with.

##This time we'll do better - Planning Fallacy

Most people are optimistic estimators, even when confronted with objective data on their past performance. This bias is called the [planning fallacy](http://lesswrong.com/lw/jg/planning_fallacy/) and is one of the most well-established cognitive biases in human psychology. But how wrong can they be?

[One study](http://www.tandfonline.com/doi/abs/10.1080/14792779343000112?journalCode=pers20) asked students to come up with estimates for when they would finish their personal academic projects (i.e. papers and such). They asked students to estimate when they were 50% confident, 75% confident, and 99% confident they would be done, and how do you think they did?

* 13% finished by their 50% confidence time
* 19% finished by their 75% confidence time
* 45% finished by their 99% confidence time 

So, even when people were told to give their worst-case estimate (ok, 1% better than the worst-case), only 45% were able to finish. That's pretty bad, however you slice it.

I expect that part of the issue is procrastination and Parkinson's law. I remember college. There was some class work and a whole lot of [other stuff](https://en.wikipedia.org/wiki/Age_of_Empires). The other stuff usually got prioritized higher due to an inherently higher fun factor. But some follow-up studies shed some more light on the reason.

It turned out that asking subjects for realistic "best-guess" scenarios produced almost the same result as asking them for their optimistic "best-case" scenario. Also, asking subjects come up with a "worst-case" scenario did not lessen their optimism in the "best-guess" scenario. People expect that the plan they come up with is actually what will happen, even when asked to contemplate all of the things that can go wrong with their plan. In fact, this bias is so strong, that when subjects were asked to break down work into smaller tasks, their overall estimate for a project got *worse!* As subjects added detail to their plan, they became more confident in it's accuracy and allow less room for error. But disruptions are unavoidable, no matter how well you plan.

**OVERFITTING**

##Combining chance

Let's say you have three major risks to your project. Each has about a 50% chance of happening. The odds of any single one of them firing may only be 50%, but there's an 87.5% chance that *at least one of them will happen.* 

What about all of the risks that have a smaller chance of firing…say 5%. That's probably too small to even track. But if you have 14 of those, there is a better than 50% chance that at least one of those will fire.

Remember those probability distributions for individual tasks that we covered earlier? How many of those had a 5% chance of taking twice as long as estimated? Probably a whole lot. 

**SOMETHING ABOUT HOW DEPENDENCIES MATTER MORE** 

##Complexity is non-linear

As projects gets bigger and more complex, the reasons for project delays shift. As you have more features, it's increasingly likely that you miss something during the planning stages. As the project schedule grows, the potential for the market to shift is greater, as is the risk of major reprioritization and scope changes. Communication gets more complex as more people and teams are involved.

That growth in complexity is non-linear. In other words: Knowing how features will interact when there are 20 existing features is more complex than it is when there are only 3; Adding another cross-team dependency is harder when there are already 10 teams on the project than when there are only 2. 

[Complexity is a major risk in itself](http://sloanreview.mit.edu/article/understanding-and-managing-complexity-risk/) and needs to be managed, both for schedule risk and fragility.

##Estimates are fragile

It's easy to influence developer estimates. Sometimes, you have a bad project manager that thinks that pushing for tight (and usually impossible) deadlines will motivate a team, but that never works. Developers that are behind schedule are demotivated and unproductive. Being ahead of schedule makes devs more productive overall (but has less impact on schedule than you might think, because of Parkinson's Law again).

* Teams that will agree to anything.

##Software estimation is harmful

Software estimation is harmful because it hides all of these complexities behind a facade of predictability. And that just increases the risk of failure.

Estimation is not free. It takes time to decompose a large project into it's components parts and figure out what it will take, and that lowers productivity. In [Peopleware](http://www.amazon.com/gp/product/0321934113/ref=pd_lpo_sbs_dp_ss_1?pf_rd_p=1944687762&pf_rd_s=lpo-top-stripe-1&pf_rd_t=201&pf_rd_i=0932633439&pf_rd_m=ATVPDKIKX0DER&pf_rd_r=02C0H71TXX6YZ44NENQA), Tom DeMarco and Timothy Lister found that *any* estimation reduced a team's productivity, *regardless of who did the estimation.* This is coming from a guy who, in 1982, [helped establish the metrics and estimate-focused culture](http://www.amazon.com/Controlling-Software-Projects-Management-Measurement/dp/0131717111) in which most software projects have been managed for decades. So what does he say now that 40 years of evolution in softare engineering practices have failed to give us a process that can consistantly deliver a software project on time and on budget?

>My early metrics book […] played a role in the way many budding software
engineers quantified work and planned their projects. In my reflective mood,
I’m wondering, was its advice correct at the time, is it still relevant, and do
I still believe that metrics are a must for any successful software development
effort? My answers are no, no, and no.
>
>[…]
>
>To my mind, the question that’s much more important than how to control a software project is, why on earth are we doing so many projects that deliver such marginal value?

##Why do we estimate?

So if estimation is bad, why do we do it?  When I ask that question, I usually get a list of answers that looks something like:

* To decide whether we should invest in or undertake a project
* To coordinate release timing with marketing/customer support/sales so they can be ready for the launch
* To figure out if we need to hire more people 
* To schedule for cross-team dependencies
* To generate a long-term roadmap based on resource bandwidth

**[Insert How's that working out for you image]**

Those are all good and reasonable things to want, but how much does estimation actually help? And what if there were other ways to achieve those goals? Ways to be less dependent on accurately predicting the future.

What if, instead of estimating

<table>
    <thead>
        <tr>
            <th>to…</th>
            <th>we…</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>…decide whether we should invest in or undertake a project</td>
            <td>…fund products and value streams and revisit funding based on ROI</td>
        </tr>
        <tr>
            <td>…coordinate release timing with marketing/customer support/sales so they can be ready for the launch</td>
            <td>…have smaller development cycles and improve transparency and coordination</td>
        </tr>
        <tr>
            <td>…figure out if we need to hire more people</td>
            <td>…staff to investment. (Ramp-up times are loooooooooong)</td>
        </tr>
        <tr>
            <td>…schedule for cross-team dependencies</td>
            <td>…field cross-functional teams to reduce dependencies and use architectures that promote decoupled systems</td>
        </tr>
        <tr>
            <td>…generate a long-term roadmap based on resource bandwidth</td>
            <td>…focus teams on single problems/products so you can finish as quickly as possible</td>
        </tr>
    </tbody>
</table>

Maybe you can't get away from estimates completely, but they become less important if you change the system to optimize for the outcomes you want, rather than trying to forcing the inputs to comply with your assumptions.

##Manage projects, don't pack boxes

Ironically, one of the biggest challenges I see when teams adopt Scrum is an *abundance* of time. 

(I'm imagining the sound of millions of developers crying out in protest over that statement, so let me clarify.)

Scrum places a lot of focus on time-boxed iterations or sprints. The concept is great - you must be completely wrapped up with development and ready to deploy at the end of a two-week (or one, or four, or whatever), sprint. There are [a lot of benefits](http://www.braintrustgroup.com/scrum/benefits-of-scrum/) to using scrum as a project management framework, but time boxes come with their own set of problems.

When you have stories that are too big to fit into a sprint, you split them into smaller chunks so you can deliver some of the functionality within the window. But then you're left with the space between when you finish those important pieces and when you start the next sprint. 

What do you put in that space?

If you're doing waterfall, you move on to the next thing on the project plan. If you're doing Kanban, it's the next highest ranked item. But Scrum has this space that just wants to be filled on one hand, and this rule that everything needs to be done at the end of a sprint.

If you're an experience team and can break down your stories into very small pieces, it's not a problem. You don't have much space in your box. But that's not where most teams live. Most teams get to the point where a meaningful story takes somewhere between 1-2 weeks to do. It fits in the window, so they stop there. And then they run into having 3-4 days of space left in their box that needs to be filled. So they fill it...with whatever is small enough to fit.

I've moved more times than I care to count. Between college and multiple apartments and now my house, I have probably packed hundreds of boxes of  *stuff*. When you pack a box, things don't usually fit perfectly, so you take whatever random crap you have laying around and fill that box to the top.  Things that are nothing like the rest of the stuff in the box. Things that you probably don't really need. But you have the space, and you don't want to waste it, so in they go.

That's exactly what happens with sprints. The empty space gets filled with whatever is sitting around in the backlog and is small enough to fit. Size becomes the sole driving factor, and importance/impact/value is forgotten.

Whatever methodology you are using, the next most important thing is always the next most important thing. Keep your eye on that, and if you need to break things out in a different way to satisfy your methodology, you can do that, or you can break your methodology. Remember, Agile is about [individuals and interactions over processes and tools](http://agilemanifesto.org). Don't let estimates cloud that perception.


Evidence based scheduling (http://www.joelonsoftware.com/items/2007/10/26.html)

Joel

##Plan to fail, and plan how to deal with that failure

Rudy Guliani - we had a bunch of plans 

Hopefully your planning is wasted. But failing to plan is planning to fail.

##Pick your head up

W. Edwards Demming was one of the giants in the world of process improvement. He had a huge hand in rebuilidng Japan's post-war economy, which became the #2 economy in the world within a decade after it tranformed it's manufacturing processes based on ideas he taught. As a statistician, he focused heavily on measuring processes and improving them through continuous introspection. 

You can't manage what you can't measure. - False! The most important figures that one needs for management are unknown or unknowable (Lloyd S. Nelson, director of statistical methods for the Nashua corporation), but successful management must nevertheless take account of them

##Estimate!

The benefits you get from estimating are huge:

* Consider the problem in detail and come up with solution(s)
* Figure out dependencies to be managed around
* Identify risks to manage around
* Develop a shared understanding of the solution/transparency to reduce the bus factor
* Relative costing to help prioritize 











Now let's go back to the assumption that the process of building software isn't random. It's certainly not as random as a coin flip. Expertise absolutely plays a role, and all things being equal, an experienced developer can build a feature faster than an inexperienced one. However, there too many unknowns in all but the most trivial applications to have a high confidence in any single estimate.


##A crash course in probability and statistics 

It turns out, people are really good at estimating some things: How hard do I have to throw this ball to reach my son so he can catch it? Do I have enough time to cross the road before that car gets here? How fast do I need to run to catch that fly ball? The physical world has a small set of fixed rules that we internalize at an early age

##Building software isn't like building a house

Building a small home is a fairly well-understood process. Humanity has been 


Software estimation is harmful because it creates a false sense of predictability in an inherently chaotic process.

ESTIMATION != PLANNING


DATA: The big dig.

##Estimation is fundamental to building software

##Why do we estimate

Need to know when things will be delivered so we can coordinate marketing, sales, communication, etc.

Need to prioritize features.

Need to manage workload on a team to maximize productivitiy.

##Why are we so wrong?

Estimate is predicting the unknown. We come up with a number, but what we really have is a distribution.

##Crash course in statistics

###Probability distribution

Go from an estimate, to a distribution

###What value are you picking when you estimate, the most likely, or a confidence level

Spinner example:

Case 1: ROUGHLY NORMAL DISTRIBUTION


Case 2: LONG-TAIL DISTRIBUTION


Both have the same peak, but they have different means and different confidence intervals.


###Complications

Combining probability distributions


###Simplifications

Central limit theorem


##Scaling up

Individual errors matter less, but biases matter more.

###Psychological biases

Under-estimating

Picking the biggest peak

Poor at risk assessment

The birthday problem - even low probability risks will fire sometimes

Incentives



##Behaviors

###Packing boxes

###Parkinson's law

"Work expands so as to fill the time available for it's completion" - Cyril Northcote Parkinson, The Economist 1955

##Confidence intervals


##What does this mean to a project plan

##Unknown unknowns and black swans


##Giving up control

Software project 1: ~1 million dollars with a return of $1.1M
Project 2: ~$1M with a return of $50M

" I’m suggesting that first we need to select projects where precise control won’t matter so much. Then we need to reduce our expectations for exactly how much we’re going to be able to control them, no matter how assiduously we apply ourselves to control."

##What is estimation good for?

###Making decisions
You still need to make decisions, and you still need some basis for making them.

WSJF gives you a metric, but don't think that a 5.1 is really more important than a 5.0. What is your margin of error? That is not a statistically significant difference.

###Forcing you to look at the problem

Breaking tasks down into smaller tasks forces you to consider the problem in enough detail to uncover some of your mistakes before you make them.


##Manage risk, because you can't control it

Building software is playing the stock market. Some things are riskier than others. Control your risk profile.

##Why do we still need to estimate?

##How do you use estimates appropriately

