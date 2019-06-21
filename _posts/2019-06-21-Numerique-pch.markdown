---
layout: post
title: "Numérique @ PCH"
ref: digitalpch
date: 2019-06-21 00:00
categories: b
lang: fr
---

En 2014, j'ai présenté à un événement "Dragons' Den" à Patrimoine Canadien (PCH) pour demander l'utilisation de normes ouvertes et de logiciels libres par le ministère.  J'avais été invité à participer au ARB pour présenter mes propositions plus en détails.  En 1016, je suis allé en affectation au Secrétariat du Conseil du Trésor (SCT) où nous avons vraiment fait avancé les choses avec les normes d'architectures numériques et la nouvelle Directive de la gestion des TI qui disent : "Utiliser des logiciels libres et des normes ouvertes" et "Tout code source doit être publier sous une licence de logiciel libre".  Voir mon blog [Faire entrer les logiciels libres et normes ouvertes dans le GC](https://smellems.github.io/b/2019/02/07/Faire-entrer-logiciels-libres-normes-ouvertes-dans-gc.html) pour plus de détails sur mon temps au SCT.

Depuis 5 mois je suis de retour à PCH et j'ai essayé de contribuer au changement de culture de l'organisation en proposant (encore) d'utiliser des logiciels libres pour répondre à nos besoins et aux demandes des clients. J'ai organisé un pilote pour publier du code source de PCH sous une licence de logiciel libre et aider la DGDPI à commencer à travailler ouvertement. J'ai aussi essayé d'organiser une série de présentations techniques pour inciter les développeurs et autres professionnels des TI de venir partager quelque chose d'intéressant. Finalement avec l'équipe d'architecture d’entreprise, j'ai aidé à promouvoir l'utilisation d'outils ou services infonuagique (SaaS) publique, On planifie une campagne de sensibilisation des employés et l'exploration de ce qui est déjà utilisé à PCH.

## Encan-Auction

Encan-Auction est une application Web développé par PCH pour remplacer une application LotusNotes utiliser lors de la Campagne de charité en milieu de travail du GC.  Quand j'ai envoyé un courriel à tous les gestionnaires pour savoir s’ils auraient une application ou du code source qui pourrait être rendu publique dans le but de travailler ouvertement à l'avenir, c'est ce qui a été suggéré.  Merci Laurence!

J'ai présenté au ARB de PCH pour demander l'approbation pour le pilote.  Malgré de la résistance, pas seulement pour le pilote, mais aussi en général avec les changements aux processus pour travailler ouvertement, le pilote a été approuvé.  Mais on avait quand même du travail à faire..

Avec les développeurs de l'application (en fait j'étais un des développeurs initiaux en 2016), nous avons tenté d'adresser les inquiétudes de l'équipe de sécurité au niveau du processus de développement qui pourrait maintenant inclure des personnes à l'extérieur de PCH, les droits d'accès (écriture) au code source et la divulgation de vulnérabilité de sécurité dans le code.  Nous avons enlevé les mots de passes et les configurations du code. Le code sera publier sans l'historique des modifications.  J'ai ajouté des tests d'intégrations automatisés qui ont détecté des erreurs XSS qu'il faut enlever avant de publier le code.

Pour ceux qui ont accès à GCcode, le code actuel est ici : https://gccode.ssc-spc.gc.ca/PCH/encan-auction

Le développement sera déplacer sur Gitlab dans le groupe de PCH : https://gitlab.com/pchgc

Il manque seulement les approbations finales de ATIP, le DSO et la DPI.  J'espère voir ça bientôt!  Il a été entendu, que pour l'instant seulement le code source utilisé pour des applications internes (pas publiques) et qui traite de l'information non classifié pourront être ouvert.

## Travailler ouvertement

PCH participe aux efforts du gouvernement ouvert depuis plusieurs années.  Le ministère est aussi un des 5 participants au pilote "ouvert par défaut" du GC. Mais on est pas encore ouvert avec notre code source et nos projets numériques.

