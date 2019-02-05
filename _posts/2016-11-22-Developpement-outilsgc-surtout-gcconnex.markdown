---
layout: post
title: "Développement des OutilsGC (surtout GCconnex)"
ref: gctoolsDevGCconnex
date: 2016-11-22 00:00
categories: b
lang: fr
---

(Besoin de traduction)

I've been working with the GCtools team for almost 3 months (Time flies). One of the things I wanted to do was to change the way that we develop GOtools to be more open to the contributions and also more ready to contribute to the software that we use. As you know GCconnex and GCpedia are Free Open Source Software. Elgg for GCconnex and Mediawiki for GCpedia. At PCH, I worked in a team doing agile development for more than a year before coming to TBS. We did Scrum and iterations of 3 weeks. Missing just the DevOps since we deployed into production only after 5 or 6 iterations... I thought that the development team was already working in an agile and iterative way, but it seems that this was not always the case. In the last 3 weeks, they have adopted more agile methods with iterations (sprints) of two weeks and the deployment to production every two weeks also!

In addition, for [GCconnex, GCpedia and now GCcollab all the code is on Github](https://github.com/gctools-outilsgc). But not only that, all the bugs, new features and what developers are working on, is also on Github. So if you have a bug or an request, you can create an "Issue" directly in Github. The developers are actively looking at new Issues.

For GCpedia some changes were made to the code, but especially for the theme to add the Canada heading. GCpedia uses version 1.26.2. The most recent version of this branch would be 1.26.4 and we should plan to go to version 1.27 LTS or directly to 1.28. But is not on this platform that most development is done. We use several plugins of the Mediawiki (Wikipedia) community. I need to look more into GCpedia..

- https://wiki.gccollab.ca/Special:Version
- https://www.mediawiki.org/wiki/Version_lifecycle

## The most interesting work is on GCconnex

First, I am very happy to that active development on GCconnex is now on Github. Since my participation in Code GCconnex last year, I noticed that although the code was on Github, the development was going on elsewhere (TFS). A Pull Request? What do we do with that? Now, look at the [activity in the last week](https://github.com/gctools-outilsgc/gcconnex/pulse). Things are moving fast!

Last week I shared a presentation I made on my/the vision for the future of GCconnex based on Elgg and how best to collaborate with the Elgg developers and users community. I noted that GCconnex still use Elgg version 1.12.x and that ideally we should upgrade to version 2.x soon. It's more complicated than you might think, since some plugins we use do not work with the new version. The problem is also how we develop and update Elgg and plugins. If you look at the GCconnex code on Github, it contains all the code needed to install GCconnex, all in one. What happens is that we have to support all the code of Elgg, but also of all the plugins that we use. We have made changes directly in the Elgg kernel, which is not recommended. These changes are important for the good functioning of GCconnex, but it prevents us from taking advantage of the improvements available in Elgg 2. Same thing for the plugins, we took plugins from the community and we modified them. Now these changes prevent us from simply updating the plugin with the new version, which it would work with Elgg 2. You see the problem, we end up supporting ourselves instead of taking advantage of the work of the community and adding Features specific to GCconnex. What is the solution? I have an idea, but I still asked the [question on the Elgg community site](https://elgg.org/discussion/view/2570541/elgg-and-gcconnex-collaboration).

The recommendation is to work to switch to Elgg 2 and use [Composer](https://getcomposer.org/) to install / update GCconnex. Elgg started using Composer to handle its's dependencies. Only a limited number of plugins are included with Elgg and the others can be installed and managed with Composer. To install Elgg, the recommended method is to use the [Starter-Project](https://github.com/Elgg/starter-project), which is actually an empty project whose only dependency (installed with Composer) is Elgg.

I made a version for GCconnex. It is the same but with our dependencies (plugins) in addition. Take a look at the [composer.json](https://github.com/smellems/gcconnex-starter/blob/master/composer.json).

This is where you notice the difference, each plugin is in its own repository and the installed version is managed by Composer. The code is separated. Some plugins have been created by the GC Tools team but many others come directly from the community. If we want to make changes, ideally we would do it in the original source. Of course we always have the option to support it ourselves, it is free software, but ideally we would contributes directly to the source. By separating our plugins from other third party plugins and the Elgg kernel we are more able to share our plugins with the community and contribute directly to the source code we use. This should facilitate updates, allow us to participate in Elgg's active development and even influence future direction.
