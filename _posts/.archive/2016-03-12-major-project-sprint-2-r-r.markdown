---
layout: post
title: 'Major Project: Sprint 2 - R&R'
date: '2016-03-12 01:14:19'
tags:
- university
- university-major-project
---

## Review
Once again I didn't have much time this week as I was at an assessment centre for a role at the BBC (which went very well 😃), so that took away two days of development time. However, I was still able to get a lot done.

The software now has models, routes and templates for project and user story pages. I also added a 404 page, which was nice and easy to do.

This work took much longer than I expected, due to complications with routing and automated tests, as well as strange bugs that cropped up. One odd bug was that, when clicking on a user story to open, the label for that user story would change to the name of a project with the same ID number. Strangely, the bug was fixed by passing in the model for individual user story pages.

However, I am finding it increasingly difficult to simulate the server-side persistent data with Ember CLI Mirage. I have to support the JSON API manually, and it's not obvious how to represent relationships without understanding the [specification](http://jsonapi.org/format/). The whole point of the JSON API is that it saves you from needing to worry about this kind of stuff. Apparently the next version of Mirage supports the JSON API, but it is still in beta and unavailable on NPM.

I did not have time to work on viewing sprints, so that feature will have to be deferred to a future sprint.

## Retrospective
### What went well?
* Gained a better understanding of how routing works in Ember.

### What could be improved?
* I was not able to complete everything in the sprint on time, so better work load estimation is needed and better time management.
* So far, it's been difficult to practice <abbr title="Test Driven Development">TDD</abbr>, as Ember is still too unfamiliar. Hopefully in the next sprint I will have a better understanding of the testing infrastructure. 

### Things to think about
* How can I better make use of automated testing in Ember?
* How can I simulate relationships in Ember CLI Mirage, as the concept is not supported natively in this old version? Would it be more helpful to start doing the actual server-side implementation now?