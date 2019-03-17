---
layout: post
title: 'Major Project: Sprint 1 - R&R'
date: '2016-03-03 13:12:05'
tags:
- university
- university-major-project
---

## Review
Much of this week was spent on [the conference poster](/2016/03/01/major-project-conference-poster/), but this sprint also focused on authentication. I used the [Ember Simple Auth](https://ember-simple-auth.com/) package for this. Initially, it was quite complex to set up ironically, but was straightforward once it was working. The experience showed me how Ember can sometimes be quite unhelpful with how it presents errors. However, using Mirage was useful for setting up a fake oauth2 response message. I will later be able to use the package for verifying authorisation as well.

I've also done a little bit of design work for the website. It is nowhere near the final design, but is a rough design just for during development.

## Retrospective
### What went well?
* Poster was completed on time.
* Despite complications, the authentication is now sorted with a fake backend using Mirage.

### What could be improved?
* My focus and time management with the project. I was once again delayed; this time by a weekend away in Aberporth, a friend's birthday, workshop demonstrating and a BCS lecture.
* So far, I haven't been practising <abbr title="Test Driven Development">TDD</abbr> (partly because I've been starting off). The login functionality needs tests!

### Things to think about
* Look into using components instead of controllers for the login functionality in Ember, as [controllers are being deprecated](https://guides.emberjs.com/v2.4.0/controllers/).
* How would oauth2 authentication be set up on the server side?