---
layout: post
title: 'Major Project: Determining the development environment'
date: '2016-02-24 01:04:41'
tags:
- university
- university-major-project
---

The main focus of my current sprint is to work out what environment I will be using for the implementation of SmallScrum.

## My criteria
### Server
I would like to be able to run the application on a <abbr title="Virtual Private Server">VPS</abbr>, for which I will have complete freedom to configure any Web server, programming language runtime, <abbr title="Database Management System">DBMS</abbr> and framework. I already own two VPSs - one used by this website and one not currently used. I can also acquire a [DigitalOcean](https://www.digitalocean.com/) VPS if need be, thanks to the [GitHub Student Developer Pack](https://education.github.com/pack).

Whatever hosting provider I chose, I intend to use [nginx](https://www.nginx.com/) for the Web server, because it has excellent support for HTTP/2.0 and is known for being robust, speedy and performant.

### Language
I would prefer to use either PHP, JavaScript/TypeScript (with Node.js) because I am highly experienced with both of these languages. However, I may also consider Java and Ruby. (I'd love to be able to create the project using [Rust](https://www.rust-lang.org/), but I'm not willing to have many sword fights with the compiler, given the time constraints.)

### DBMS
If I require a relational database, I would like to use PostgreSQL, as it is known for being robust and generally very compliant with the SQL standards. I am generally very experienced with SQL commands.

However, I am also very willing to consider NoSQL alternatives provided they are robust and have good documentation, as I have never used one before. MongoDB springs to mind as a common choice for NoSQL databases.

### Server-side framework
I would like to use a framework to help me with the development. Ideally, the framework would provide me with a system for unit testing.

### Client-side
I am using a user-centred design process for creating the application, so I'm very focused on the user experience. Whatever set of Web technologies I chose to use to implement the client-side of the application must enable me to create a *delightful*, *polished* and *very snappy* user experience.

Ideally, the technology stack will enable me to provide the following:

* Must support [Single-Page Applications](https://en.wikipedia.org/wiki/Single-page_application) (SPA). In other words, loading content through [AJAX requests](https://en.wikipedia.org/wiki/Ajax_%28programming%29) to help ensure that content is snappy. The [Web History API](https://developer.mozilla.org/en-US/docs/Web/API/History_API) should be used to make sure the URL is still correct and that the browser back button still works. One of the goals of the application is to make sure developers aren't annoyed by the sluggishness of loading pages. Even a 500 ms delay is not good enough.
* [Progressive Enhancement](http://) to ensure the application is still usable if users have JavaScript disabled or if they are on old browsers. While we can expect digital agency staff to be using the latest versions of Web browsers, their customers may be on an old IT system with strict security policies that restrict certain content. (This requirement is good practice, but may not be essential.)
* [Responsive Web Design](http://) to ensure the application can be used on a wide range of devices. However, I am currently unsure if any users are likely to interact with the application using a smartphone or tablet. (This requirement is good practice, but may not be essential.)

## Investigation into frameworks
<table>
  <caption>A comparison of possible frameworks and how they match my criteria.</caption>
  <thead>
    <tr>
      <th>Name
      <th>Language
      <th>Persistent storage
      <th>Built-in unit testing
      <th>Supports <abbr title="Single-Page Application">SPA</abbr>s
      <th>Compatible with <abbr title="Progressive Enhancement">PE</abbr>
      <th>Comments
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Laravel
      <td>PHP
      <td>MySQL<br>
          PostgreSQL<br>
          SQLite
      <td>✓ (PHPUnit)
      <td>✗
      <td>✓
      <td>Excellent documentation.
    </tr>
    <tr>
      <th>Symfony
      <td>PHP<br>
          Twig
      <td>MySQL<br>
          PostgreSQL<br>
          SQLite<br>
          MongoDB
      <td>✓ (PHPUnit)
      <td>✗
      <td>✓
      <td>Robust.
    </tr>
    <tr>
      <th>Backbone.js
      <td>JavaScript (node.js)
      <td>Database via RESTful API
      <td>✗
      <td>✓
      <td>✗
      <td>Good server communication.
    </tr>
    <tr>
      <th>Angular2<br>
      (<abbr title="Mongo, Express, Angular, Node.js">MEAN</abbr> stack)
      <td>TypeScript
      <td>MongoDB
      <td>✗
      <td>✓
      <td>✗
      <td>Excellent documentation. Very flexible. Immature platform.
    </tr>
    <tr>
      <th>Ember
      <td>JavaScript<br>
          Handlebars
      <td>Database via RESTful JSON API
      <td>✓ (QUnit)
      <td>✓
      <td>✓[^1]
      <td>Excellent documentation.
    </tr>
  </tbody>
</table>

[^1]: Supported with [Fastboot](https://github.com/tildeio/ember-cli-fastboot), a first-party add-on that is currently in active development.

### Server frameworks
[**Laravel**](https://laravel.com/) and [**Symfony**](https://symfony.com/) are perhaps the most well known and widely used PHP frameworks. Laravel in particular is comparable to Ruby on Rails in how it generally works. However, these are not specifically designed to facilitate the back-ends of <abbr title="Single-Page Application">SPA</abbr>s, so they would be unsuitable for use in this application. Frameworks in this category (which I will call *server frameworks*) are only focused on generating pages purely on the server-side, and are not worth looking into.

### Templating frameworks
A type of framework that has gained traction in recent years is one that pushes as much as possible of the processing onto the client-side. They allow the logic-level code to be written in JavaScript, with communication to the server purely to access the database. These are generally known as *templating frameworks*. They tend to be written in JavaScript, and structure the codebase similar to server frameworks. However, they can be transpiled to a form that is suitable to be deployed to a Web server. Typically, communication with the server is done via RESTful APIs, once the initial request for the content on the index page has been sent. There is now even a *de facto* standard for the API used for this client-server communication, simply called the [JSON API](http://jsonapi.org/). By using this standard, I wouldn't have to create a bespoke solution for handling the REST calls on the server-side due to the many [libraries](http://jsonapi.org/implementations/#server-libraries) available.

Angular.js is a common templating framework. I was trying out [**Angular2**](https://angular.io/), which is the successor to the first version that is very widely used. I liked how it used TypeScript instead of plain JavaScript (I'm a static typing fan). However, its capabilities seemed to be much more limited compared to other frameworks like Ember - focused mainly on generating views. Also, it appears to do very little in the way of transpiling the code to a format that is suitable for the Web; older browsers would struggle. As it is a complete re-write of the original Angular.js framework, it's not as stable. Also, an available library for facilitating server communication via the JSON API is in development and not stable.

Ember is another widely used framework. I particularly liked using Ember, and found its [code structure](https://guides.emberjs.com/v2.3.0/getting-started/core-concepts/) to be very simple. It also provided a command line tool with code generators, similar to server frameworks like Ruby on Rails. There was also built-in unit testing infrastructure and built-in support for Babel (a tool that backports ES6 and ES7 code to ES5). It's also very extensible. Notable add-ons include: [Mirage](http://www.ember-cli-mirage.com/) for prototyping communications with the server, thereby removing the need to develop the server-side code at the same time as the client-side code; [Deploy](http://ember-cli.com/ember-cli-deploy/) for automatically deploying a new production build from a local environment to a Web server; and [Fastboot](https://github.com/tildeio/ember-cli-fastboot) for falling back to traditional server-side rendering of pages [when needed](http://tomdale.net/2015/02/youre-missing-the-point-of-server-side-rendered-javascript-apps/).

Another possible option is [Backbone.js](http://backbonejs.org/), which I did not look into in detail due to time constraints. It has much more emphasis on communication with the server via a RESTful API than Angular or Ember. However, I wasn't impressed with the documentation, and the design of the Backbone.js APIs seemed more complicated than Angular and Ember.

## My decision
During this little investigation into the possible frameworks I could use to create SmallScrum, it has shown an interesting change in the types of frameworks we now use to develop websites, and the types of experiences we create for those websites. While PHP and MySQL were the staples for website environments, more modern systems seem to be making use of node.js and MongoDB. Additionally, <abbr title="Single-Page Application">SPA</abbr>s are becoming very common. 

Therefore, I have decided to use Ember for the project. I've basically fallen in love with it. I've found it to be straightforward, robust, extensible and I even get to use ES6 syntax! When looking into Angular, I was looking forward to the possibility of using TypeScript, but I can settle for Babel.