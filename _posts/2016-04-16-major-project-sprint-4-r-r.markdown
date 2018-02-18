---
layout: post
title: 'Major Project: Sprint 4 - R&R'
date: '2016-04-16 18:03:44'
tags:
- university
- university-major-project
---

## Review
Once again, this week was full of unexpected problems in part due to the technologies I'm using for the project.

I realised I wasn't building the Ember application in the production environment, so I corrected that. But when I did that, the outputted pages appeared blank when loaded into a Web browser. (I can't even remember how I fixed it!)

I attempted to begin work of the remaining CRUD functionality for the project and user story pages. However, I immediately realised that Ember CLI Mirage is still too immature as a library to easily and quickly support Create and Update functionality with the JSON API.

Therefore, I made a separate branch to remove Mirage and create a mock server (using Ember's 'http-mock') that basically duplicates the actual production server. That began a nightmare of things to sort out:

1. Acceptance tests for the `/projects` page were failing, due to issues with authentication. I eventually realised that it was failing to connect to the oauth2 page on the http-mock server. 
2. I then realised that the http-mock server does not seem to launch when running unit tests, even though Mirage did. The documentation also implied that it should. This issue took a while to solve. I submitted an issue report to the Ember CLI repo on GitHub, but it eventually became apparent that I would need to manually launch the mock server's code myself to use for unit testing. I tried to find ways to automate this in a cross-platform way with scripts, or by using `before` and `after` hooks in the unit testing system. This was to no avail, due to bugs with the ember-beautify package.
3. I eventually did the following: I simply launched the server myself manually in one terminal window, and then launched the unit testing in another terminal. But this wasn't possible to do on Travis where only one terminal can be run. But that was fine, because Travis did not run on Windows, so I was able to use `npm run-script test-server &` to launch the http-mock server in parallel.
4. The solution worked, but the test was still failing because the AJAX requests to the server still did not use the correct port. Therefore, I had to modify the configuration settings for each addon package that made an AJAX request so that they sent the request to the correct host. Ember Simple Auth gave me the most problems, because it seemed to ignore my setting. I had to [submit a pull request to get it fixed](https://github.com/simplabs/ember-simple-auth/pull/955).

The CRUD functionality for project pages had its own set of problems:

1. Due to the way Ember's templating system works, the form for creating/editing projects had an odd behaviour. When editing the name of a project in an input box, your changes would instantly be reflected on the page's heading. But this was misleading, as it made it appear as if changes were saved immediately, which was not the case. Users still had to click the 'Submit' button to permanently store the changed data. Therefore, I had to do a deep copy of the string values so they weren't sharing the same pointer with the content of the page.
2. Deletion was difficult to implement, because once you delete a page, it no longer exists. Ergo, errors occur when Ember tries to update the page and realise it no longer exists anymore. Ergo, the code is halted before I have a chance to redirect the user off the page. Therefore, I had to refactor the action handlers for the form component so that communication was not done within the component itself. Ember has a concept of allowing actions to 'bubble up', so that if there is no action handler for 'delete' in the page's controller, then it bubbles up to the page's route to see if it is handled there instead. However, for some reason, this was not the case with components. A component is completely isolated. There were two ways to solve this:
  1. A closure could be used to pass a pointer to a controller's action into a component. That way, the component would be able to call the controller's action. However, I was storing the actions in the route, not the controller, because [controllers are going to be deprecated in a future version of Ember](https://guides.emberjs.com/v2.5.0/controllers/). Therefore, I decided against doing this.
  2. It was possible to [pass in a property called `target`, which would make everything magically work](http://stackoverflow.com/a/33877726/1838865), although this technically went against the idea of components. Option 1 is the preferred option, but it seemed as though there were good enough reasons not to use option 1.

So it's been yet another interesting week!

## Retrospective
### What went well?
* I was able to complete the background section for the report.

### What could be improved?
* To speed up development, I will no longer be practicing TDD to the problems stated above. I will hopefully have time to add tests post-development.
* Reflecting on my experience with this project as I approach the deadline with not much functionality implemented, I regret choosing Ember as the base platform for the project. I should have gone with something simpler and lightweight that I'm familiar with. That would have allowed me to get stuff done more quickly. Perhaps if Ember was 

### Things to think about?
* How do I discuss original research in my dissertation write-up (talking about personal experiences working in digital agencies)?
* What should I focus on now that time is running out to complete the project?