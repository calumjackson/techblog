---
title: "Data Analytics: 12/09"
date: 2019-09-13T15:59:47+01:00
draft: false
weight: 1
---

---

**My. _Second._ Meetup.**

This meet-up was organised by the [Data Council.ai](https://www.meetup.com/DataCouncil-AI-London-Data-Engineering-and-Science/) team, and had a few _hot_ presenters:

* Snow Plow
* Monzo
* pgAudit

### Snow Plow

The first of many Stephen's on stage this evening was from Snow Plow (the meetup sponsor), who are a data analytics _platform_ (still not sure how well used that term is generally - is this something that is used to build other services on? Maybe I should write down _what being a platform means_ to me).

My vague understanding of the operation of this was that Snow Plow is a data analytics platform which allows eventing to be almost instantly tracked and analysed within the data warehouses. Having side-_tracked_ myself reading their [github pages](https://github.com/snowplow/snowplow), I can see they are based around a general event tracking and their individuality comes from being an open source, loosely coupled architecture (read: cool, well structured for microservices architecture).

The actual talk was from a lead engineer, who was pushing the idea that tracking testing is as important as any other testing if you are to be a data analytics company with any **integrity**. The validation of tracking can be built into testing automation much like any other functionality, and in turn built into your CI pipeline, such that you get a constant valid stream of data hitting your warehouse - with the obvious benefits of not missing out on precious data, and more importantly not shifting **bad data** :scream: into your warehouse. This all seemed pretty reasonable, and got me thinking that is this the evolution of test driven development, moreover is this an extenstion of TDD or is it a new TDD - Tracking Driven Development? If data is a main output of your service, where does that sit in importance to actual functionality :anguished:.

Unfortunately I asked a question around whether this is a extension of TDD or if it's own TrackingDD, but lead into the philosophical aspects I was expecting didn't really pay off (I was probably being rather gratuitous to myself to expect it to :joy:), but is something I might keep thinking about...


### Monzo

I don't think this company need an introduction (unless your reading this from a non-UK background - they're a startup tech bank). They seem to have a lot of code in [github](https://github.com/monzo), their [open API](https://docs.monzo.com/) stuff looks interesting and a good use of online documentation (is this auto generated via Slate????), so I might have a dig around in there to see how a well revered tech start up does things :laughing:.

The onus of the talk here was around Monzo migrating to [dbt](https://docs.getdbt.com/) (data build tool)





### pgAudit

I didn't do this talk justice as I was distracted having lost a filling in the break. From what I listened to this was a tool to verbosely audit whilst creating a standardised auditing format.
