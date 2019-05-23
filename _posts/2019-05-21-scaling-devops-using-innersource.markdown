---
layout: post
title:  Scaling Devops Using Inner Source
date:   2019-05-22 1:20
description: How do you scale Devops best practices across multiple product teams and maintain consistency and reliability of your tooling, automation, and culture? Inner source is more supportable in the long run and can help give teams the flexibility they need to succeed in releasing code that is built, tested, and deployed consistently.
---


Let's say you're part of a small team of go-get-em engineers, eager to develop amazing software and using the latest of software trends and technologies. You've got your SDLC at it's golden state, with automated testing, containers everywhere and with Kubernetes to manage it all. Your team is the epitome of agile. You ship software consistently and receive immediate success. Because of this, your team begins to grow. You begin splitting and forming more teams, while adding only the best talent to undergo widening of the applications' scope and service offerings.

You've added more and more features under your project. Eventually, the teams decide we need microservices architecture to continue to grow quickly. Apps begin splitting and teams work on their own automation and CI/CD pipeline processes. 6 months down the line, multiple teams are handling deployments and testing in completely different ways, making it an operational nightmare and every other deployment needs to be rolled back due to misconfiguration issues and support overhead is really killing the teams. Team members inevitably move onto different things and leave spaghetti code for others to support (_good luck_) and the number of new released features seem to be fewer and farther between compared to when the team was smaller.

<div class="img_row">
  <img class="col three" src="{{ site.baseurl }}/img/posts/2019-05-21-scaling-devops-using-innersource/this_is_fine.jpg" alt="" title="example image"/>
</div>
<br/>

Okay so that was probably an exaggeration, but you get the idea. As development orgs grow, there are naturally some growing pains. To maintain nimble, agile practices, there needs to be consistency between how apps handle their SDLC, especially applications that have a similar technology stack.

As your team begins to grow, you will see these signs as well. There will be natural break points where pieces of code become unmanageable or highly replicated between different applications. Over time, the same "problem" ends up getting solved 20+ ways, wasting dev and support cycles creating and maintaining these pieces. This is where I feel Inner source naturally comes into the picture for organizations following DevOps and Agile methodologies.

<br/>
#### What is inner source?

Quoting the king of information on the web ([en.wikipedia.org/wiki/Inner_source](https://en.wikipedia.org/wiki/Inner_source)) Inner source is the use of open source software development best practices and the establishment of an open source-like culture within organizations. The organization may still develop proprietary software, but internally opens up its development.

> ### _"we must work together to succeed as an organization, not just a team."_

Inner source for your SDLC gives you:
- consistency between applications
- supportability (less code to maintain)
- flexibility for teams to add/edit features in shared inner source projects
- visibility as opposed to a separate team supporting that project
- the entry point into GitOps in your organization ([weave.works/technologies/gitops/](https://www.weave.works/technologies/gitops/))
- a catalyst for collaboration between multiple teams

At the heart of it, Inner source is the macro answer to the DRY principle ([codementor.io/joshuaaroke/dry-code-vs-wet-code-89xjwv11w](https://www.codementor.io/joshuaaroke/dry-code-vs-wet-code-89xjwv11w)). But to really implement it, you'll need a culture change. Traditionally, when teams are solely responsible to develop and ship code, there can be pushback on inner sourcing because teams feel less _in control_ or don't want extra contraints to developing in a way that's more difficult or even not possible. Collaboration is key here. Just like a scrum team agree to completing some stories in a sprint, for inner source to work, incubate the thought of _"we must work together to succeed as an organization, not just a team."_

<br/>
#### Don't jump just yet, plan the dive first

Before starting any technical endeavor, it's always good to plan first. This is especially true for inner source. One thing you'll want to consider, is what you actually want to solve. Like mentioned before, you'll begin to see those WET pieces of code in your SDLC processes, like deployment of two very similar apps happening almost identically, or maybe your infrastructure isn't even stored in code, these maybe be good times to develop a process for maintaining these peices in a more centralized way. Please remember - implementing this is not an easy ordeal, it'll take more than one day. It'll require real work and planning to execute effectively. Getting approval and support from your management can really help in this process.

<br/>
#### Establish ownership over projects

Once you have a plan in place, it's good to have someone(s) to maintain the project. Think just like an open source project, someone who understands the domain and can provide guidance on the roadmap for that project. You will need people to review and approve PRs as they come in just like any application.

<br/>
#### A mature CI/CD process

Again, just like any other application you're building, a mature SDLC and automation is necessary for consistency and supportability of your inner source projects. Without a proper way to build and test changes, you're going to have a bad time and this project will become a chore more than it'll actually help.

<br/>
#### Begin with one project, slowly adopt when you get some wins

Start your inner source implementation with one project or piece first. Like mentioned earlier, many teams are only going to get on the bandwagon when they feel it's safe to do so. Having a good track record will only help show definitive proof that inner source will work for your organization. Part of this is providing an easy adoption, which means writing as many docs and training as possible. Go ahead and plan to put some cycles to supporting the transition for teams, by answering questions and general training. Also provide some way to get feedback from teams. This will help show you how teams are adopting, what can be improved, and if you're tackling the correct things the right way.

> ### _just like any other application you're building, a mature SDLC and automation is necessary for consistency and supportability of your inner source projects._

<br/>
#### Example: Terraform
For our organization, we were planning the move from AWS to GCP. We decided that having Infrastructure as Code (IaC) is a must. The industry leader in this is Terraform ([terraform.io](https://www.terraform.io/)). But what we found difficult was managing the change control and automation of terraform across an entire org. We decided to have the following separation of responsibilities and projects:

- `terraform-modules`: Git repository where shared modules will live
- `terraform-team-project`: Git repository where a team can manage their GCP projects (one set of terraform scripts to manage all team GCP projects - dev, staging, and prod)

This allowed us to scale quickly and give the reigns to the teams and give them enough flexibility while also providing a good process that keeps things DRY.

<br/>

Yes, inner source sounds like a big effort, especially with teams that show pushback. On top of that, if implemented incorrectly, it can lead to an opposite effect on communication and effectiveness. But in the connected world we live in, collaboration is the only way we can truly succeed in providing the best capabilities and services, and a big part of that is how we ship code. Inner source helps to organize and structure these processes so that adoption and scale can be achieved no matter the size of your organization.



<strong>--JG</strong>
