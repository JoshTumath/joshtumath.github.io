---
layout: post
title: 'Major Project: Sprint 0 - R&R'
date: '2016-02-25 00:25:00'
tags:
- university
- university-major-project
---

##Review
The first sprint is done! A staging server has now been set up using nginx, which can be found at [smallscrum.joshtumath.uk](https://smallscrum.joshtumath.uk/). I have also [laid out in a blog post](/2016/02/24/major-project-comparison-of-frameworks-and-platforms/) my desires for what technologies I believe would be best for the project and investigated the most appropriate framework to use. I have chosen to do the development with [Ember](http://emberjs.com/). I have set up a private GitHub repository for the project (my supervisor recommended not to make it public for now) with Travis CI connected up for doing continuous integration.

However, I have not set up any server-side technologies (e.g. database and logic layer) as I originally planned. I am still unfamiliar with how best to go about it, but I do know that I will use the *de facto* standard [JSON API](http://jsonapi.org/) for client-server communication. By using this standard API, I don't have to worry about what server back-end I use. Until I need to decide, I can use [Ember Mirage](http://www.ember-cli-mirage.com/) to fake data from the server.

## Retrospective
### What went well?
* All the foundational work for the rest of the project is now completed.
* Although I was not able to settle on a server-side environment, I am able to work around that easily.

### What could be improved?
* My focus and time management with the project. I have been delayed by loads of unexpected external factors, like: having to work on a coding task for a BBC assessment centre, my car having its MOT and then breaking down a couple of days later, domestic tasks, shopping, social events, visiting family, workshop demonstrating and moving to a new phone contract. But life is full of distractions like that, so that's no excuse. I need to find a better way to manage my time.
* Deploying Ember code that's been built is currently quite tedious. It would be good to eventually use either the [Ember CLI Deploy](http://ember-cli.com/ember-cli-deploy/) script or Travis CI to automate uploading it to the staging server.

### Things to think about
* How should I represent my design planning for the rest of the project? Do I need to use CRC cards and the like? The specification for the final report requires a design specification in an appendix.