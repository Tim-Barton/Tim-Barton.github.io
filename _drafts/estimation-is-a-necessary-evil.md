---
layout: post
title:  "Estimates are a necessary evil"
---

Bold claim huh?

"Evil" might be a little strong, but I don't think I've ever met a Developer who *likes* doing Estimates. Sure they suffer through doing an Estimate, but best case scenario it ends up being an useless artefact that's quickly outdated, and worst case the Devs are told to reduce them then are blamed when the project fails to deliver on the (artificially shortened) Estimate. Yet businesses still insist that Estimates are necessary and force Developers to create them.

So do we take up pitchforks and overthrow the oligarchy?  
Unfortunately no, because while I too have a less than stellar opinions around Estimates, I have come to believe they are necessary to a certain degree.

To understand how to solve the problem, I'm going to spend this post breaking it down and provide some high level approaches we can follow.

## Why are Estimates bad?

In my experience Developers are usually negative about Estimates for a few main reasons:

### Too many unknowns at the time of estimation

Also known as the 'how long is a piece of string' problem, it occurs when the idea the business wants developed hasn't had enough time spent on it to define the scope of the problem. While not every facet of every idea needs to be detailed, for an estimate to be realistic time needs to be made formulating an approach which involves making certain trade-offs to meet the defined needs. If these needs aren't scoped then the correct trade-offs cannot be reasoned about and the estimate cannot be made.

As an example let's say you're asked to develop a Customer Relationship Management (CRM) system for two different independent businesses:  

1. The first client is a small business with ~20 customers that they contact on an individual basis about their small range of products, and just need a way of sharing the customer contact details between the 3-4 employees.
2. The second business is a multi-national mega-corp with thousands of customers on multiple continents each with a different customer contact point depending on the product and hundreds of employees requiring concurrent access.

Similarly there are two extremes of the solutions available:

1. A simple spreadsheet located on a shared drive or cloud document platform, which can be created in a single afternoon by anyone even slightly technically minded
2. Purchase an off-the-shelf solution from a large vendor (e.g. SAP) or create a bespoke solution requiring thousands of hours of development and testing effort by experienced teams, integrations with Active Directory/Exchange/etc, and expectations of 99.9% availability.

I hope at this point it's obvious that the two solutions are vastly difference in terms of cost and the scale they support, meaning that while the large system would comprehensively cover the needs of the small business the cost would be far too high and while the cost of the spreadsheet is small the mega-corp needs the comprehensive feature coverage of the larger system. In real-life it would be rare for the unknowns at the time of estimation to be this pronounced but it does demonstrate the problem faced by developers - they can either offer a cheaper solution that may not meet the needs, or a more comprehensive solution that may be too expensive. It's also rare for the choice to be a simple 50-50 split between two options, leaving an estimating developer in an no-win situation trying to the decide the best option from multiple paths without the required information.

The problem is even worse when the solution requires the use of a previously unused technology. Even the best documented 3rd party offering with excellent support can behave in ways that a developer can't pre-plan for and therefore can't estimate. Even though a developer can spend time investigating the new technology, it is never a guarantee because it's impossible to determine all the edge cases that are hit until you are actively developing the solution. At the end of the day Software Developers aren't building chairs, tables, or even houses, all of which have specific plans on how to be built. Instead dealing with new technologies is closer in nature to renovating: until you pull off the plasterboard it can be impossible to know that the previous plumber ran the pipes half-way around the room, the original electrician has used non-standard wiring that needs replacing, or that mold has destroyed parts of the timberwork, creating extra costs that were unable to be estimated.

While there are always going to be some unknowns at the start of a project which Developers need to handle via making certain (preferably documented) assumptions, having too many unknowns/assumptions creates an estimate that the Developer can have little faith is correct, but will be expected to conform to, leaving them feel set up to fail.

### The Estimate will be voided by changes during the project

Changes in software projects are inevitable, whether due to some of the upfront assumptions being proven wrong or the business needs changing, every project needs to have the ability to handle changes in scope. The simple fact these changes will occur can be enough to make a Developer feel like time spent upfront estimating is wasted, but there are a few things that can make this even worse:

1. The change was inevitable. More than once I've seen a Developer with a good domain understanding and emotional investment in a company have their views dismissed by a less experienced business owner, just to be proven right.
2. The estimate was a high-confidence estimate coupled with a large number of changes. It can be very disheartening for a developer to spend a large amount of time creating an estimate they are comfortable with committing to with a high degree of certainty, just for the sheer number of changes to make the final product unrecognisable to the estimated product they worked so hard to understand.
3. Estimating the size of the change takes time away from completing the already committed work, so even if the change is eventually knocked back the scheduled delivery date has slipped.

### They are consistently asked to estimate things that never eventuate

Every Developer I've ever talked to wants to code. It doesn't matter whether their personal drive is to be creative or to solve problems - code is our chosen tool to reach that goal. So any time spent away from coding is time spent away from the thing that we all want to be doing. In a professional environment there will always be things pulling us away from coding, but we accept them as long as we can get back to the task we love.

I have unfortunately seen how badly a Developer's morale can be affected when all their time is spent on these non-coding tasks to appease red-tape with nothing to show for it. It can be a hard to describe to someone just how hard it is - at the end of the day they're getting paid to do 'easy work' so why are they unhappy? The best analogy I can think of is spending all your time planning a dinner for your friends, just for no-one to come. You've done all the prep work - running around getting food & drinks, done all the cooking, cleaned and tidied, etc - but you don't get any of the pay-off. Have that happen once and you'll be upset but probably understanding that someone was sick, someone else had a work emergency, etc. Have it happen consistently and you'll start to feel that no-one appreciates the work you put in.

### All of the above, all the time

## Why do we need them?

I'll admit that for many years I thought that most of the "reasons" behind why the Business Units "needed" Estimates were artificial guff they could mostly do without, then I had an epiphany.

I was working on a consumer facing value-add product for a Marketing department that needed to be completed before a big event. While not completely a [loss leader](https://en.wikipedia.org/wiki/Loss_leader), it was designed to be reduced revenue product to drive customer engagement
