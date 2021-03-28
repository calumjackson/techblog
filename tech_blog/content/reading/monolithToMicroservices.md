---
title: Monolith To Microservices
date: 2020-08-03T231005
weight: 7
---

---

Author: Sam Newman


# Context

This book covers the steps and strategies needed to decompose a monolithic architecture into a microservices architecture, starting with why you should move to microservices (and if you should), before moving onto the design patterns needed to achieve this. The initial chapters are a good introduction to the subject matter, defining what anyone is likely to want to achieve by moving to microservies, and the other options available outside of microservices. One re-iterated point is that Microservices _are not a silver bullet_ - there are many other architecture options which can give you similar capabilities without the complexity of microservices, which are difficult to comprehend in the design phase of microservices given their distributed nature.

# Chapter 2 Notes

This chapter discusses the steps to consider when planning a move to microservices. Notably time is spent on the decision to move to microservices being based on achieving some end goal, not because it was a buzz word.

This is mainly driven by the point that moving to micro-services is not simple, and creates a complex architecture to maintain, which may not be necessary in the problem space. A lot of time and energy can be put into microservices which could be wasted if it is not done for the right reasons and suitable alternatives have not been considered, for example flexible scalability is a possible bonus of microservice architectures, but this could be achieved with much cheaper costs by plain old vertical or horizontal scaling in certain contexts.

The second part was defining the business and human nature to driving change in the organisation, as the basis for getting the momentum to actually implement this change against competing priorities in the business. This delves into the "8 steps for operational change", which builds a model based on the following steps

1. Create a sense of urgency
2. Build a guiding coalition - set of diffuse people who will be able to help drive the project forward.
3. Build a vision and strategy
4. Communicate the vision to the teams
5. Enable teams to work / build accountability / autonomy to work on the features. Empower employees with broad based action.
6. Create short term wins (gains)
7. Consolidate small wins (gains) into big gains and push momentum
8. Anchor the mindset / work / approaches into the fundamental culture of the company.

Once these decisions have been made, the choice of what to migrate is made easier by drawing up a model of the architecture using events storming and domain driven design. These techniques allow you to define the domain boundaries and also determine the difficulty to isolate a particular microservice from the monolith (i.e. on piece of functionality may be used by multiple other services, making it more difficult to extract).

### How to know change is working

The author mentions that knowing where you are now is as important as knowing where you want to go - otherwise you will be unaware of where you are on your transition, and on top of this understanding how monitoring provides the framework for tracking that. Regular checkpoints of both quantitative and qualitative measures are critical in measuring the success of change - qualitative is possibly eye raising here however the authors point is that you need to bring the engineers along on this journey with you, so to move in a direction where they are not seeing advantages is a move to failure. I imagine this doesn't mean you would need to drop everything and go back to a distributed monolith, but it may mean making changes at a more sustainable rate so that employees can understand each level of change more before having the next level thrown upon them.

I am thinking of this in the same way as the UK government is looking to end the lockdown in early 2021 (time to date this blog _smile_) - each removal of restrictions is stepped with 4-5 weeks wait inbetween. This has two uses I can see; the government can monitor the effectiveness of each set of changes without having the data comprimised by having too many changes to cover (which do you revert if infections rise significantly), and steps the re-introduction of normal services back to the NHS, who are still swamped with COVID in the critical care units which effectively become a bottleneck to all other specialities as all major surgeries end up in an ICU.

# Migration Patterns

## Strangler Fig Pattern

This is the method of separating out slices of functionality (ideally by domain), and developing a micro service to deliver that functionality but to switch the operation of that service over slowly from the monolith. This replicates the strangler fig in that it grows on an existing tree and becomes part of the trees structure until eventually the old tree dies within.

In this case you could extract the functionality of say a payroll service (copying code verbatim is a good option here if possible, as it will keep functionlity the same) and exposing that service slowly as it is delivered. HTTP proxy is marked out as a good splitting method as the traffic can be more easily re-routed, and is quick to change back to using the initial functionality in the monolith if things aren't working out.

One aspect that needs thought is the interaction with other services within the monolith - it might be needed to expose downstream services via an API to be able to recreate that link which would be easily available within the monolith.

A lot of the complexity of implementing the strangler fig is in deciding what method re-routing messages to the services takes. There are options around using a service mesh (Istio), updating the API and mapping all messages into the new API, and Content Based Routing. Content Based Routing is a option which could fall either way where ideally we would "keep the pipes dumb" and not create a level of complexity upstream, however other options such as getting the monolith to ignore certain messages and the complexity of timing the switchover could lead to taking the content based routing approach as it abstracts that matter - likely this better for more complex message re-routing where it is not planned to be in place for long amounts of time.

A _service mesh_ is something I haven't really understood before but this book seems to give a good (if brief) overview of the concept, that the service mesh provides the ability to deploy services with a local proxy to each service alongside, and a control plane which allows central management of those proxies. Within the boundary of the service mesh all communications to services are via proxies which can route traffic appropriately and configuration of those can be managed from a central location. [Redhat provide a good view of the service mesh](https://www.redhat.com/en/topics/microservices/what-is-a-service-mesh), indicating how the abstraction of the communication layer allows the removal of specific coding to deal with communication in each service. This sounds like "smart pipes" which the author is advising to avoid, but I think the idea is to treat the communication layer as a first class service & the pipes within that are still "dumb".

## Branch By Abstraction

Similar to the Strangler Fig option in places where functionality is embedded in the services & cannot be re-directed via re-routing messages. This creates a more invasive method of abstraction and involves adapting the code of the original monolith, but this is a less complex option than the parallel run.

This method is implemented via abstracting an interface to the functionality within the monolith, such that initially this is just a pass through to the existing functionality. The difficulty in this pattern is that understanding all the services which use the functionality can often be unknown, which means you are in the position of having to work that out before starting to re-route them to the abstraction.

Once the new implementation is ready the abstraction can start to switch functionality referencing within the abstraction so that it starts to use the new method, and then start to clean up the old service by removing it

## Parallel Run

The name gives this away, build the new implementation alongside the existing monolith and run the transactions through both systems, comparing the outputs in both until the new implementation can be validated to the point of this being the new source of truth.

## Change Data Capture

Pattern for tracking actions being taken through database calls (triggers or logs), and passing those messages in as the API calls to the new service. This is quite an event driven approach but can add a lot of complexity, such that building and maintaining this can add as much work as other implementations.

# Decomposing the Database


## Database As A Service

This concept seems to be a invocation of the CQRS pattern, where reads and writes would be written to one database, ideally via the owning service, which then has a separate external database which keeps an eventually consistent view of the internal database to expose to outside services in a read only manner.

This level of encapsulation of the internal database prevents coupling to the internal database and reduces read/write contention between them (however this may not reduce compute contention if the "external database" is built as a separate schema on the same database).
