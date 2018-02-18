---
layout: post
title: 'Major Project: Mid-Project Demonstration'
date: '2016-03-14 13:09:00'
tags:
- university
- university-major-project
---

<script async class="speakerdeck-embed" data-id="bd1dd8ca87714cfba609e4953f0c35ea" data-ratio="1.77777777777778" src="//speakerdeck.com/assets/embed.js"></script>

This is a presentation that I gave to my Second Marker, explaining what my project is about and my development progress. I also gave a demonstration of the Ember application running.

I've included below my notes for the presentation, which was expected to be no longer than 10 minutes.

## Background
*1.5 minutes*

* I’ve worked at two agencies, seen problems
* What’s a digital agency?
    * Small to medium sized business
    * Web design, small mobile app development, SEO, marketing, branding
    * Normally targeting small local businesses
* How do they develop software?
    * Designer + developer. Small teams – normally developers work solo
    * Always use waterfall type of methodology
        1. One meeting to get requirements and choose CMS
        2. Visual design made
        3. Implemented quickly
        4. Client approves implementation
        5. Website given to customer or hosted on agency’s own web server
    * Very hard to respond to change. Not budgeted. No time. Strict deadlines that are hard to meet.
    * No slack time.
* Clear benefits moving to agile, respond to change, less pressure

## Project description
*2.5 minutes*

* Agile project management system
* Aims:
    * Aid agency staff in time management, while making sure their interactions with the application are short and without lag or delays.
    * Give agency staff flexibility between projects and support queries.
    * Track project requirements using agile methods.
    * Facilitate regular communication between agency staff and customers.
* Features:
    * User stories for requirement tracking
    * Support tickets (pestering developers to deal with them) and sidetracking
    * Calendar with sprints and deadlines, seeing how sidetracking affects deadlines
    * [show wireframe]
* Development methodology:
    * Using Scrum
    * Weekly sprints, see supervisor on Thursdays for review and next sprint planning
    * User stories for tracking requirements
 
## Technical work and issues
*3 minutes*

* Single Page Application
* Using Ember
    * Node.js to transpile
    * Babel for ES2015
    * Integrated automated testing suit, QUnit, etc
    * Mirage to simulate server requests
    * [explain diagram]
    * [demo]
* Using RESTful JSON API
    * De facto standard
    * Libraries for both client and server
* Server-side
    * Investigating in current sprint
    * Node.js, Express, MongoDB (NoSQL)
    * Decide on JSON API library
* What I’d do differently
    * Mirage is version 0.1 – wish I implemented server-side earlier
    * (discuss alternatives of Ember)

## Remaining work
*1 minutes*

* Features
    * A persistent storage system on the server-side using MongoDB
    * JSON API on server-side
    * User account management
    * Calendar of work schedule
    * Creation of support tickets
    * Allowing agency staff to pause their current work to deal with support tickets
    * Live updates as information such as user stories and calendars are changed by other users
* Usability tests

## Extra
*Answers to potential questions*

* Future work:
    * An add-ons platform to enable digital agencies to add other features, such as an invoicing system.
    * An API to use live data from SmallScrum. This would allow digital agencies to create bespoke information radiators, among other possibilities.
    * Enable the application to work offline in certain situations, such as when creating user stories or viewing the user’s calendar.
