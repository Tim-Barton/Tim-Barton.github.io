---
layout: post
title:  "Feature Breakdown"
categories: features
comments: true
---

Feature Breakdown is the act of taking your body of work and breaking it down into the discrete tickets that can be worked on individually.

To a certain degree this is obvious, tell a Developer
> make me an API to access this data  

and they'll think to themselves
> Well that's easy, I need a standard CRUD set of endpoints, let's start with create, then retrieve, then update, then delete

They've taken the large piece of work (the API), broken it into individual features (CRUD) and even ordered the work to boot.

The problem is when a Developer thinks this is enough breakdown to understand the problem, but in reality there is still a lot of complexity to be understood:

* Does a user need to be logged in?
* What data is required to create/update a record?
* What optional data is allowed?
* What (if any) are the data validation rules?
* Can a user retrieve/update/delete a record they didn't create?

This puts the Developer in the position of needing to figure out the Functional side of a feature (what it needs to do) while also trying to figure out the Technical side (how it does it). Since stakeholders aren't hanging around to answer every little question on the 'what' this means the Developer has to either:

* Wait around for an answer, delaying all their other work
* Pick up another ticket with the risk that new ticket also becomes blocked leading to spiralling cycle of backed up work
* Take a best guess with the risk of being "wrong" and having to redo the functionality.

A better approach is to have defined regular Feature Breakdown sessions with your stakeholders to ensure that you can get all the answers to those questions up front.

## What does good Feature Breakdown look like

Before we get into the methods I like using for Feature Breakdown (with examples) I think it's worth discussing what a well broken down feature looks like (so the later examples make more sense)

