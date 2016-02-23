---
layout: post
title:  Rapid prototype versioning
date:   2016-02-23 22:17:00
author: Matthew Shaw
image:
tags:
- Prototyping
- Versioning
- GOV.UK
- Node.js
- Express.js
- Nunjucks
---
As a part of my day job I create prototypes of new services on [GOV.UK](https://www.gov.uk/). We use these as one of the ways to research and learn more about our users' needs. It's a very effective and fast paced way to get a lot of vital feedback early on in the development lifecycle and use it to [iterate quickly and frequently](https://www.gov.uk/design-principles#fifth).

Creating new versions of prototypes whilst preserving your previous versions allows you to see how far you've come, what worked, what didn't and provides documentary evidence of user-centred research, design and development. This is particularly useful information for a [Digital by Default Service Standard](https://www.gov.uk/service-manual/digital-by-default) assessment.

Managing multiple versions of prototype code can soon become cumbersome and error prone. Although naming conventions, git branching or tagging and multiple deployment environments can help with this, we need a simple solution. The approach I've developed is to structure your routes to make use of request parameters, such that you [don't repeat yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and avoid unnecessary duplication of generic routing code. This allows you to focus on what you really want to iterate on; the content, layout and structure of what your users are going to see.

#### Example

This is prototype code only, not production-ready, the aim here is to enable rapid change so we can learn as much as possible about our users' experience and interaction with the service.

Here's how to do it using the [GOV.UK Prototype Kit](https://github.com/alphagov/govuk_prototype_kit) which uses [Node.js](https://nodejs.org/en/), the [Express.js](http://expressjs.com/) framework and [Nunjucks](https://mozilla.github.io/nunjucks/) templating engine at it's core, although you could just as easily apply this same approach to your favourite web application development tools.

Directory structure:
{% highlight markdown %}
├── app/
│   ├── assets/
│   ├── views/
│   │   ├── beta-v1/
│   │   ├── beta-v2/
│   │   ├── beta-v3/
│   │   │   ├── data/
│   │   │   |   ├── AB1234.json
│   │   │   |   ├── AB2345.json
│   │   │   |   ├── AB3456.json
│   │   │   ├── applications.html
│   │   │   ├── draft.html
│   │   │   ├── approved.html
│   │   │   ├── rejected.html
│   ├── routes.js
{% endhighlight %}

My URLs are structured in a [RESTful](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api#restful) way, with the addition of the leading `/:version` parameter. My resources here are "applications", where `/applications` is a collection of applications, `/applications/AB1234` is a specific application and `/applications/AB1234/draft` is a draft of application AB1234. Here's the URL routing code for this:

{% highlight javascript %}
router.get('/:version/applications/:application/draft', function (req, res) {
  var version = req.params.version;
  var application = req.params.application;
  var data = fs.readFileSync(__dirname + '/views/' + version + '/data/' + application + '.json');
  var parsedData = JSON.parse(data);
  res.render(version + '/draft', { "data": parsedData, "application": application, 'version': version });
});
{% endhighlight %}

In the above `GET` request, `/:version` corresponds to the directory name within `views`, such as `/beta-v2/applications/AB2345/draft`. Likewise `:application` corresponds to the name of a file inside the `data` directory which contains the structured JSON data that is passed to the `draft.html` template. When I want to make a new iteration I just duplicate the last version directory in `views` and set about making changes based on user research feedback.

I've also made good use of the templating engine, holding all variable data on each page in a structured JSON file, so the HTML templates are largely about presentational logic and layout of that data. This is in keeping with [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) software architecture and mimics how the data-driven UI would receive data from an API. This means I can make very quick changes to page content without affecting layout that I might want to preserve between versions, and vice versa.

Combine this with an index page with links to each version, a date or sprint each iteration was created and a change log for each iteration and you'll have a rich visual history of your application prototyping.
