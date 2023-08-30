---
layout: post
title:  "Why we Estimate"
---

I've never met a Developer who likes to Estimate (or at least admits to liking it). We've all done Estimates sure, but at best it's with a stoic acceptance that "it's just part of the job" and at worst it's with a hate-filled "why are we wasting our time with this".

The reasons for why this is range from a simple "it's time spent away from coding" to complex issues that would take their own post to cover appropriately, but I believe it's possible to turn Estimation into a tool that allows Developers to do their best work - you just need to understand *why* you're doing them.

Without further ado here are my completely subjective "valid" reasons for doing Estimates:

* Opportunity Assessment
* Tendering
* Lead Times

## Opportunity Assessment

Almost every Estimate I've been asked to create boiled down to the simple question of "Are we going to make money doing this?" Given every business (even non-profits) need to make more money than they spend in order to stay in business, this question is a very important one. While cost is just one deciding factor in any decision, the level of accuracy needed for the cost changes the closer you get to making the decision.

Let's use the example of looking for a house / apartment / unit / etc:

1. At the very early stages you'll probably have a very broad range of criteria: desired suburbs, numbers of bedrooms/bathrooms/etc, cost  
2. You'll then do some early research leading to refined and updated criteria: the suburbs are a little further out, drop the optional extra bathroom, and increase the budget.  
3. From there you'll start to look at individual houses, where you'll be making individual decisions as to what you'll pay for each house given the criteria it meets.  
4. If you're lucky enough to be spoilt for choice you'll get to a point where you have to make a decision between House A - more expensive but better in some way - or House B - cheaper but not as good - because at the end of the things you can't live in 2 houses.  

Software Product design can follow a similar lifecycle:

1. At the very early stages the business will have a rough idea of what the product might do, who it might appeal to and rough cost/risk profile
2. They'll then do some further research helping refine the product offering, target market segments/personas and cost/risk options
3. As they work through the product they'll work on the individual features until it's a solid product idea with a cost/risk breakdown
4. Finally someone needs to determine which of the planned products gets executed and in which order, based (partially) on the costs

{: .note}  
When I say "costs" I mean that to cover all the possibilities: money, time, number of Developers, etc. Each business will be different in what they care about and track, so substitute "cost" with whatever personal metrics your company uses  

Each stage of this cycle needs a different level of Estimate. Just as with the house search where you have a range of costs you're looking at, a Business in the first Phase is mostly looking to understand whether the idea is viable in general. By the final stage the Business should have a very clear idea on the expected return, and therefore the appropriate costs they can take.

### The Problems

There are two main issues that I've seen arise when considering opportunity assessment.

The first is a mis-match between the Business phase and the estimate requested. Simply put the business is in Phase 1, but they get a Phase 4 detailed Estimate. This can be due to company culture/red tape, Developers' desire for details, or a combination of the two, but it frustrates everyone - Developers will expect the idea to be completed and get frustrated at the lack of details, and the Business gets frustrated by all the detailed questions they're expected to answer when those details haven't been worked on yet.

The second problem is when the Business have spent so much time and energy on an idea to get it to Phase 4 that it's now their baby, their Magnum Opus - basically it's not allowed to fail. These are the Estimates that usually get pushed back on, because along with the idea not being allowed to fail, it also can't be changed and the Estimate *has* to be under X so "you just need to make it work".

### The Solution

Both problems can be solved by the same action - get involved earlier in the planning. Hopefully you've heard of the concept of [Shift Left](https://en.wikipedia.org/wiki/Shift-left_testing) where the earlier in the Development cycle testing is considered, the better the final product is. The same concept can be applied to Product - the earlier in the Product design cycle a Developer has input, the closer aligned the Product is to current systems capabilities, which in turn makes the Product cheaper.

"But Tim" I hear you say "I'm just a Developer, isn't it Senior Management's job to deal with that early phase stuff?"  
Well, Yes, but let's be real, for every Senior Manager I've had who understood the systems I've had 2 or 3 who barely knew how the Product itself worked, let alone the technical systems. I've even had a Senior Manager who (to the best of my knowledge) has never written a line of code in their life. Most of them therefore won't have the knowledge required to influence a decision so it aligns with the current technology capabilities.  

