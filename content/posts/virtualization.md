---
title: "Intro to Virtualization and the Cloud"
date: 2022-08-01T17:21:15-04:00
tags: ['cloud']
draft: false
---

Virtualization allows for the creation of "virtual" computers and devices on
one server. It is an effective strategy for partitioning and managing compute,
storage, and network resources. Virtualization is not a new concept, but its
popularity has waxed and waned over the decades.

![Siemens System 4004](/siemens_4004.jpg)

Back in the days of mainframes, time-sharing was invented to allow multiple
users to run code on one mainframe, but it had its limitations, so
virtualization was created[^1]. This allowed each user to seemingly have their
own mainframe, and was a great boon to administrators who wanted to keep the
hardware at the highest possible effective utilization. With the rise of
personal computers, virtualization took a backseat to the new user-friendly
desktop machines---why *seemingly* have your own machine when you can
**actually** have one? As operating systems advanced, the original problem
which time-sharing and virtualization solved became more of a OS implementation
detail of how to best manage multiple processes. 

Fast forwarding past various other operating system advances, the development
of the Internet and its protocols, and the general exponential increase in
information technology (which I feel lucky to have observed during my life),
and modern cloud providers find themselves in much the same position as the
early managers and developers of mainframe computers. The central problem is
still how to most effectively keep their machines busy and allow users---now
paying customers---access to compute, storage, and networking resources. By
virtualizing these aspects of computing, the cloud provider takes care of the
underlying infrastructure and allows customers to provision whatever resources
they need.

While customers can provision storage and compute capabilities in the cloud,
and run a growing variety of services, all these components have to talk to
each other. In a traditional network, physical devices play a large part in the
creation of that network, for example: switches connecting devices and routers
managing network traffic. By using software-defined networking (SDN), these
physical devices can be abstracted away and seemingly created on demand. The
benefits are enormous. By defining compute, storage, and network capabilities
programmatically through infrastructure-as-code (IaC), we can roll back to a
last known good configuration if any recent experimental changes prove
untenable.

Since the advent of time-sharing, one of the more complex issues in managing
computer resources was maximizing the ability for multiple users or processes
to take full advantage of the hardware[^2]. Virtualization of compute, storage,
and networking in the cloud allows organizations to quickly productionize IT
infrastructure, respond to change in demand for specific resources, and avoid
many of the limitations of traditional on-prem infrastructure.


[^1]: Victoria Fedoseenko. A brief history of virtualization, or why do we divide something at all. https://www.ispsystem.com/news/brief-history-of-virtualization

[^2]: Christopher Strachey. Time sharing in large fast computers. https://archive.org/details/large-fast-computers

