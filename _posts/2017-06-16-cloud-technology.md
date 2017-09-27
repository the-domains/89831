---
inFeed: true
description: 'They are just reports, right? How complicated can it be?'
dateModified: '2017-09-27T22:09:30.509Z'
datePublished: '2017-09-27T22:09:31.525Z'
title: Cloud Technology
author: []
publisher: {}
via: {}
sourcePath: _posts/2017-06-16-cloud-technology.md
hasPage: true
starred: false
datePublishedOriginal: '2017-06-16T06:07:08.967Z'
url: cloud-technology/index.html
_type: Article

---
# Cloud Technology

They are just reports, right? How complicated can it be?

A lot has happened in the last two decades. We have come a long way from Microsoft Access and Crystal Reports. I have specialized in full-stack development for custom Business Intelligence online since 2008\. Before that I worked as a SQL developer. What I have now is a tried-and-true system for finding data, ingesting data, and representing it online.

## The Ingest

I recommend using a dedicated utility server to run the ingest, using [Sidekiq][0] for resiliency. For budget solutions we can put cron jobs on your application server. The main requirement for a good ingest is idempotency. I have designed a custom database schema-driven solution for maximum transparency and administration, which is reusable and designed for customization.

## The Application

Any application will do, but I suggest using [WordPress][1] for budget solutions, and [Ruby on Rails][2] for maximum efficiency and control. I recommend [Engine Yard][3] to all my clients, and find most often that standard support is just fine if I am still on retainer, and for those that want to run without me after development they can upgrade to managed support.

## The Reports

I spent years vetting new report solutions. I can say without hesitation that [Periscope][4] is a fantastic drop-in BI product. I use it with my largest client, with end users from some of the biggest names in online sales (Facebook, Netflix, Uber) as a white-label solution. What does that mean? It means we present the Periscope framework as a middle layer upon which the reports sit, often I write the form that assembles the complex parameters and then as a final step I call the API with those values and present a gorgeous responsive javascript report, embedded inside the Rails application that I am running. The reports include pivots, and exports, and search ability, and toggling of included values, in some cases. It really is like having a team of javascript developers at hand for a fraction of the price. If you wanted to build your own using something like [D3][5] it would take months. Seriously. For each report. And then you have to support your own reporting framework. _No way_. Cloud reporting for the win.

## The Timeline

Engine Yard runs on the [AWS][6] back end, basically the spine for just over 40% of the world's online business.
![](https://s3-us-west-2.amazonaws.com/the-grid-img/p/588b89e3bcfea28bab1c16afb8298d07d86bebff.png)

My favorite part of that is rolling a new server, for the database, or the application, whenever I want in about 30 minutes, at any time, at essentially no cost. It is a fantastic backdrop for development, because scaling up and automated deployment is basically trivial. The only remaining complexity is the data, and the navigation plan for the site itself. Here are some general ideas for time frame:

### App Servers

* WordPress - 1 week for nav set up
* Ruby on Rails - 2 weeks for nav set up

### Ingest

This depends greatly on the source of the data, but pulling data files via (S)FTP and writing an ingest for the data tend to take about 2 days per protocol/file format. I am used to processing csv files but I can just as well parse JSON or text files.

### Database

I have a strong background in schema design so as long as you are already clear about your needs and expectations, this takes from a day for very simple projects to maximum one week to try out different types of solutions for bigger projects.

### Business Layer

And the best part is that the report development is a breeze. Periscope makes it so if you set it up correctly in the beginning - I have my own ideas about optimizing performance on Periscope which are trade secrets - the reports can be written very quickly. Like about 2 hours each with strong and direct requirements.

## The Takeaway

Maybe you have a simple use case, and I need to take a few days to spin up a super-fast WordPress site that you can administer on your own, and just write a daily call to google for site stats to post to a sweet line graph and you probably don't even need a Periscope subscription.

Maybe you need a few analytics to start with, get the ingest set up, a Rails site, and a Periscope subscription with a custom plug in for embeds so you can hire a low level analyst to do drag and drop development for new reports with no need for more coding: 3-5 weeks.

The only thing to remember is that at this point, servers are cheap. Maintenance costs are cheap. It's the talent that is expensive. What I do is give you a system you can handle yourself, or teach someone to handle, with no coding background.
![](https://imgflo.herokuapp.com/graph/2b2431f8e7ba7b0/5aa7475a1d986aaa1e4e38879af21223/croprotate.png?cropheight=738&cropwidth=1115&degrees=0&input=https%3A%2F%2Fthe-grid-user-content.s3-us-west-2.amazonaws.com%2Fe3785fce-d72f-47f3-b041-d7d7c40cfd55.png&x=0&y=8)

[0]: http://sidekiq.org/
[1]: https://wordpress.org/
[2]: http://rubyonrails.org/
[3]: https://www.engineyard.com/
[4]: https://www.periscopedata.com/
[5]: https://d3js.org/
[6]: https://aws.amazon.com/