Does this mean I'm telling you to barge into CTO level meetings to make your opinions known? No, that's literally the worst thing you can do. Focus instead on the fact that for every Chief Marketing Officer with a great idea, there will be a team of Marketing and Product people tasked with seeing it to life - so go make friends with one of them. If you can influence them in the early Phases to shape the product in way that works better with your systems, the lower final Estimates mean they'll see the success of working with you and continue to do so. You in turn then spend less time arguing over Estimates and more time coding.  

## Tendering

For the most part Tendering is just a special case of 'Opportunity Assessment' where you're usually getting a full Phase 4 Product idea from an external entity. Given the Product idea has come externally your ability to follow the preceding advice to get involved earlier is severely limited.

One possibility is when the Tender allows a 'non-compliant bid' which means you don't have to meet all the listed requirements (usually for a lower price). If you can early on work with the Sales team to identify the areas of a Tender where you can provide the most value for the cheapest price, it will allow them to create a non-compliant bid at a very competitive price, which could carry the day for them (and therefore you).

## Lead Times

This is actually a fairly recent addition to my list that occurred when I was working on a consumer facing value-add product for a Marketing department. It was designed to be a [loss leader](https://en.wikipedia.org/wiki/Loss_leader) - something that could be marketed far and wide to draw customers in with the promise of how much value they'd get from us. In the course of events we were told that TV ad slots to feature our product had been booked for just after our expected launch date and ahead of a major event. This came with the dire warning that they'd need 6 weeks to produce different content for those slots if we were going miss our expected launch date. My first reaction was along the lines of "Why'd they book ads before the product is done, just be patient, sheesh." Then a light bulb went off regards the concepts of ['Wastes'](https://theleanway.net/The-8-Wastes-of-Lean) from Lean Principles.

Basically I realised that:

* If the Product was Live but not being advertised, then it was losing money and not meeting it's goals of bringing in new/relapsed customers  
* If the Product was ready but not launched until advertising was ready, then it was wasted sitting on the shelf, and we were giving our competitors a chance to be first to market.

The best case scenario for this Product was to launch it *as close to* the advertising date as possible. This required us to as realistic with our timeline Estimate as possible - and track our progress against that 6 week Go/No Go readiness date.

### The Problem

The main issue I've seen with timeline Estimates boils down to a difference between Effort and Schedule. Most Developers I've seen tend to estimate in terms of Effort - in a perfect uninterrupted world it should take X days to complete that task. Unfortunately we don't live in a perfect world, there's an endless drain on our time: Daily Standup, Weekly Team meetings, Monthly Department meetings, Code Reviews of others' work, calls from the Junior asking for help, Sick Days, Annual Leave, and the list goes on.

Secondly with Effort based Estimates they can be based on an internal thought process of 'How long will this take *me*' when the work in question might be done by someone either less skilled or less knowledgeable in the domain.

### The Solution

To combat this I use a two-fold approach:

1/. Use [relative estimation](https://www.agilealliance.org/glossary/relative-estimation) techniques  
2/. Apply a schedule modifier based on past data  

Relative Estimation is a wildly written topic (and I have my own post planned for the future) that can help remove some of the "I'm doing this work" bias, as well as solving a host of other problems.

The schedule modifier is a concept I've used to turn the Effort Estimate into a Schedule Estimate by applying a broad multiplier denoting how much Effort a Developer can spend in a day on their tasks. I've used figures a low as 50% and as high as 80% depending on the team make-up, prior performance, and the expectation of external interruptions, meetings, etc. Using a schedule modifier isn't an exact science but I've found that as you track your deliveries you will find a figure that represents the output of the team.

The concept here isn't to be 100% precise on each individual feature, but to create a realistic trackable project estimate that can live within the margin of error for your work.

## Conclusion

I don't think that Estimates are ever going to the favourite part of a Software Developers job, but by understanding why an Estimate is required you can help remove some of the pain.  

There are some future posts planned around Estimates and ways to approach them, which should hopefully help reduce that pain even further.
