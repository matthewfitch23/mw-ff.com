---
layout: post
title: "The simplest thing that actually helps"
date: 2026-10-06 09:00:00 +0100
categories: general
---

In December, I wrote about the dashboard we built for a rowing fundraiser. My original plan involved connecting eight rowers over USB, streaming their data to a backend, and pulling in live donation totals.

The version we actually used was a single HTML file and a Google Sheet.

That difference is worth another post, because “build less” sounds sensible until you’re the person with an idea and an editor open.

## Simple still takes thought

The original plan wasn’t completely unreasonable. Reading directly from the rowers would have saved people from entering distances manually. A backend could have made the data easier to manage. Automatic donation updates would have been nice.

Each part had a justification. Put them together, though, and I had given myself a much bigger job than the event needed.

We needed people in the gym to see how far we’d rowed. Coaches could update a spreadsheet. The screen could read it. That was enough to get started.

The difficult bit was accepting the manual step. As a software engineer, it feels slightly wrong to ask a person to do something a computer could do. But the computer’s version comes with work too: building it, testing it, handling the ways it fails, and being available when it stops working.

For a weekend fundraiser, typing a number into a sheet was a reasonable trade.

## AI needs a boundary

The useful prompt was roughly:

> I have 60 minutes to build a dashboard showing our rowing progress. What’s the simplest possible solution that hits the goal?

The time limit gave the conversation a boundary. Without one, there was plenty of room to keep discussing a more complete system.

I think this matters when using AI to build software. It’s easy to ask for another feature when generating the first version costs so little effort. Add a settings page. Support another data source. Make it configurable. Each suggestion sounds small.

But I still have to understand the result. Someone has to check that it behaves properly, and someone has to deal with it later.

I’d rather use AI to help question the scope before asking it to write the code. Which part of this needs to exist? Could a spreadsheet do it? What would we lose by leaving this feature out?

Sometimes the answer will justify the bigger build. It should at least get a hearing.

## The rough edges that mattered

Our dashboard had bugs. Early estimates were too optimistic, so the total sometimes went backwards when someone entered the actual distance. We also showed individual rowing pace, which wasn’t much fun if you were the slowest person on the screen.

Those were worth fixing because they affected the people using it.

An imperfect estimate was tolerable. A number visibly dropping after someone had worked hard was discouraging. Individual statistics sounded useful while building the dashboard, but the event was about a shared effort.

That’s a more useful way to judge a rough first version than asking whether the code is polished. You can tolerate plenty of untidiness behind the screen. You need to pay attention when the untidiness becomes someone else’s problem.

A small build still needs care. It just lets you spend that care on fewer things.

## Leave yourself a way to stop

One thing I like about a narrowly scoped project is that it can be finished.

“Build a rowing platform” has a long list of possible next steps. “Put our total distance on the TV for this weekend” has an end.

There’s room for both kinds of work. Some tools deserve to become products. Others can do their job and stay scrappy. I don’t think every useful thing needs a roadmap.

Before starting the next small project, I’d like to be able to finish this sentence:

> This is done when someone can…

For the rowing dashboard, it was when someone could look up at the screen and see our progress without finding a coach and asking.

That leaves out a lot of technically interesting work. It also makes it much easier to decide what to build on a spare evening.

The dashboard helped because people could use it that weekend. An elegant system still sitting on my laptop wouldn’t have been much use to anyone.
