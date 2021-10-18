
---
title: "Research"
date: 2020-06-28T21:38:47+01:00
draft: true
weight: 3
---


# Key Info

_Push Payments_: Buyer Initiated payments, where buyer provides the card details and then pays the sellers bank account.
  * Push payments are considered non-repudiable (safe to spend immediately) as the buy has authorised the transaction.
  * Reduce payments processing to single transaction management, removing intermediary steps of reconciliation between the two endpoints, and reducing issuer costs associated with payments.
  * Instant payments offer choice to the consumers - gaming is a good industry use case as it returns winnings to keep users at the table.
  * Acquiring bank pays out to customer, receives debits from VISA on daily(?) basis which the acquirer then has to collect back from merchant.

_Pull Payments_: Supplier Initiated

# VISA Direct

Visa Direct is a real-time push payment platform to enable expedited payments to customers or small businesses using the debit card rails provided via VisaNet. It has processed 3.4 billion transactions as of late March (2bn in the last year). Visa Direct is currently open as three options:

1. Business to Customer (B2C)
2. Business to Small Business (B2SB)
3. Peer to Peer / Person to Person (P2P)

One oft cited use case is payments to the gig-economy, where businesses like Uber will be managing the debiting of fares from customers centrally, however Uber drivers can opt to be paid for their fare immediately via push payment (at a fee from Uber) rather than a daily settled ACH payment which could take days to actually reach bank accounts where the banking route or issuer has slower settlement timelines (or don't work weekends / bank holidays).

The reach of Visa Direct is 200 countries and territories. These cross border payments allow money to move real time cross border removing the settlement delays associated with banking systems cross borders. **Remove the requirement of originators / acquirers to have to setup connections to local payment networks**

## Earthport

Visa owns one of the largest independent account clearing house (ACH) networks - so basically now VISA can use push payments through both card and bank rails. This has opened up a large network of accessibility for VISA direct payouts, which furthers the network effect of VISA Direct & therefore increases its growth and value.

# Interview

## Senior Solution Consultant

* Supporting Acquirer and Originator Enablement
  * I imagine this will entail building relationships with new and existing acquirers and help them build their product roadmap to enable Visa Debit integration.
  * This will likely also require building product overviews and understanding how customers want to take push payments forward, including understanding what their acquirer platforms help enable and how the features Visa Direct provides can help move them towards new opportunities.
  * This could be a useful place for value chain mapping to show how the landscape will change for companies as they start to embrace push payments.
  * Will need to help acquirers understand the changing nature of payments and how the model will affect their business - for example if an acquirer only settles a merchant on a daily basis, there is a increased risk associated where effectively the scheme deductions are liable.
  * Building the initial designs of how acquirers will interact with their specific technology landscape.



# Visa Possible Questions

  * Why you want to work at Visa? Why do you want this role?
    * It's an institution, as Zero said to Mr Gustaf in Grand Budapest Hotel.
    * It's an ubuiquitous entity which everyone instantly associates with payments, and provides the means for people, businesses, and governments to thrive by opening up payment possibilities to them.
    * Empowers businesses by providing them the rails to take payments from customers across the globe, abstracts the complexity of cross border payments, etc.
    * Has a strong inclusion and diversity presence, I found that incredibly powerful to see pages and pages of Women and people from diverse backgrounds in positions of leadership and influence. I think a lot of the issue with getting women into tech is around the stigmas which are ingrained in schools and not having role models who represent their backgrounds.


  * What examples do you have of providing support/leading teams/managing projects?
    * Building Bucharest team
    * Brexit
    * General SOE building with release teams.
    * Australia
    * Multi Currency MIDs
    * Mastercard Japan
    * End To End Orchestration
    *
    * Teams wise I have helped build a remote team in Bucharest for our Customer and Financial Reconciliation Reporting function in Worldpay. We acquired a fintech operation out in Bucharest to help reduce our contractor cost as we stabalised into a strategic tech platform rather than a project.
    * This basically entailed building the knowledge of 7-8 new developers and designers in the team, leading the design process, and taking on the lead role as the product owner was spread quite thin between other projects.
    * Most projects I've worked as part of over the past 2 years have been shorter term integration pieces trying to piece together the last steps of our acquiring platform for migrating of the mainframe. These have entailed building SOEs for technical delivery (such as the brexit project, a migration in itself), building delivery plans for coupled components which are delivered across streams (and driving de-coupling opportunities as part of these projects).
    * Leadership skills are those I would like to grow, as I've had exposure within the reporting outfit, and within these projects, and leading the automation team within our platform (whilst that team effectively sits in infrastructure as a wider piece).
    * Personally the most important work I think I've done in leadership is protecting my peers & helping solve tension between teams when things have not gone as planned. There are a whole host of reasons why things go certain ways and certain decisions are made, which need to be understood rather than blamed to help prevent these in future (what would have stopped me making the same decision? Hindsight?)

  * What is your current role like on a week to week basis?
    * Almost a platform consultant in nature of working with the engineering teams to help review and guide their technology decisions against the wider platform where appropriate - something which is changing as roles become more decoupled & better idempotence is created, but that isn't there yet so I have been help guide impacts of software delivery, and help engineers understand the wider platform.
    This often includes helping engineers understand the business impacts of the decisions they are making, such as
    * I would see myself as how people generally refer to staff engineer - architect roles, where I am playing the role of "glue" for 50-60% of the week and delivering change projects in the remainder of the time (Australia & Multi-Currency MIDs, Brexit).

    * The historic nature of our platform being a distributed monolith makes a lot of what sound benign projects more difficult than necessary to deliver as we have to manage multiple delivery trains across our platform and
    * I also manage the end to end automation of the services throughout our platform, which generally means for each release reaching out to multiple teams to understand how they want to implement their service and building that into the automation software. As a side project we're currently building out the automation framework so it can sit inside the individual development teams - it's something which has taken a long time to come to fruition as we were tied into a particular software where the next version provided a solid framework to move this process left, however the automation team ownership sat outside our teams ownership, so that was again a case of convincing multiple people that the upgrade would drive value through reducing test cycles and delivery time / cognitive load on E2E teams.
    * I ran the brown bag sessions for our team, which I found useful in building knowledge outside of tech as much as within ()

  * How would you adapt/transfer your key skills and experience to this role?
    * I would like to adapt my practices to this role to have a more effective approach to project management & delivering with teams - the nature of this job implies there will be multiple ˜
    * Taking charge of a team will be another aspect I haven't had direct management of in a while.
  * What challenges would you expect to face coming into this role?
    * Learning the detail behind the product - what VISA Direct is, and how it differs from the VisaNet landscape and provides the scale of change promised
    * Picking up skills in management and planning which I've previously been involved in a contributory manner.
    * Managing and maintaining project plans when acquirers are working on different SDLCs to ours - some will be newer and much more agile, and being able to align their rate of change against ours, versus working with more established acquirers for which we might be integrated with a more six sigma approach as their service is

  * What would I like to receive from VISA, or get out of the experience?
    * Exposure to client based operations which are working on the cutting edge of payments, and delivering real change to customers where you will be able to see their progress and the changing face of their originator systems as they adapt to real time payments systems.
    * Having a voice in how payments is adapted, working with talented people who will be bringing ideas which challenge the way we think about payments and cause me to question the boundaries I have.
    * Opportunity to be exposed to



# Influencing Skills

* In the role of E2E orchestration owner, generally I have had to help guide the prioritisation process of where it appears work is needed on the platform which is not seen by individual silos or prioritisation groups outside not involved with the end to end. The place I usually helped influence was by demonstrating a weakness in our integration points, and how improvement there would help deliver significant value which was not always obvious. One case was our delay in payment suspensions based on a manual process, which created a cascading effect of delays to merchant settlement and customer reporting (which used settlement generation data). By showing the improved customer experience possible (we brought in report delivery by 8 hours and all but removed missed payment SLAs), we got the required sponsors for automation of the payment suspension process.

Similarly, I've regularly worked with business clients to help define the process they want, and drive confidence through prototypes or simple definitions of complex issues to help understanding of the goal the project is aiming to achieve. An example recently was the Australia next day settlement project, where we were not able to hit a next day merchant settlement target as the scheme settlement timelines did not line up to avoid pre-funding.





## Questions I Was Asked:

* How have I dealt with painful people to work with?
  * Usually people need time and space to be heard
  * PIR example of understanding how people have come to that decision - blameless societys, how do you change the model.
  * These seemed okay, improve upon actions that came out of it.

* How have you got to where you are?
  * Story of worldpay - think this was good but could make it more concise. Went through background of how I joined worldpay, worked in test of reports, moved into the design team and leading a team out in Bucharest, which was a new fintech team and needed help understanding the platform. Things I learnt from this were that it wasn't best to spoon feed, it would have been better to set exercises and for them to understand the data models that way.
  * I would also put a lot more on them to come up with the ideas etc, as my initial way of working was to drive the change but had little buy in from the team as they were less involved. This might have worked with more hierarchical teams but the culture was likely a bit more egalitarian and they wanted to be involved in design.

* Why do you want to leave worldpay
  * Said that I was quite comfortable at Worldpay - could have said I am in a good position at worldpay _because_ we've got to a position where we're about to drive a lot of change in the platform, around technology and the acquiring background, such as building our regionalisation model. However this was a particularly interesting role to be a part of and will put me a little out of my comfort zone, so is a place where I can learn and grow in my role, and be a part of change in the industry in general. This will start to drive huge growth for both VISA and other acquirers based on the model possible, particulary where an acquirer can start trading in a region it doesn't yet have banking ties with but can be paid out via VISA direct.

* What are your best qualities
  * This was a good section - conveyed my holistic nature and overall understanding of concepts of business against concepts of technology.

* What do your friends think about you?
  * Calm, loyal, need to think of a better way to say I can question things without sounding argumentative.
  * It might be good to contextualise this by mentioning how there are a lot of difficult topics and I like to talk about them with people.

## Things of note

* Mentioned the importance of data and visualising that to the customer
* Tableau and Power BI as tools to research over coming weeks
*

# Possible Questions Interview 2

* Stakeholder Management
  * Despite not managing external clients, have dealt with internal product teams and feeding back to our VP level / CTO level to explain the context of the issues, why this needs resolution, and plan to change.
* Communication
  * Communication was not one of my stronger points when I was a kid so this is something I have worked on throughout my career, I've taken positions of leading teams, I've led technical courses for grad joiners in PL/SQL, my role at the moment requires me to convey the mechanisms of the platform and of acquiring regularly for large groups across our global teams as part of releases, or when building impact assessments etc.
  * One thing I've found since working with offshore teams is how articulate things more slowly and clearly given that listening to a fast talking Yorkshire accent isn't always easy when it's someones second language! Particularly with online meetings now ubiquitous it's important to ensure people are understanding, I personally try to be on camera as much as possible as it not only shows you body language when talking but also when listening, and helps people place better how much you might be taking in.
* Motivations/Enthusiasm
  * I'm motivated by solving complex problems which have an interesting business context, really enjoy working with teams to put together those designs and seeing those projects come into being and taking life.
  * Seeing what is delivered showing value is a great feeling here.
  * Think it's important to remember as projects become agile that you should be congratulating regularly within the iterations as it's more difficult to determine the end point given that the point of agile is to be able to maintain a continuous state of delivery, but at that point it becomes less obvious when you have achieved something.
  * I would be really excited to work with other highly motivated groups who are great at sharing knowledge and ideas, and having the prerogative to help bring those ideas to life.
  * I personally would like to stay close to technical knowledge and to keep up to date with that aspect, even if this role is likely to be more on the product management role - ideally I would use this role to really get to know the VISA Direct product and the way the company works, and use that as a sounding board to moving towards more technical architecture roles.
* Overall working style
  * Someone who will take the time to understand the problem, generally like to be inquisitive about why decisions are being made and understanding the basis for decisions.
  * Work best as part of a team who can throw ideas around or plan together, and share information between the teams.
* Knowledge of Visa and Payments industry
  * What do I think VISA Direct will bring and how that will work
    * How VISA direct will drive huge growth into VISA as basically every transaction will be new value as they would have previously been ACH based transactions. That means the turnover and fees gained will grow on a strongly linear growth pattern?
  * Dynamics of cryptocurrencies and how they will change payments. Though, when does Bitcoin become legitimate? USD Coin is good because it is being pegged to USD so is not of value to horde.
  * Scheme machinations - fraud monitoring / FX

* Working with senior management
  * Had exposure of reporting and working with CTO level, explaining technical & business problems we have had in the platform, their impact to the customer / business, and how we can resolve this and what we would need from them - so both from a PIR point of view and helping drive the planning for the change needed (i.e. on our reporting SLAs, how we needed to prioritise automating payment suspensions to expedite our reporting SLAs with the added benefit of reducing settlement risk and alleviating manual work in the risk team.
  * Work relatively closely with senior management within the platform anyway as a part of my role, usually would be a reliable source to build the technical and business impact of any changes on the platform and their risk - usually I would draw up possible risks through consultation and delegate any quantitive stats for the teams to provide as they are closer to their actual products.
  * Represented Worldpay at client integration meetings with Tesco in the early months of my role when the platform was still in it's infancy, however since then implementation managers have taken over that aspect as customers have migrated over and implementation managers built their knowledge of the capabilities of the platform.  

* How would I engage a client?
  * I would largely want to question them on their goals in acquiring first, understand what they want out of VISA Direct as a product, and then build on their requirements/scope to give a view of how technologically we can achieve that, what the key boundaries we need to progress with are (risk, reporting, etc) to start to go live, how that fits into their delivery model (is it agile, six sigma, lean, waterfall etc).
  * Use of value chain mapping could be useful to expose to acquirers how their business model can progress.
  * Would likely be useful to draw up tech models to understand what product they are expecting, and to start to draw up how this scales etc.

* Data based presentations
  * Reviewing Tableau and Power BI - both presentations layers built on basically low code platforms - allow you to drop and drag to build datasets and then visualise on top of that.
  * Not familiar with their GUIs directly, however very experienced at working with data and data models at the database level and building queries which use analytical functions etc to provide information, building to cover data defects, designing functions & queries which would be used to drive decisions within programs, as well as building dashboards for business users in Oracle Apex.

* What do I want to gain out of working on this product / team.
  * Looking at the team that is setup I imagine would work well in that there is a lot I would be looking to learn from the experience of the group, particularly around programme management which isn't in my direct line of experience, where I

* Knowledge of VISA and  Payments
  * VISA is historically a card scheme within the four party model, which would provide the interface into the issuers from the acquirers and originators. This interfaces is managed via providing customers with cards which are linked directly to a customer bank account, and when a merchant takes a transaction at the POS, the

# My Questions

* How do you see the team running in terms of splitting work? Who does what, what does a usual week entail? Is it an acquirer each etc?

* What are the organisation and team management aspects of the role going to entail? Will I be managing projects directly, or as an overseer of multiple projects where I would be more likely to delegate planning, and play a prioritisation role etc.

* What technical exposure do you see in the role?

* Where does this career track lead within VISA, is this a lead into software architecture or towards programme management?

* What technology is VISA Direct built on / what type of technologies are we expecting Acquirers to be integrating via?

* What opportunities are there to teach / be taught at VISA? Do you run architectural katas as well as dev days?

* What support would I be offered in being able to build the skills necessary for the role, online learning / courses.

## Other Qs

* How does the climate 2040 pledge align with VISAs cryptocurrency / blockchain strategy?

* How does VISA maintain it's scalability infrastructure

* How come this role wasn't an internal hire?

* How does VISA promote mentorship and sponsorship?

* What are the diversity levels within technology, compared to the model exposed in the face of VISA? Is Visa Europe as representative as VISA Inc looks?


## Answers to my questions

### Where do you see the growth in Visa Direct over the next 2-3 years?

Stergios saw VISA Direct as the main route of progress within VISA alongside cryptocurrencies (VISAs enablement with USDCOIN) and tokenisation. His aspiration would be that you would not want to work on another product / project for the next 2-3 years. Assuming this was given the amount of change and being the forefront of VISAs product view.

# How will Earthport extend the Visa Direct offering? Is that by the ability to build it into the open banking rails?

Yes basically has been operated as VISA Direct Payouts - which is the banking aspect of this which could revolutionise acquiring as it would allow acquirers to enter new markets as soon as they had acquiring bins rather than having to build the banking integrations with whichever bank is in that region.


## How prepared do I feel?

I am feeling like I have a good position of creating a nicely balanced team with the two people interviewing, as they have backgrounds in business, risk, and program management which would work nicely with my technical knowledge and acquiring knowledge in terms of bridging these conversations with clients from a technology perspective - how will the acquirer integrate with VISA, what problems should they expect to hit, how have other acquirers dealt with those issues, and _how might they build this to scale_.

My experience working on the architectural elevator allowed me to move between the leadership teams to help them in putting technical and business context to their decision making, as well as to work with the developers to understand the fundamental issues of the
problems we are seeing and how we can go about solving them, with all the layers inbetween.

Data visulisation and presentation I don't feel too worried about on the caveat that despite having no formal experience in Tableau and PowerBI, I am well versed in the fundamentals of database querying and providing insights from data which can help with decision making. Low code visualisation programs I don't really expect to be a barrier as I've built these kind of visualisations based on my own handwritten queries using analytical functions, and have an excellent understanding of relational databases.

Generally I have been working relatively independently as a solution architect, moving across projects to help bring them together from an end to end perspective and helping build the view of how we can deliver this. Generally this has been why I have not been involved in the planning as heavily as given the scope of projects across the platform (for example, from a operational perspective we have increased our platforms automated procedures by 300% since I took the role). I have proven myself as being able to enter a project, build a context quickly, and help deliver the solution - to the point where I am a go to person for this which we've had to push back on as it became detrimental to the time I was available to put to projects. One piece was our customer integration into our acquiring system, as the file based merchant refresh was causing issues on the authorisation system (which was outside the platform). I helped bring the teams together to understand the problem, we built a design to alleviate the issue and then planned it's delivery into production over the next couple of releases by solving the key issues first which were causing live issues and having the strategic fixes to the problems on our backlog for the product owners to take ownership of.

#### Sean Pitman
* Experience leading product, particualy start up and close down of a small product. Likely to be well versed in

#### Stuart Bowes
*

Both recent hires from Natwest, so outside of the finextra .

####

# Key
66dML6uVT2zD454y
