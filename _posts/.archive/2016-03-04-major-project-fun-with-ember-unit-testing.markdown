---
layout: post
title: 'Major Project: Fun with Ember unit testing'
date: '2016-03-04 16:24:02'
tags:
- university
- university-major-project
---

*'Fun' being ultra-sarcasm for 'not fun'.*

One thing that's 'nice' about Ember is that it uses QUnit for automated testing. Well... that genuinely is nice. Ember provides by default a fantastic testing infrastructure using common testing tools like QUnit and PhantomJS.

However, one thing that's not nice at all is the varying degrees of documentation for it. There are some fantastic guides about generally using them, but I've been struggling to find any documentation at all on the helper functions that you can make use of in these tests. I'm calling methods from `this`, but I have no idea what the `this` object refers to.

If JavaScript was statically typed, this wouldn't be an issue, but that's a whole other discussion. I'm having trouble finding an actual list of methods in the API docs that match up with the methods I'm calling from `this`.

Another annoying thing is that PhantomJS seems to use an old version of WebKit, as far as I can tell. It took me a while to realise that was why using the `String.prototype.includes()` method wasn't working. It seems its support for certain ES2015 features is patchy. (But thanks to the [ES2015 Compatibility Table](https://kangax.github.io/compat-table/es6/) for helping me to figure it out.)

&lt;/moan&gt;