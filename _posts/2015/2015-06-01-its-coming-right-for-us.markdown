---
layout: post
title:  "It\'s Coming Right for Us!"
date:   2015-06-01 11:52:37
comments: true
categories: [product owner, triage]
---
I've been involved with several development teams that lost their way. They got overwhelmed by incoming requests and made some bad decisions that derailed progress on what should have been their main focus.

It wasn't totally their fault. Triage is hard. It takes a lot of discipline (and support from above) to say "no" to the person *passionately arguing with you* about how X needs to be done RIGHT NOW, even if it's not the most valuable thing you could be doing.

## You have limited resources

If you had infinite resources, you wouldn't need to triage. You could do everything you want to and damn the consequences. Sounds like a wonderful world.

It's not.

When you have unlimited resources, you build more than you need to. China has [entire cities](http://www.thebohemianblog.com/2014/02/welcome-to-ordos-world-largest-ghost-city-china.html) that were built for a population boom that never happened. 

[![Empty roads in Zhengzhou (source: <a href="http://www.panoramio.com/photo/4956519">Panoramio</a>)](https://d23f6h5jpj26xu.cloudfront.net/ybuhed7nefxfw_small.jpg)](http://img.svbtle.com/ybuhed7nefxfw.jpg)

It's even easier to overbuild software. Instead of rounding up millions of dollars in construction equipment, spending years in planning, and hiring thousands of workers, you just write a few user stories. You're the product owner right? So let's get the team working on that pronto!

Ok, reality check. You're not China. You don't have a trade surplus of roughly 50 kajillion dollars/euros/bottle caps. You have limited time, limited budget, and limited skills on your team, so you need to make some tough decisions as to what gets done. 

## Rule #1: Don't triage like it's self-defense

If you really want to get a handle on your backlog, you first have to figure out what fires you can let burn. Some will burn themselves out quickly, others continue to smolder but never pose an existential threat. Identify those and get them out of the way. 

Yes it's painful. We all want to create the perfect product. We think that means it can't have imperfections, so we lie to ourselves just a little bit to justify fixing that alignment issue, or adding validation to restrict that name field to 600 characters (because otherwise it will throw an error when we try to write to the database and that's so horrible!). We end up overreacting to every minor thing because we want to.

<iframe width="560" height="315" src="https://www.youtube.com/embed/Nt6kKhlX8vU" frameborder="0" allowfullscreen></iframe>

Take a deep breath and repeat after me: "let it burn."

We used to fight wildfires by putting out every fire that sprang up before it could spread. It turns out [that was a pretty bad idea.]([http://usatoday30.usatoday.com/news/nation/2006-11-07-fire-management_x.htm) We ended up with more severe fires in the end. Now we spend more time *managing* fires as they burn, and spend fewer resources with a better outcome.

If you're putting out every fire as fast as you can, I guarantee you're building up a hidden layer of hacks and tangled code below the surface. Instead of saving your application, you are [increasing the risk of catastrophic failure](http://www.ontechnicaldebt.com/blog/bad-code-isnt-technical-debt-its-an-unhedged-call-option/). So take a breath and figure out how to fix the cause, and not the symptoms.

## Rule #2: Opportunity cost dwarfs all other costs

When you have limited resources, *be lazy*. Figure out how you can add the most value with the least amount of effort. Look for the ideas that will give you a 10x, 100x, or 1000x return on investment. It's easy to fill a list with 1.5x, ideas, but working on those means you're *not* working on something that can get you that 100x return.

What's a 100x idea? It might be a feature that opens your product to a new market. It could be figuring out continuous deployment so your team gets back 80 hours a month to work on new things. Find the bottlenecks in your process and remove them, and write the tools that allow you to create more value with less effort. Take advantage of the fact that productivity gains are multiplicative: if you can do 3 things, each of which gives you a 100% gain, you have an 800% improvement overal (2 x 2 x 2)! It takes almost 22 10% gains to get that return.

When you're going through your list of 1.5x work, always keep your eyes open for the 100x gems and do those first. Your time is too valuable not to.


## Rule #3: Involve the right people

Triage is about making *good enough* judgements. The first thing you need to do is figure out who should be involved. You need the following voices represented:

### Product Owner/Project Manager - Referee

You run the discussion and makes the decisions based on everyone's input. You also represent the product interests (marketability, revenue/cost saving opportunity - essentially the ROI) of each feature. As Product Owner, you own the inbox and backlog, so you better be there!

### Engineering - Sizing, Sanctity of the System 

How big is this request? Is there another way to solve the problem? Is the feature already in the system, but nobody knows where it's buried? You know these answers better than anybody else on the team.

You also represent the sanctity of the system. Is this feature worth the additional complexity and costs that it will incur to maintain? [40 - 80% of the total cost of ownership of a system is in  maintenance](http://www.kictanet.or.ke/wp-content/uploads/2012/08/Forgotten-Fundamentals-IEEE-Software-May2001.pdf). Will it make it harder to add new features in the future? Argue against technical debt.

### QA/Test - Confidence in the System

The end user is your primary concern. How big of an issue is that bug really. Is it something they will encounter 1% of the time, or 100%, and if they do, does it really matter? 

There are many end users, and you represent them all: customers, dev ops, maintenance teams, etc. What does quality mean to each of these? Ultimately, it's about not getting their way: 

* Having a system that rarely crashes keeps your team focused on planned work
* Making sure customers can easily navigate your system keeps them happy and makes your product more marketable
* Solid, consistent design provides the *je ne sais quoi* that makes everything just feel *right*

### The person who made the request - Why?

The team should [ask questions](http://en.wikipedia.org/wiki/5_Whys) to [understand what the reasoning behind any request](http://jasonevanish.com/2012/01/06/dont-build-that-feature-how-to-use-the-5-whys-to-learn-what-your-customer-really-is-saying/). The best person to ask is the person who made the request. Using a proxy can reduce the number of people in the meeting, but sacrifices the ability to dive deep into the problem. Triage often, keep focused in the meeting, and you'll keep these meetings small and fast.
  
## Rule #4: Start with "no"

[![Don't mess with the bear](https://d23f6h5jpj26xu.cloudfront.net/jubmafssa2wxw_small.jpg)](http://img.svbtle.com/jubmafssa2wxw.jpg)

Your backlog is like a backpack that you have to carry every day. Every user story, every task, and every bug has it's own weight. Carry too many and you spend all of your time triaging and re-triaging and shuffling tasks that you'll never have enough time left to work on.

When you discuss a new enhancement or bug, start by rejecting it. Once you do that, you can start to sell it to yourself: Why is it more valuable than what you already have planned? Starting with "no" helps you get in the right mindset to stick to rules 1 and 2.

Starting with "no" is also good for your integrity. You *can't* do everything people ask for. Be up front about that. If you can legitimately consider someone's request and tell them that you're not going to address it up front, you will have a much easier time meeting expectations with the ones you accept.

You also need to change what you mean by "no." Most people see "no" as an absolute, as in "no, we are *never* going to do that." It should mean "we can't justify doing that *at this time*." Priorities change, new justifications emerge. Just because you reject something today, doesn't mean you will reject it a month from now, but you don't want to carry the baggage of all the ideas you rejected. So make it OK for people to ask again if they still have the same problems in a month, or a year.

## Rule #5: Go fast!

Spend just enough time to understand the problem and get an idea of how big it is. You want to answer two questions in triage:

1. Is this problem worth solving?
2. When should you solve it?

If the answer to #1 is no, then you're done.

If the answer to #2 isn't within the next 2-3 quarters, reject it (see rule #4).

From there, either take the request into your current backlog to be fleshed out by the Product Owner, or drop it on your roadmap and look at it again when you get there (don't spend any more time on these until you're about a month out).

Your triage process needs to be fast so you can respond to requests quickly. Your only answers are "we won't address this now" and "we'll look into it some more." Commitment comes later.

## Good triage requires discipline

I like to have one 30 minute inbox review meeting each week (Fridays work great). It's important to stay focused on the go/no-go decision to make the best use of everybody's time. Follow up on the items you accept into your backlog after the meeting to get them ready for development. 

Don't discuss solutions. Don't argue about why you are rejecting something. If you get off track, table the discussion and continue later. Stay disciplined and you'll have a clean way to vet requests and make quick, informed decisions. A good triage process keeps your team focused on the right things, and reduces chaos, allowing you to get more done with the limited resources you have available. 