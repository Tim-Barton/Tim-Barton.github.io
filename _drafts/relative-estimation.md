---
layout: post
title:  "Relative Estimation"
categories: estimation
---

Relative Estimation is the act of grouping features by their relative size then estimating each group, rather than estimating each individual feature as per traditional methods.

As an example, let's say I need to buy my wife a present, so I go ahead and list some options that she might like:

* Bath bombs
* Books
* Flowers
* Massage
* Jewellery
* Cruise Holiday

As a couple we have set a budget for presents, so I can buy as many presents from that list that fit within the budget. I could go to the effort of estimating all the items, but I know I can't afford them *all* so let's just quickly size them:

| Cheap | Fairly Cheap | Not that expensive | Expensive | Really Expensive |
| Bath Bombs | Books<br> Flowers (Shops) | Flowers (Florist)<br>Massage | Jewellery | Cruise |

Now that we've relatively sized the options, we give them some rough estimates, so I can think about what is possible:

| Cheap | Fairly Cheap | Not that expensive | Expensive | Really Expensive |
| Bath Bombs | Books<br> Flowers (Shops) | Flowers (Florist)<br>Massage | Jewellery | Cruise |
| ~$5 | ~$20-$30 | $50-$100 | $100-$200 | $1000+ |

These rough estimates now allow us to think about the cost vs. value and whether it would be better to get one big present, or a few small present with the budget we've allotted.

We can estimate software features in the same way, either to understand what's possible within a budget, or what the rough total cost of all the desired features.

## Why would we do this?

The general reason for Relative Estimation boils down to

> “It is better to be roughly right than precisely wrong.” - John Maynard Keynes

Extending our above example, let's suggest our budget is $100.

I think to myself that my wife *really* likes jewellery and she needs a new necklace to hold some of the pendants she already owns. Sold on the value in my idea and knowing my budget I do a search to find a necklace for $100 that I think she'll like. I buy it, she loves it, but it turns out to be too fine for the pendants she has, and the necklace breaks in a week. I was *precise* in my estimates, but I bought the *wrong* thing.

Conversely by using the rough estimates I think to myself that jewellery is probably out, but I could put together a few smaller items. So I get her some nice flowers from a Florist, along with a book she's been eyeing off and some bath bombs. My rough estimates mean that maybe I go a little over budget, but I've brightened up our home and given her a few lazy afternoons reading in the bath - so I win 'Husband of the Year' again.

In the software world you can be wrong by building the wrong thing, but you can also be wrong in the estimate itself. For all the precision and care you put into something, there are always unknowns that can blow out the timeline/cost: an API that behaves differently than documented; a vendor that ghosts you once the contract is signed; a library has a security flaw discovered you need to mitigate. None of these things can be planned for, but they have made your precision estimate now worthless. Instead a rough estimate gives you enough precision to make commitments, and enough slack to handle some of these black swan events.

There are some other specific benefits to using Relative Estimation

### Reason 1: It's quicker and more collaborative

Once you've accepted that being rough is good enough, you can estimate an entire project in a couple of hours, rather than weeks.

Also because the speed is increased, you can involve the whole team in the process. This creates a better solution as more viewpoints are included working towards the best outcome. It also helps better train Junior and/or newer staff as they can be present through this workshopping to see the edge cases, thought processes, etc.

### Reason 2: It helps remove bias

Generally speaking Estimates tend to be done by Senior Developers who have a good understanding of the systems to be changed, so they tend to Estimate how long it would take *them* to complete a feature. This in turn can cause the overall Estimate to be undercooked as the Senior Developer generally won't be doing all the work (or any of the work). A by-product of the greater collaboration mentioned above is the Junior staff will be in the room to suggest a more appropriate Estimate for their skills. If you then take a mid-point between the Senior and Junior estimates for the whole group, averaging this across the total number of features your Estimate should be roughly right.

### Reason 3: Our brains work that way

