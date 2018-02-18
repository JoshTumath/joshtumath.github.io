---
layout: post
title: 'Major Project: Starting off'
date: '2016-02-02 02:14:13'
tags:
- university
- university-major-project
---

As of last week, I officially started my [Major Project](//www.aber.ac.uk/en/modules/2016/?m=CS39440) (dissertation) for my final year at University. During this semester, I have almost all of my time dedicated to my project, which is *Software to aid digital agencies in applying agile methodologies*.

## What's a digital marketing agency?
It's a small to medium sized business that offers services like Web design, small mobile app development, <abbr title="Search Engine Optimisation">SEO</abbr>, marketing and branding. While their name implies all they do is marketing, they are most of the time called on for their software development services. If you're a local letting agency who needs a website and mobile app for listing their properties, digital agencies are normally the cheapest option for you. Though they tend to be small, local companies, it can be big business!

One reason why they are relatively cheap compared to large software engineering companies is that only one or two [designers and developers](https://en.wikipedia.org/wiki/Digital_marketing_engineer) normally get assigned to a project. Additionally, the work tends to be charged per hour (sometimes with an additional surcharge).

## How do they normally develop software?
As far as I know, every one of these companies uses a variant of the [waterfall model](https://en.wikipedia.org/wiki/Waterfall_model) for plan-driven development:

1. There is a meeting to discuss with the client what they want. A proposal is made. The client approves the proposal.
2. A visual design is made for the system by one designer in a program like Photoshop. The client approves the design.
3. An implementation is made and hosted on a staging server by one developer. The implementation is quality-controlled. The client approves the implementation.
4. The website is released, and is either hosted on the agency’s server or handed over to the client so that they can host it elsewhere.

I'm quite familiar with the project lifecycle of digital agencies, having worked at both [Clicky Media](https://clicky.co.uk/) in 2013 and [GloverSure](http://www.gloversure.co.uk/) between 2014 and 2015. The former portrayed itself as quite a premium digital agency, offering a wide range of services. The Web team (or 'geeks' as we were amusingly called) made up about a quarter of the staff in the company and tended to be college graduates. The latter focused more on the development side, charging a cheaper hourly rate offering a smaller, more focused services. About 20% of staff were designers and 70% were University graduate developers (the rest were managerial). The ways that both these companies approached everything was quite different, but both used a waterfall model and suffered from all of the problems associated with that.

## What are agile methodologies?
The waterfall model and other similar development methodologies have a common problem of making it very difficult and costly to adapt to change. There are many development methodologies and frameworks trying to solve that, which come under the umbrella of 'agile development'.

Generally, these methodologies like [XP](https://en.wikipedia.org/wiki/Extreme_programming) and [Scrum](https://en.wikipedia.org/wiki/Scrum_%28software_development%29) try to split up work into short iterations, where something is completed at the end of the iteration. This is different to waterfall, where everything to be done is planned from the beginning, all development is done at the same time and the process ends with a large release.

To ensure that these quick releases of agile development do not lower the stability of the software, there are many practices that are followed. These include: [continuous integration](https://en.wikipedia.org/wiki/Continuous_integration) (with build automation and automated testing to ensure that each integration doesn't cause regressions), unit testing, pair programming, <abbr title="Test Driven Development">TDD</abbr> and refactoring.

## So how do you do agile in a digital agency?
Well that's what I'm going to have a go at figuring out. It's not easy for the following reasons:

* Since it's unusual to have more than one Web developer and one Web designer on a project, developing in teams is not possible. While a customer may have many staff involved with their project, they will be working on the project at different times and specialise in completely different areas to each other. (So we can't expect a social media marketer to be pair programming with a Web developer!)
* In a large software engineering firm, a team of developers will be focused entirely on a project until it's 'done' - potentially indefinitely. However, digital agencies tend to have few developers, and they may need to jump between projects a lot. They handle support and maintenance for websites, in addition to development for new projects. It's not unusual for a customer to suddenly call up to kindly let a developer know that their website has exploded and that for every second their website is broken, they are losing £1 trillion of revenue per second and it needs to be fixed urgently. Staff regularly need to be taken away from their usual projects to deal with bug fixes and small feature requests.
* Staff burnout is common, because they must be continually focused on every project they work on. Breaks are generally not encouraged.

I can only imagine that any attempt to peel a digital agency away from their current workflow would be somewhat costly. Any attempt to introduce [slack](http://www.everydaykanban.com/2012/07/27/slack-is-not-a-dirty-word-how-slack-can-improve-your-products/) or other common agile concepts into their workflow would increase development time. However, I am just speculating. I hope to find a way to introduce agile concepts into a digital agency's workflow without causing them too increase their charges too much. (One might argue that: because agile methodologies are more adaptable to changing requirements, customers will be less likely to request costly changes to their projects near the end of the development.)

## What will you produce in this Major Project?
I will be creating an agile project management system that will be specifically targeted at digital marketing agency staff to aid them in using agile practices as part of their software development methodologies. I will also be producing an example of a methodology that a digital agency might follow while using the agile project management system.

In order to get a rough idea of how this software I am producing can meet the needs of a digital agency, I hope to contact some agencies to query them on their current development methodologies. I have already been trying to contact a few digital agencies to discuss their project lifecycle with them, but I have so far received the same response: 'Too busy'. This is unsurprising due to the inflexibility of their methodologies. Plus, being small businesses, they tend to be more reluctant to allow for slack.

And that's it! Over the next 13 weeks, I will be spending much of my time on this project, and plan on blogging at least weekly about my progress.