---
layout: post
title:  "Vibe Rowing: How AI helped us row 4 million metres and raise over £20k for Sophia"
date:   2025-12-15 20:00:00 +0000
categories: general
---

![Sophia Clarke](/assets/images/sophia.jpg)

Sophia Clarke is a 3-year-old miracle. Born with Campomelic Dysplasia and requiring 24/7 life support, her needs are complex, and her care is costly.

Her family are part of the [CrossFit Pioneer](https://www.instagram.com/pioneertrainingni) community, and when our head coach Karl came up with the idea of a fundraiser to help renovate their home for Sophia's needs, the whole gym rallied around this incredible cause.

Karl's crazy idea was that we would row 3 million metres in one weekend.

We had eight Concept2 rowers. Over 1,000 half-hour rowing slots to fill, and a goal to raise £10,000.

## The Problem

One big question popped into my head: "How will we know how far we've rowed?"

When I see a problem like that, the builder in me kicks in.

I wanted everyone in the gym to be able to see the progress as we went. A big display showing live metres rowed, and ideally how much we'd raised in real-time. It was a chance to make something that turned our effort into visible momentum.

![Concept](/assets/images/concept.png)

Naturally, I massively overengineered it.

## The Original Plan

- Connect all 8 rowers via USB
- Stream live row data to a central hub
- Run a backend API to serve up distances
- Pull live fundraising updates from the GoFundMe API
- Display real-time totals on a TV

This looked great in my head.

![Original plan](/assets/images/original-plan.png)

## Reality Check

But I quickly realised: I have a full-time job, a toddler, a life. And I actually like to sleep.

I don't have 20 spare hours and a soldering iron.

So I did what I've increasingly been doing in my day job at [Bazaarvoice](https://www.bazaarvoice.com/) over the past few years: I asked an LLM to help.

I prompted something like this:

> "I have 60 minutes to build a dashboard showing our rowing progress. What's the simplest possible solution that hits the goal?"

I've found that giving LLMs tight time constraints helps them (and ultimately me) focus on the essentials.

I was amazed at how simply we could solve this. No backend or APIs: just a single HTML file and a Google Sheet.

![Actual solution](/assets/images/actual-solution.png)

Instead of trying to wrangle flaky USB rower data (and let's be real, processing that data with my even flakier code), we'd update a shared Google Sheet with the metres for each slot manually.

### A Simple Dashboard

A simple dashboard would:

- Display a live-ish total, ticking up gradually between updates with an estimation
- Show the donation total (also editable from the sheet)
- Auto-refresh with the latest true distance rowed from Google Sheets every 15 seconds

I gave ChatGPT a rough prompt and it generated a really clean dashboard UI in one go. It then helped me wire things up to the Sheet. I only made a few visual tweaks.

![Screenshot](/assets/images/screenshot.png)

We added a pacing config tab in the sheet, so we could estimate metre counts based on how many rowers were active. That way, the screen would keep ticking even before the next manual update.

## The Funny Bits

Some funny (but very fixable) bugs cropped up:

- We initially showed each rower's pace on the screen. People didn't love being the slowest on screen. 😅
- Our early estimates were too optimistic, so when actual updates were entered, the total went down, which was a bad demotivator.

The downside of running the HTML page locally off a laptop is that physical proximity is necessary to release any changes.

## The Event

![Event](/assets/images/event.jpeg)

The event kicked off at 6am on Friday 21st November. I expected we'd be rowing well into Sunday night, or maybe even Monday.

The energy in the gym was unreal, and we managed to hit 3 million metres by 11pm on Saturday.

After that, we just kept going (on coach Karl's orders).

By Sunday afternoon, the total hit 4 million metres.

We smashed through the £10k fundraising target. As of writing, over £23,000 has been raised to help Sophia and her family!

## The Dashboard Legend

![Live dashboard](/assets/images/live-dashboard.jpg)

The dashboard became a bit of a legend that weekend.

Everyone rowed harder watching the numbers tick up. Coaches updated the spreadsheet. The big screen reacted. The group chat was pinging with photos of the latest count from the gym.

That scrappy HTML file, built in just a couple of hours, kept over 100 people rowing together towards a shared goal.

## The Lesson

Sometimes, it doesn't take much code to make a massive impact.

Will I open source it? Probably not, at least in its current state!

To be honest, the code is very scrappy and unpolished. But it worked.

And it worked better because I scoped it ruthlessly.

I used AI to accelerate, cut complexity, and build something that delivered real value.

All in all, this project reminded me that the fastest way to build something great is often to build less.

## Support Sophia

If you want to help out, it's not too late to support Sophia and her family.

[Click here to donate to the fundraiser.](https://www.gofundme.com/f/sophia-clark-one-in-3-million)
