---
layout: post
title: 'Major Project: Sprint 4 - Planning'
date: '2016-04-02 23:18:25'
tags:
- university
- university-major-project
---

As the deadline is fast approaching, I need to get a move on. <abbr title="Create, Retrieve, Update, Delete">CRUD</abbr> functionality for projects and user stories must be implemented first of all. Then, support for creating sprints must be added, as well as the user controls for adding those sprints to the server.

However, as I was slowed down so much by setting up the unit testing in the last sprint, I'm worried I will have the same problems for this sprint. The current version of Ember CLI Mirage does not support the way JSON data is presented in the JSON API (the next version does, but it's still in beta), so hopefully I'll be able to get around that.

## Goals for this sprint
* CRUD functionality for projects
* CRUD functionality for user stories
* Creation of sprints
* Styling

## How will it get done?
To solve the Mirage issue, I could seed in some development data to the server-side application, copy what fortune.js outputs and paste it into Mirage's test data. Seems dodgy, but it would work.