Our brains are [excellent pattern matching machines](https://www.psychologytoday.com/au/blog/singular-perspective/202105/why-the-human-brain-is-so-good-detecting-patterns) so they are very good at comparing and contrasting things - it's why we see cloud animals. So by looking at our work in comparison to other items of work, we are working with our brains rather than against them.

Let's try an example: If I ask you to visualise 2.5 million litres of water, could you?

Go on, give it a proper go.

Now I'll tell you that an Olympic sized swimming pool has roughly 2.5 million litres of water, can you visualise that amount now?

By giving us a reference point for our estimates we can better utilise the unique abilities of our brains to match patterns.

## How to get started

When you're first starting out, you wont have any tickets to use as your baseline, so what do you do?

Simply, you just need to pick a feature and go with it. Personally I try to find something that I think will be in the middle of the scale, something with a level of complexity or some unknowns, but not too much, and hopefully close to something the team has done before.

There's no silver bullet or guaranteed algorithm to picking this first feature, just go with something that seems right and adapt as you learn.

## Ways to Relative Estimate

There are two main models I've seen used for Relative Estimates:

* T Shirt sizing
* Story Points


### T Shirt Sizing

This is the act of breaking work into buckets similar to the sizes used in Men's clothes (shirts in particular): Extra Small, Small, Medium, Large, Extra Large, etc. The example provided above is a demonstration of using T Shirt Sizing.

Some people I know prefer to have their T Shirts work on a Linear scale, where each size is just the next step up. Personally I like working on an Exponential Scale where the sizes "jump" more - specifically I like it when each size is double that before it.

|        | Extra Small |Small | Medium | Large | Extra Large |
| :---:  |:---:  |:---:  |:---:  |:---:  |:---:  |
| Linear Scale |   1   |   2    |   3   |      4      | 5 |
| Exponential Scale | 1 | 2 | 4 | 8 | 16 |

I prefer Exponential Scale because I feel it's easier to rationalise about the relative sizes when you can ask questions like "Ok so Feature A is bigger than Feature B, but is it twice as big or just a little bigger?" It also becomes easier to gut check the Final Estimate as the buckets are related. Lastly by having a much larger number associated with your largest items of work it helps embody the concept that they are usually those with the most risk.

My normal process is to relative size all the features, then Estimate one of the 'Small' tickets and one of the 'Large' tickets. If we've sized correctly the 'Large' Estimate should be 4 times the 'Small'. We can then calculate the other sizes Estimates and allow the team to gut check them against the features in each bucket. This provides a few different points of validation to catch any errors or outliers without an undue amount of extra effort.

These validation steps also help protect against one of the major downsides of T Shirt Estimation: The Extra Large bucket becoming an 'or bigger' bucket for all the things that are just too big to think about. No-one wins if you leave these super big tickets as they are, so when you find them you really need to do some feature breakdown to ensure they fit within your scale and are being estimated correctly.

### Story Points

Story Points are probably the most well known Relative Estimation technique as it has become a staple part of a "standard" Scrum implementation. With Story Points, the buckets we use are numbers (as compared to labels like in T Shirt sizing) which allows us to estimate using the concept of Velocity - defined as the number of Points achievable by the Team in a given time period. When you generate your expected Velocity using past data this has the extra benefit of handling the Senior/Junior estimation difference, because the score has already aggregated the different amount of work that each person is able to achieve.

Similarly to T Shirt Sizing, Story Points have two major scales that I've come across: the [Planning Poker](https://storypoint.poker/) scale and the Fibonacci Sequence.

| | :---: | :---: | :---: | :---: | :---: |:---: |:---: |:---: |:---: |:---: |:---: |
|Planning Poker| 0 | 0.5 | 1 | 2 | 3 | 5 | 8 | 13 | 20 | 40 | 100 |
| Fibonacci |   |     | 1 | 2 | 3 | 5 | 8 | 13 | 21 | 34 | 55 |

While I do use T Shirts for my up front Estimation, I switch to Story Points for the Iteration Planning during the delivery. I do this for a few reasons:

* over the course of the project you're going to learn things that make your in progress estimates more accurate than your up front estimates.
* Velocity is a useful tool for ensuring you're taking the right amount of work into each Iteration
* if you're already having good ticket discussions in your planning, adding a final estimate step doesn't take much longer, and can uncover edge cases not originally discussed.

## Things to keep in mind when using Relative Estimation

### Remember you're Sizing/Estimating against the other tickets

I've been in situations where teams or individual have created an expectation that "Large" means "6 weeks", so they'll estimate the feature in their head, then convert to the T Shirt or Story Point size.

This is just standard Estimation with added steps, keeping all the problems and adding none of the benefits.

So remember the key is: "how does this feature compare to the others?" - when leading an estimation session it's good to stop and literally ask this question every once in a while. More when the team is new to this process.

### Don't be afraid to change your scale

When you're first starting out, since you've just picked a feature to be your baseline, what you might find is that all the work is bigger (or smaller) than the first feature. In this situation don't be afraid to take all your features and move them down a band or two (i.e. all Mediums become Smalls, Larges become Mediums, etc) to give you more room at the higher end of the scale.

As you get more mature this will become less necessary, but still something you can keep in mind.

### Break things down where you can

Tickets in the highest buckets can sometimes become an 'or bigger' scenario, where your Estimate says they'll be 6 weeks, but in reality they're a lot bigger.

Do your best to identify tickets that are in this category and either break them down into smaller chunks, or plan to spend early iterations on these tickets until you can break them down.
