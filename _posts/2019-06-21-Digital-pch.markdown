---
layout: post
title: "Digital @ PCH"
ref: digitalpch
date: 2019-06-21 00:00
categories: b
lang: en
---

In 2014, I presented at a "Dragons' Den" event at Canadian Heritage (PCH) to request the use of open standards and open source software by the department.  I had been invited to participate in the ARB to present my proposals in more detail.  In 1016, I went on assignment to the Treasury Board Secretariat (TBS) where we really made progress with the digital architecture standards and the new IT Management Directive that say: "Use open source software and open standards" and "All source code must be published under an open software license".  See my blog [Getting Open Source Software and Open Standards into the GC](https://smellems.github.io/b/2019/02/07/Getting-open-source-software-open-standards-into-gc.html) for more details on my time at TBS.

For the past 5 months I have been back at PCH and have tried to contribute to the culture change of the organization by proposing (again) to use open source software to meet our needs and customer demands. I organized a pilot to release PCH source code under an open source license and help CIOB start working in the open. I also tried to organize a series of technical presentations to encourage developers and other IT professionals to come and share something interesting. Finally, with the enterprise architecture team, I helped promote the use of public cloud tools or services (SaaS), we are planning an employee awareness campaign and exploring what is already being used at PCH.

## Encan-Auction

Encan-Auction is a web application developed by PCH to replace a LotusNotes application used during the GC Workplace Charitable Campaign.  When I sent an email to all managers to find out if they would have an application or source code that could be made public in order to work openly in the future, that what was suggested.  Thanks Laurence!

I presented to the PCH ARB to request approval for the pilot.  Despite resistance, not only for the pilot, but also in general with changes to processes to work openly, the pilot was approved.  But we still had work to do..

With the application developers (in fact I was one of the original developers in 2016), we tried to address the security team's concerns about the development process which could now include people outside PCH, access rights (writing) to source code and disclosure of security vulnerabilities in code.  We have removed the passwords and code configurations. The code will be published without the change history.  I added automated integration tests that detected XSS errors that need to be removed before publishing the code.

For those who have access to GCcode, the current code is here: https://gccode.ssc-spc.gc.ca/PCH/encan-auction

The development will be moved to Gitlab in the PCH group: https://gitlab.com/pchgc

Only the final approvals of ATIP, DSO and CIO are missing.  I hope to see it soon!  It was agreed that for the time being, only source code used for internal (not public) applications that deal with unclassified information may be opened.

## Working in the Open

PCH has been involved in open government efforts for several years.  The department is also one of 5 participants in the GC's "open by default" pilot. But we're not yet open with our source code and digital projects.

In order to publish the Encan-Auction application on Gitlab and add automated tests during "merge request", I wanted to try Gitlab's continuous integration (CI) functionality.  I had to work in the open..  So I did (in my personal account) without really asking permission.  Finally, after explaining that this was only test code, I got permission and moved it into the PCH group. 

Here's my sample PHP app with some tests that will run in Gitlab CI : https://gitlab.com/pchgc/sample-php-wet

I hope that other PCH developers will continue to work openly, especially for new projects.

## Open culture (organization)

After spending more than two years in a very open organization (OCIO at TBS) and an even more open team (GCTools), I don't understand that since my return to PCH, I haven't had a team meeting.  No weekly meeting where everyone is informed about what is happening in the wider context and for the team, no "all staff" and no "CIO coffee chat"..  If things are uncertain, and according to rumours they are, communication is even more important if we want to get through it together.

With the OutilsGC I organized a series of presentations for the team on different topics. The GCTools Tech Talks and then the Digital Collaboration Division (DCD) Talks. It was an opportunity to bring together the developers and the rest of the team to present varied and interesting topics. Each employee was encouraged to present something, it didn't even have to be long or have a "presentation", sometimes it was just discussions.  I tried to organize the same thing for CIOB in PCH, I thought I wouldn't have any problem finding people (it's a larger team) interested in presenting something that they are passionate about.  No one volunteered..  I made two presentations: Docker and Working in the Open. The participation was still good and it allowed me to meet the cloud team and the one that needed to use Docker.

### Too busy to change

The best excuse to say you don't want to do something is that you're too busy.  We don't have time to change our processes or better document, we're working on important things.  That's true, but you also need to step back and look at how to improve and align yourself with the GC digital standards.  Developers should take 10-20% of their time for this and for automating several repetitive tasks that will then allow them to do more value-added work and even be more efficient in the future in addition to working openly.

### Experimentation, Cloud and Internet

There needs to be a place where developers can experiment with software and technologies.  The PaaS and IaaS cloud services are perfect for this!  They can be created and deleted quickly and we only pay for the resources used.  Another thing is access to the Internet (the real Internet) and a development computer that they can configure as they please.  Give them the tools and trust them, you hired them to do a job..  I would have very much liked to have participated by organizing a pilot for PCH grants and contributions with CiviCRM or other open source software.

I am not a free agent, but I stayed just long enough to start opening doors to work more openly at PCH. I would have liked to stay a little longer, but I hope that the openness will continue.  Next week, I'm starting at ESDC in the IT strategy team.  We will work to help the organization apply digital and architectural standards.  DevOps #OpenSourceSoftware #Cloud