Dans le but de publié l'application Encan-Auction sur Gitlab et d'ajouté des tests automatisé lors de "merge request", je voulais essayer les fonctionnalité d'intégration continue (CI) de Gitlab.  Il fallait que je travaille ouvertement..  Alors je l'ai fait (dans mon compte personnel) sans vraiment demandé la permission.  Finalement j'ai eu la permission et je l'ai bougé dans le groupe de PCH.

Voici mon application exemple PHP avec des tests qui seront executé par Gitlab CI : https://gitlab.com/pchgc/sample-php-wet

J'espère que d'autres développeurs de PCH continueront de travailler ouvertement, surtout pour des nouveaux projets.

## Culture (organisation) ouverte

Après avoir passé plus de deux ans dans une organisation très ouverte (BDPI au SCT) et une équipe encore plus ouverte (OutilsGC), je ne comprends pas que depuis mon retour à PCH, je n'ai pas eu réunion d'équipe.  Pas de réunion tous les semaines où tout le monde est mis au courant ce qui ce passe dans le context plus large et pour l'équipe, pas de "all staff" et pas de "CIO coffee chat"..  Si les choses sont incertaines, et selon les rumeurs ils le sont, la communication est encore plus importante si on veut passer au travers ensemble.

Avec les OutilsGC j'organisais une série de présentation pour l'équipe sur différent sujets. Les GCTools Tech Talks et ensuite les Digital Collaboration Division (DCD) Talks. C'était une occasion de réunir les développeurs et le reste de l'équipe pour présenter des sujets variés et intéressants. Chaque employé était encouragé de présenter quelque chose, ça n'avait même pas besoin d'être long ou d'avoir une "présentation", des fois c'était juste des discussions.  J'ai essayer d'organiser la même chose pour la DGDPI à PCH, je pensais que je n'aurais pas de problème à trouver des gens (c'est une plus grande équipe) intéressé à présenter quelque chose qui les passionne.  Personne ne ces portés volontaires..  J'ai fait deux présentations : Docker et Travailler ouvertement. La participation était quand même bonne et ça m'a permis de rencontrer l'équipe infonuagique et celle qui avait besoin d'utiliser Docker.

### Trop occupé pour changer

La meilleure excuse pour dire que tu ne veux pas faire quelque chose c'est que tu es trop occupé.  On a pas le temps pour changer nos processus ou mieux documenter, on travaille sur des choses importantes.  C'est vrai, mais il faut aussi prendre un peu de recul et regarder comment s'améliorer et s'aligner au normes numériques du GC.  Les développeurs devraient prendre 10-20% de leurs temps pour ça et pour automatisé plusieurs tâches répétitives qui vont leur permettre ensuite de faire plus de travail à valeur ajouté et même d'être plus efficace à l'avenir en plus de de travailler ouvertement.

### Expérimentation, infonuagique et Internet

Il faut un endroit où les développeurs peuvent expérimenter avec des logiciels et technologies.  Les services infonuagiques PaaS et IaaS sont parfait pour ça!  Ils peuvent être créer et supprimer rapidement et on paye seulement pour les ressources utilisées.  Une autre chose est l'accès à l'Internet (le vrai Internet) et un ordinateur de développement qu'ils peuvent configurer comme ils veulent.  Donner leurs les outils et faites leur confiance, vous les avez engager pour faire un travail..  J’aurais beaucoup aimé participé en organisant un pilote pour les subventions et contributions de PCH avec CiviCRM ou d'autres logiciels libres.

Je ne suis pas un agent libre, mais je suis resté juste assez longtemps pour commencer à ouvrir des portes pour travailler plus ouvertement à PCH. J'aurais aimer rester un peu plus longtemps, mais j'espère que l'ouverture vas continuer.  La semaine prochaine, je commence à ESDC dans l'équipe de stratégie TI.  On vas travailler pour aider l'organisation à appliquer les normes numériques et d'architecture.  #DevOps #Ouvert #LogicielsLibres #Infonuagique
