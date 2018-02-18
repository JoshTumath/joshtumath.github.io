---
layout: post
title: 'Major Project: Sprint 3 - R&R'
date: '2016-04-02 22:50:28'
tags:
- university
- university-major-project
---

## Review
Oh dear. What has happened? This sprint started 21 days ago, and I'm two weeks late posting this R&R. The Easter holidays were partly to blame for that, but I was also grappling with some very annoying bugs, but more on that in a bit.

Firstly, I should talk about the Mid-Project Demo, which I think went well. I'd prepared some UI wireframes over the weekend to present, as well as a code demonstration. My Second Marker seemed impressed with my work, and my mark for the presentation was 80%.

Now, onto the development work. I had been very ambitious with this sprint, and had not realising some of the server-side set-up would take so long, so I didn't complete the sprint functionality in the Ember app.

So basically, I did the following (not necessarily in this order - some things were worked on at the same time):

1. *Sort out the basic setup of the Web server.* I decided to use [express.js](http://expressjs.com/) the Web server, as it is the most widely used server library for Node.js. I then needed to figure out how to structure the code for the server in such a way that would be suitable for an Ember application. I ended up using a `public/` directory for storing the built app, as this directory was reserved specifically for serving static files (like HTML and JS files). I also had a routing file for routing HTTP requests to the `index.html` file in the `public/` directory.
1. *Find a way to automatically build an Ember application in order for it to be served over the Web server.* I wanted to have the Ember application and the server-side code stored in the same Git repository, and then build itself automatically if the repository is cloned onto a server. However, this proved complicated, and I ended up storing the server code in a separate repo. I also created a build script that would automatically download the Ember application and build it in the server's `public/` directory. This took a considerable amount of time to work it all out, and took a while to get it to work on Travis.
1. *Find a suitable [server-side implementation of the JSON API](http://jsonapi.org/implementations/#server-libraries-node-js) to use.* It needed handle as many aspects of the API for me as possible to save me time, and be compatible with MongoDB. I spent a while trying different solutions. I ended up choosing [fortune.js](http://fortunejs.com/), which handled <abbr title="Create, Retrieve, Update, Delete">CRUD</abbr> operations, the URL structure, error handling and interfacing with the database. Perfect! However, I was hesitant to choose it at first, because, while it seemed the most robust, it was poorly documented.
1. *Sort out the testing infrastructure for the server.* I needed to manually set up a unit testing strategy, as I wasn't using a particular framework for the server itself. While I wanted to be consistent with Ember's testing strategy, it used bespoke infrastructure. I noticed that [Mocha](https://mochajs.org/) seems to be the most popular for Node.js applications, so I set that up and configured Travis to use it. I originally had Travis run the Ember application build script, but later realised that won't be necessary as I will only be needing to test APIs. 
1. *Set up fortune.js*. The library is nice in how it handles so many functions. All it requires is a list of models for each database collection, a handler for interfacing with MongoDB and a handler for interfacing with the JSON API. However, it ended up being quite tricky to set up. The documentation sometimes made things unclear, and it sometimes failed to pass errors to explain why things like communication with the database weren't happening. I was also frequently getting errors where it was very unclear from the error messages what was causing them. However, now that it's all set up, it will be very simple to expand the store in future sprints to add additional models for new types of data.
1. *Test the GET operations for fortune.js* The Mocha unit tests firstly set up an instance of the Web server. I found a commonly used library called [supertest](https://github.com/visionmedia/supertest) for sending requests to the Web server and checking if the content that is returned back is what's expected. This took time to set up and make sure that my code was <abbr title="Don't Repeat Yourself">DRY</abbr> (no duplicate code) and as reusable as possible for when writing future tests. There would be times when errors were being thrown while running the tests, but not from the browser when the server is running.  For example, one that kept bugging me was a `TypeError` relating to an internal `header` property, and it was unclear as to why it was happening, or what `header` even referred to.

As a result of the chain of complications I came across while setting this all up, I was determined to get it all sorted rather than keeping to the Scrum process. That is why this sprint has ended up being three weeks long.

Having reflected on what I have achieved in the past three weeks, I realise it is actually a lot, but it doesn't feel very substantial for the time I had. I am nearing the final deadline for the Major Project, and there is still a lot of functionality left to implement.

## Retrospective
### What went well?
* I have ended up with what I believe to be quite robust code. (I had been refactoring the code as I worked on it.)

### What could be improved?
* I did not keep to the scrum process. I did not end the sprint when I should have, so I should be more strict about this in future.
* I wasn't documenting when things were going wrong and why they went wrong. I just kept hacking away until it worked. So in future, I should draft my R&R blog posts in advance, noting down problems as they happen.

### Things to think about
* Is using Mirage still necessary, now that I have the server-side set up?