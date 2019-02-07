---
layout: post
title: "The GCTools"
ref: gctools
date: 2019-02-06 00:00
categories: b
lang: en
---

For the past 2 years and 5 months, I have been on secondment at the Treasury Board Secretariat (TBS) in the GCTools team, currently named the Digital Enablement Division.

Not too long before joining, my team and I had won the Code GCconnex competition. My first task was to organize the second edition, the GCTools Hackathon which took place in April 2017. I had never organized such a big event (even a small one) and I was lucky to find Alexandrine and Jennifer (using the Career Marketplace and micro-mission) to help me with all this. It was really a stressful time with many emails and phone calls. Managing registrations, team formation, and seeking the approval of briefing notes! I remember being at the ISED Lab at 6:00 in the morning and wondering if anyone would to show up. See my [blog on my experience of organizing the Hackathon](https://medium.com/@DerekAlton/lessons-from-the-field-da467ea7362e#a043).

Thanks to the support of my director, I was able to spend the majority of my time working with the Enterprise Architecture, Open Government and other teams at TBS to influence policies, directives and guidance that support the use of open source software and open standards in the GC. It turns out the GCTools team was the perfect hideout to work with everybody else at TBS-OCIO. See my other blog on [Getting Open Source Software and Open Standards into the GC](../../../2019/02/07/Getting-open-source-software-open-standards-into-gc.html).

For the rest of my time, I tried to influence the direction of the GCTools by proposing several applications and next steps to, in my opinion, put us in a better position to attract developers (hackathon, departmental project or free time) to work with us on the code, which is available on [Github](https://github.com/gctools-outilsgc). But also to bring us towards the ideal that I had of the GCTools.

I really like the GCTools, and even more what they represent. The GC's digital collaboration tools are open source software! They have been used internally for more than 10 years and have enabled external collaboration for more than 2 years. The GCTools team is led by a small internal team that provides support, maintenance and help desk of the tools for the 250,000 federal public servants and many more users possible with external collaboration.

In November 2013, a presentation at CIO Counsel compared the cost continuing to use open source software with a small agile team to procuring an integrated suite like Sharepoint. Open source software was ~$2-3M/yr, SaaS ~$7-10M/yr and On-premises ~$12-30M/yr, without including cost of training and migration of content from the current GCTools. That looks about right and it's close to the actual budget of the GCTools team.

My recommendations for the future of the GCTools have been the same from the beginning and at one point I had convinced management and we were moving in the [right direction to update GCconnex and GCcollab](https://github.com/gctools-outilsgc/gcconnex/tree/elgg2.3_upgrade). Until we choose another direction.

## Update our software

In my [second blog](https://smellems.github.io/b/2016/11/22/GCtools-development-especially-gcconnex.html) after joining the GCTools team, I raised this issue of using old versions of Elgg for GCconnex and GCcollab. To get more out of the open source software we use, we need to stay up to date and take advantage of the improvements and patches made by the community.

The version of Elgg used is 1.12 which will only continue to receive security updates until the release of Elgg 3, that is expected sometime in the next two years. Ideally GCconnex and GCcollab would use the latest version of Elgg 2 with the latest plugins as well.

## Do not keep forks

How many times have I been told that? And I'm the first to say so as well. GCconnex and GCpedia are forks of Elgg and MediaWiki to which modifications have been made for more than 10 years. Unsurprisingly, it's not easy to maintain and keep them up to date because we have to ensure that our modifications still work.

Instead of forks, upstream versions (without modifications) of open source software should be used. Configuration and plugins, modules or extensions should be used to "modify" the software. The GCTools repositories should not have forks of the software we use, but rather our plugins, themes and configurations (eg. Kubernetes, Docker, etc.). Any modifications to existing open source software must be made in collaboration with the community. For example, to improve accessibility or add translations.

We want to be responsible for as little code as possible. By contributing our modifications we ensure that future versions will support our improvements and corrections in addition to contributing the sustainability of the software and influencing the direction of development. We leave it to the community to continue to support the open source software we use, which allows us to focus on our needs and those of the users.

## More Ops, less Dev

Yes, the GCTools need developers, but I don't think we should continue to support modified versions of open source software (lots of code). We shouldn't develop new features (even more code) without using open source software that already meets the majority of needs. We should develop themes if necessary, maybe a few plugins and that should be enough. I imagine more management of the cloud infrastructure, deployment and updates of the open source software used rather than active development of new features. Not to mention the help desk and the outreach team, which play very important roles supporting users.

## Back to Basics

Over time the various GCTools platforms have accumulated too many different features which makes maintenance and support difficult. In addition, these functions are forks of Elgg plugins, integrated directly into the GCconnex and GCcollab code. The latest versions of plugins are often incompatible with our version of Elgg. That's why it would be beneficial to tidy up our current functionalities before adding other applications to meet users' needs.

We started by disabling CometChat (the integrated chat within GCconnex and GCcollab), but I would have liked to have gone further by disabling various plugins such as: forums, surveys, event calendar, ideas, pages, profile badges, subgroups, questions, messages, widget, dashboard. Keep only the groups, discussions, blogs, likes, profile, colleagues, members, activity and of course the Career Marketplace.

## Everyone on GCcollab

The introduction of GCcollab has been very important to enable collaboration outside the GC, but has certainly created confusion among users. “Do I use GCconnex or GCcollab?” 

From the beginning the goal was to bring all GCconnex users to GCcollab because this platform allows external collaboration and has the advantage of being hosted on "the cloud". The next version of the GCTools is expected to enable both internal and external collaboration. It will be necessary to migrate existing users with their content to the new platform while keeping the possibility of sharing between GC employees only (access levels). The same should apply for GCpedia and [GCwiki](https://wiki.gccollab.ca/Main_Page).

### Why keep Elgg?

This question has come up often, “Why keep Elgg”? My answer...“because we are already there”. We already have expertise in the support and development of the platform. Elgg meets the users' needs because its plugins are developed to offer basic collaboration features (eg. groups, discussions, colleagues, etc.). GCconnex and GCcollab are not good examples that Elgg does not meet performance requirements. 

The biggest criticism is that the community is not strong, but it still keeps moving forward. Since the community is not very large, there is an opportunity for the GCTools team to contribute to development and influence the direction. I think other platforms like Drupal, Odoo, NextCloud could be good, but unlike Elgg, the focus of these communities is not digital collaboration. The solution should not be to develop it ourselves from scratch.

## Open source software suite for the GC

I wish we were already there - that we had simplified the GCtools by removing several features and had never stopped working on the Elgg 2 update. Once that would have been done we could have gone ahead with our users and added features through other independent open source software, but grouped by a single user (Single Sign-on) and a portal. And that's when it gets really interesting!

We don't want to recreate the monolith we had with Elgg 1. We want to create a suite of up-to-date open source software, to which we contribute to improve future versions. We would also work on making it easier for users to navigate between the different tools. I wish we were in a better position to show that the GCTools are already THE solution for digital collaboration in the GC before the arrival of large proprietary solutions.

Here is a list of open source software that is already or could be part of the GCTools without really expanding the current team or its funding. 

- Keycloak (Account)
- Elgg (Collab, Profile and Career)
- MediaWiki (Wiki)
- RocketChat (Message)
- Jitsi (Videoconference)
- Etherpad (Collab Notepad)
- Ethercalc (Collab Spreadsheet)
- OSEM (Event Mangement)
- Limesurvey (Survey)
- Loomio (Idea and Decision) 
- Taiga (Project)
- Gitlab (Code)
- Lufi (File sharing)
- Matamo (Analytic)
- Polr (Link shortner)
- Gitlab pages (Website)
- Bonita BPM (Workflow)

Perhaps some of these applications will eventually be included in the GCTools, but it is not currently the direction that has been chosen. I look forward to seeing what the GCTools will become in the next few years.
