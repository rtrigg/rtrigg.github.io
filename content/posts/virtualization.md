---
title: "Virtualization and the Cloud"
date: 2022-07-31T01:39:11-04:00
draft: true
---

Virtualization allows for the creation of "virtual" computers and devices on
one server. It is an effective strategy for partitioning and managing compute,
storage, and network resources. Virtualization is not a new concept, but it's
popularity has waxed and waned over the decades.


![Siemens System 4004](/siemens_4004.jpg)

Back in the days of mainframes, time-sharing was invented to allow multiple
users to run code on a mainframe at the same time, but it had it's limitations,
so virtualization was created[^1]. This allowed each user to seemingly have
their own mainframe, and was a great boon to administrators who wanted to keep
the hardware at the highest possible effective utilization. In the office,
virtualization took a backseat with the rise of personal computers---why
seemingly have your own machine when you can actually have one on your desk?

Fast forwarding past operating system advances, the development of the Internet
and its protocols, and the general exponential increase in information
technology: and modern cloud providers find themselves in much the same
position as the early managers and developers of mainframe computers. The
central problem is still how to most effectively keep their machines busy and
allow users---now customers---access to compute, storage, and networking. By
virtualizing these aspects of computing, the provider takes care of the
underlying infrastructure, and allows customers to provision whatever resources
they need.

While customers can provision storage and compute capabilities in the cloud,
and run services, all these components have to talk to each other. In a
traditional network, physical devices play a large part in the creation of the
network, for example, switches connect devices and routers manage network
traffic. By using software-defined networking (SDN), these physical devices can
be abstracted and created on demand. By defining compute, storage, and network
capabilities programmatically through infrastructure-as-code, we can roll back
to a last known good configuration if recent experimental changes prove
untenable.

Since the advent of time-sharing, one of the more complex issues in managing
computer resources was maximizing the ability for multiple users or processes
to take full advantage of the hardware[^2]. Virtualization of compute, storage,
and networking in the cloud allows organizations to quickly productionize IT
infrastructure, respond to change in demand for specific resources, and avoid
many of the limitations of traditional on-prem infrastructure.


[^1]: Victoria Fedoseenko. A brief history of virtualization, or why do we divide something at all. https://www.ispsystem.com/news/brief-history-of-virtualization

[^2]: Christopher Strachey. Time sharing in large fast computers. https://archive.org/details/large-fast-computers

