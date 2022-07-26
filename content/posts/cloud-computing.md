---
title: "Cloud Computing 101"
author: Robert Trigg
date: 2022-07-25T23:48:45-04:00
tags: ['cloud']
draft: false
---

Trying to convince management it's *finally* time to migrate or expand into the
cloud? Perhaps you are new to cloud computing, and trying to learn more. Or
maybe, you're just wondering how well the NIST definition of cloud computing
fits in 2022? It's been over ten years since the words:

> Cloud computing is a model for enabling ubiquitous, convenient, on-demand
> network access to a shared pool of configurable computing resources (e.g.,
> networks, servers, storage, applications, and services) that can be rapidly
> provisioned and released with minimal management effort or service provider
> interaction. 

were written by Mell and Grance (2011), and they seem to hold up.

I like the focus of cloud computing as a *model* of computing. In this model,
the traditional on-premises data center or hardware is abstracted to a service.
Compute resources and needs can be fulfilled on demand in a pay-as-you-go
financing plan[^1]. The advantages of this approach are hard to overstate,
which is probably part of the reason why cloud providers (AWS, Azure, and GCP
being the big three), have done so well the past decade. 

![The trend is clear](/cloud_trend.jpg)

As a quick refresher, or by way of introduction of this is all new to you, the
advantages of the cloud include:

- **Increased Agility**: This is *such* an overused buzzword, but it's true!
  Cloud technologies let companies experiment more, give new technologies a
  whirl, and generally develop more faster. Imagine: quicker standing-up of
  computer, network, and storage resources---no more waiting 6+ months for
  procurement and approval processes!
- **Cost savings**: This can be hard to convince management of, especially if
  you are asking for more money to throw at the cloud, and they might not think
  you need it. However, it's one of the first things people think of when
  migrating to the cloud, as it *seems* easy to understand--give me two numbers
  to compare! Turns out it's not that simple. For now I'll just give the
  example: with on-prem resources, it's common to over-provision "just in
  case," which means that a lot of hardware is idle much of the time. 
- **Improved Performance and Uptime**: Tell me you can run a data center better
  than one of the above companies and I'll uh... I guess talk to some angel
  investors I know, because we all need to have a meeting in the next week or
  two!
- **Metrics, metrics, metrics!** You can do this yourself, but cloud service
  providers have some really nice built-in logging if you want to track
  traffic, the health of instances, etc. Also, if you have special logging
  or data retention requirements due to the nature of your product and the
  jurisdiction you are in, you can take advantage of these offerings and
  automation to save time.
- **[There's](https://docs.aws.amazon.com/whitepapers/latest/aws-overview/six-advantages-of-cloud-computing.html) [a](https://www.microsoft.com/en-us/windows-365/cloud-computing-advantages) [lot](https://www.ibm.com/cloud/learn/benefits-of-cloud-computing) [more](https://cloud.google.com/why-google-cloud/) to it!** but let's more on.

## Jargon-as-a-Service
Cloud computing has it's own terminology, and there's a lot of it, so it's not
surprising that people sometimes feel overwhelmed by all the terminology. I
think it's important to focus on the basics, and connect that to what you
already know.


### Software-as-a-Service (SaaS)

This has eaten the internet. Most of our day-to-day interactions with the web
are through SaaS. Think of Gmail, Netflix, MS Office Online, etc. Anytime you
are doing something in a web-browser that's somewhat similar to how you might
have run local software to do something back in the day (for those of us who
remember the 90's), that's Software-as-a-Service, or SaaS. App in the browser?
That's SaaS. Social media platforms? Also SaaS. I'd argue this is so ubiquitous
that people don't even notice it any more, but it's pretty cool when you stop
and think about it.

Usually SaaS has a subscription price; when it's free there's usually some
other benefit to the provider, whether it's just keeping you in their
ecosystem or monetizing your data through advertising metrics or whatnot. If
you want to build a SaaS offering for your customers, you don't *have* to use
the cloud, but you better have a bunch of geographically dispersed servers and
somehow know your future usage and traffic patterns (and thus, hardware
requirements). 


### Platform-as-a-Service (PaaS)
You can use PaaS to build applications. If you are a developer, you might be
familiar with Heroku or Google App Engine. These offerings can let you get
right to work developing your app, without having to worry about all the
underlying infrastructure. Think: I just want somewhere to run this code so my
users can run my app!


### Infrastructure-as-a-Service (IaaS)
Closer to the metal! Though likely just virtual hardware,
Infrastructure-as-a-Service, or IaaS ("eye-aze," I guess?) lets you provision
custom storage, network, and compute resources. You can set up and configure an
environment from the hardware to the operating system all the way up to
whatever app or service you are trying to create. These days, the line between
PaaS and IaaS can be a little blurry, depending on the provider.

Example Time: Let's say you want to set up some overnight builds and testing,
and the free options on GitHub or whatever just aren't cutting it. Maybe your
builds take a while, or the tests are so big or numerous that it takes hours to
get results.  If you want to stand up a little build server, that can cost $10k
for hardware alone (this isn't counting the ongoing cost of the IT staff's
time, you know, the folks who setup and maintain it, many of who are already
too busy with other tasks).  Also, you risk over-provisioning, where the
machine sits idles for 12 hours a day. This is where IaaS is going to be your
favorite new flavor.  Once you have a machine definition file of some sort,
it's seconds to minutes to stand up a machine, and you can set it all up to run
automagically whenever someone pushes changes to the code repository. Maybe you
do 10 at once because you got 10 extra branches you want to test **now**, it's
no problem!

Well, that's all for now. Keep your feet on the ground and your head in the
clouds!


[^1]: This is perhaps oversimplifying, because there are other financial
arrangements, like reserved instances, where customers commit to a year or more
of hardware or payment amounts... but it's a good-enough definition for
starters. This is 101, no need to get into the weeds.

References

Mell, P., & Grance, T. (2011). The NIST definition of cloud computing. Gaithersburg, MD: Computer Security Division, Information Technology Laboratory, National Institute of Standards and Technology. Retrieved from http://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-145.pdf