This is not "what makes a good story" (that's a whole other topic), but more "when is the ticket the right size."

### Solves a single Functional problem

For a feature to be well broken down, I believe that the ticket needs to be of the smallest practical size. Therefore my rule of thumb is that your final tickets should handle a single functional use-case. Another way of putting this is if you're looking at a user function that can either succeed or has three ways to fail, there should be 4 tickets: 1 for the happy path, and 1 each for the failure conditions.

Part of this comes from a study into [Test Driven Development (TDD)](https://en.wikipedia.org/wiki/Test-driven_development) that determined the 'test-first' mentality (probably) has less to do with quality benefits than the granular approach to the work.
>Conclusion: The claimed benefits of TDD may not be due to its distinctive test-first dynamic, but rather due to the fact that TDD-like processes encourage fine-grained, steady steps that improve focus and flow.  
>Source: [D. Fucci, H. Erdogmus, B. Turhan, M. Oivo and N. Juristo, "A Dissection of the Test-Driven Development Process: Does It Really Matter to Test-First or to Test-Last?," in IEEE Transactions on Software Engineering, vol. 43, no. 7, pp. 597-614, 1 July 2017, doi: 10.1109/TSE.2016.2616877.]((https://ieeexplore.ieee.org/document/7592412))

### Is a Vertical Slice

A ticket is a vertical slice when it contains all the work required to complete the feature across all the stacks - Frontend, Backend, Databases, etc.

The analogy I like to use is serving a piece of cake: you don't serve just the cake base, then the filler cream, then the icing last, you serve the whole slice with all the components together. Similarly in Software completing just the Frontend doesn't give the user a usable feature, all the components across all the stacks must be delivered for the user to get any value. From their point of view they want to perform some action and get some level of outcome from the system, even if that outcome is just a response saying something went wrong.

This works even in teams with stack specialists (i.e. Backend Devs separate from Frontend Devs, etc) as it helps ensure that all members are aligned on the expectations of feature even if they have their own tasks within it.

### Practically trumps all

Both the preceding points are ideals that I think you should strive for, but there will be plenty of examples where one or both aren't going to work for a feature. In the end Feature Breakdown can be just as much an art as a science - finding that sweet spot where a ticket is small enough to enable Developers to focus on the key technical challenges, without being so small as to be pointless. It will take some practice and experience with the systems to get it right, but it's a worthwhile endeavour to work towards.

Luckily I have two methods that can help guide you through the process

## Methods to do Feature Breakdown

---
Author's Note:  
The following section is a reworked version of a pair of Brown Bag videos I've given on this topic. Going into it I have the sneaking suspicion that the audio/visual aspect of those talks helped with these example heavy methods. If you're reading this note it means I wasn't able to translate this effectively to text with diagrams at a level I'm happy with, but I've gone with "perfect is the enemy of good" and released this as is while I figure out a better way of doing this.

---

### And Then

The simplest form of this method is splitting every time your feature description uses the word 'and'.

An initial requirement of:
> The user can do A and then do B

becomes two stories:
1. The user can do A  
2. The user can do B

This also works on all [sentence conjunctions](https://ctl.yale.edu/sites/default/files/files/GWC_LinkingWords-1.pdf), e.g: and, or, but

As an example let's take this mock Login page  
![Mock Login Page](/img/feature_breakdown/Login.png)

When we look at this page, we can describe it's functionality like this
>The user can login, *or* sign up, *or* have forgotten their password

We then break this down into 3 main features based on 'or'

1. Login
2. Sign up
3. Forgotten password

As we delve the next level deeper we can describe the login process as

> The user can login successfully, *or* if unsuccessful will get an error message

Which breaking it down gives us

1. Login  
   1. The user can login successfully
   2. The user can fail login with an error message
2. Sign up
3. Forgotten password

There are of course occasions where the use of a conjunction is still part of a single story, which we can demonstrate with the next level of detail on the Login feature.

When looking in to the details of the two login stories, they more appropriately become:

1. The user can login successfully *and* be redirected to the homepage
2. The user can fail login with an error message because they entered the wrong username *or* the wrong password

In my view both of these stories are at the correct level even though they have a conjunction, because they are vertical slices - i.e. from the user's point of view they are singular flows.

For the successful login flow we go back to vertical slices description where the user performs an action and expects an outcome. In this example The user enters their login details (performs an action) and if they have done that correctly they expect access to the system (the outcome), therefore this is a complete vertical slice.

The failure conditions are more complicated as they rely on the domain context, best practice, and expected effort to make the determination. When implementing a login screen it is [best practice to use the same error message](https://www.authgear.com/post/web-application-authentication-best-practices#single-failure-message) for a missing account as for an incorrect password. Thus while technically there would be two separate checks (one for username existing, another for password correctness) from the user's point of view they receive the same outcome for their action. Since the checks are also relatively simple to implement and will probably exist within same backend function, we gain nothing by breaking this into two tickets (except more tickets to manage) so we consider this a complete vertical slice.

### Zero, One, Many

As a method Zero, One, Many is really effective in any occasion where you are going to be dealing with lists of things. It helps by allowing you to focus one aspect of the display and interaction with the list:

* Zero, how does it behave when there's none of the thing?
* One, how does it behave when there's only one of the thing?
* Many, how does it behave when there's multiple of the thing?

For this example we're going to be "implementing" a playlist ala Youtube or Spotify.

#### Zero

![Empty Playlist Screen Mock](/img/feature_breakdown/Zero.png)

This is effectively creating the base case for the Playlist.  
 i.e. What does the screen look like when there's no items?

* Where does the title/description go?
* Where are the Playlist options/settings?
* Do we have a message saying "We didn't find anything for this list"?

From a Backend point of view this can include things like:

* Creating the basic API endpoints (probably returning hard coded empty lists)
* Creating the basic DB table relationships

It also is a good time to think about all the error conditions that could cause no items to appear:

* What if we can't find the playlist?
* What do we do if we're offline?

You'll notice that a lot of these examples fail the 'Is A Vertical Slice' test, because in dealing with the Zero case there's very little in the way of user functions being implemented. What you're focusing on here is all the things that might get forgotten about if you dived straight into implementing the list functionality.

#### One

![Single Item Playlist Screen Mock](/img/feature_breakdown/One.png)

In this case we're focused on the details around a single item in the playlist effectively templating ready for the 'Many' case.

So we're looking really closely at the information and layout associated with a single track

* What information are we displaying? E.g. Track Name, Arist, Play time, etc
* How are we displaying this information within the display component?
* How does the display component sit within the main list component?

The aim of the breakdown here is to ensure that you can engage your stakeholders effectively on what they need to see for the items in the list. Technically speaking these tickets should be creating the components/classes/types that you will instantiate in the 'Many' instance.

#### Many

![Full Playlist Screen Mock](/img/feature_breakdown/Many.png)

With the 'One' cases having dealt with the specifics of displaying the items in a (hopefully) extensible way, in 'Many' we are looking at the conditions that only occur when there are lots of objects. Issues like:

* Pagination
  * How many entries will our API return at once?
  * How do we request more entries?
  * How do we ensure the entries don't change order between paged calls?
* Ordering
  * Can we order by track name, play time, artist, album, etc?
* Searching (uses text input)
  * How can we search in the list for a specific song/artist
* Filtering (uses pre-defined categories )
  * Can we filter on genre, artist, year released, etc?

The examples so far focus on handling multiple songs in the list, but the 'Many' condition has multiple dimensions that you need to think about.

What if the user has multiple devices?

* Do we support concurrent updates to the Playlist?
* If Device A is currently playing the Playlist, and changes are made on Device B, what does Device A do?

What if there are multiple users?

* How do we handle access permissions?
* Do we need to start displaying who added the song to a Playlist?
* Do we need to notify everyone when someone makes changes?

## When to do Feature Breakdown

Short Answer: Constantly

Long Answer: Feature Breakdown should be done before you start the work on the feature, but you don't have to do it all at once.

Early in a project, you will need to do enough breakdown to understand the high level of the work to be done, but these features can still be rather large and missing a lot of the detail we've discussed above. Then as you come to implement each large feature you break it into smaller pieces that you are able to individually implement.

I've heard this described as Boulder, Rocks and Pebbles: The boulder is your project, which you break into Rocks (the large features), which are in turn broken down into Pebbles (the individual tickets to implement). Even with this analogy it might seem like you can or should do all the Feature Breakdown at the start of the project, but I think this is a mistake.

To demonstrate why, let's assume your building a [Japanese Rock Garden](https://en.wikipedia.org/wiki/Japanese_dry_garden) and you've had a boulder delivered that you're going to break down into the individual pebbles that will make up the garden.

In the upfront example you break the entire boulder into rocks, then into pebbles before you start loading the pebbles into the garden. It's at this point you realise the pebbles are too big for the garden you've designed, so you go back and do all the extra work to break all the pebbles into smaller pebbles. Then you realise you've made the pebbles too small, but you can't stick pebbles back together so you're stuck with dealing with them as they are. Think of these pebbles as tickets that are so small you spend just as much time moving the ticket on the board as you do implementing them - not fun.

If you approach the breakdown iteratively, you still break the entire boulder into rocks to ensure you have enough material but then only break down the first rock into pebbles. As you load that into the garden you realise these pebbles are too big, so for the next rock you make them smaller. These pebbles are now too small but taking the learning from the first 2 rocks, the 3rd rock's pebbles are exactly right. You finish the garden by breaking the remaining rocks into these right sized pebbles and you have delivered it (mostly) perfect.

## Final Thoughts

There are times when 'Feature Breakdown' can seem more like 'Feature Discovery' but working through these items ahead of time has many benefits. Simplest is that with all the Functional details sorted you can maximise your development time towards achieving that 'flow' state of highest productivity. It can also help the Product people make sure they've thought through all the edge cases of their product which not only protects you, buts helps demonstrate to them all the extra work that you do towards their products. Getting started with this process can seem slow at first, but it will help you develop better products, of higher quality, with greater satisfaction.
