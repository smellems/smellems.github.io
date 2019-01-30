---
layout: post
title: "Positif, positif, positif…"
ref: positive
date: 2014-08-25 00:00
categories: b
lang: fr
---

Positif, positif positif positif... ok.  On vas parler de choses positives.  Le Canada fait surement des bonnes choses pour augmenter leur utilisation de logiciels libres et de formats standards ouverts.   Ces deux administrations publiques sont-ils comme les autres grandes organisations: ils utilisent du open source sans le savoir et malgré le (ou à cause du) manque de position clair sur les logiciels libres?  Voyons ce qui en est.

**Presque tous les liens dans cet article sont vers des site qui sont seulement accessible par les employés du gouvernement du Canada.  Désolé pour les autres.**

## Vieille position du Canada

Le document est vieux, mais il existe.  Le dernier document officiel qui explique la [position du Gouvernement du Canada à propos de l'utilisation de logiciels libres](http://www.collectionscanada.gc.ca/webarchives/20071212130456/http://www.tbs-sct.gc.ca/fap-paf/oss-ll/position_e.asp) date de 2007.  PAF!

> Le Programme d'architecture fédérée (PAF) constitue un ensemble de principes directeurs qui orientent le développement des systèmes de technologie de l'information. Un certain nombre de ces principes se retrouvent dans une série de lignes directrices relatives à divers sujets, y compris les logiciels libre, qui sont présentement diffusées ou le seront sous peu.

En ce qui concerne les lignes directrices relatives à l'utilisation de logiciels libre, les quatre principes ci-après sont applicables :

### Réduction de la complexité de l'intégration

Favoriser la réduction de la complexité et permettre une intégration aussi généralisée que possible.  Les applications devraient être « hautement modulaires » et « faiblement couplés » pour favoriser la réutilisation des composantes.  La modularité, le faible couplage et la réutilisation sont des principes fondamentaux des méthodes de développement agiles.  Ces pratique sont généralement adoptés par les communautés de développement de logiciels libres.  Les formats de données standard et l'application des normes TI ouvertes sont largement pris en charge dans les logiciels libres.  L'accès actuel et futur à l'information est garanti à tous par la disponibilité du code source et l'utilisation de formats de données standard.

### Sécurité, confidentialité, protection de l'information et protection des renseignements personnels

Les systèmes de TI doivent être mis en place conformément aux politiques et lois gouvernementales touchant la sécurité, la confidentialité et le respect des renseignements personnels. L'information doit être protégée contre tout accès non autorisé, déni de service et modification, que ce soit intentionnel ou accidentel.  Les logiciels propriétaires n'ont pas démontré qu'ils sont à la hauteur de ces attentes.  La disponibilité du code source permet la révision et la validation de la sécurité des logiciels libres.  Les failles de sécurité sont rapidement identifiées et corrigées.

### Utilisation de normes et de technologies éprouvées

Les solutions de TI doivent utiliser des technologies fiables et basées sur des normes dans le but de réduire la dépendance à l'égard de fournisseurs.  Il existe plusieurs logiciels libres de grande qualité, qui ont faits leurs preuves en entreprises.  Ceux ci sont disponibles, souvent gratuitement, pour utilisation ou modification.  Certains sont maintenant considérés aussi matures et fonctionnels que leurs équivalents propriétaires.

### Coût total de possession

Il faut chercher l'équilibre entre deux ensembles de facteurs : d'une part, les coûts de développement, de soutien, de reprise après sinistre et de retrait, et d'autre part, les coûts associés à la souplesse, à l'évolutivité, à la facilité d'utilisation/de soutien pendant le cycle de vie de la technologie ou de l'application.  Des organisations et des gouvernements ont déclaré avoir réduit le coût total de possession de leurs technologies en utilisant plus de logiciels libres.  Les économies proviennent entre autre des coûts d'administration, de support et de mise à jour.  L'administration de logiciels libres ne demande pas autant de personnel et le prix des mises à jour est négligeable vous donnant ainsi l'avantage de pouvoir rester à jour avec les nouvelles versions en tout temps.  Le résultat est l'amélioration des logiciels que vous utilisez, l'augmentation de la sécurité et de la fiabilité à un coût réduit.

Donc, les logiciels libres répondent aux critères techniques du PAF. Les logiciels libres sont considérés comme des logiciels commerciaux (COTS) et peuvent être comparé aux logiciels propriétaires.   Par contre, on peut lire que pour réduire la complexité de l'intégration, il faut réduire au minimum le nombre de fournisseurs.  Ce critère pourrait limiter l'utilisation de logiciels libres puisque ceux-ci sont souvent distribués par plusieurs fournisseurs indépendants.  Il serait plus important de réduire la dépendance à un fournisseur particulier tout en augmentant l'utilisation de formats de données standard et l'application des normes TI ouvertes facilitant l'intégration.  On risque aussi d'obtenir des meilleurs prix si plusieurs fournisseurs peuvent offrir le support pour un même logiciel libre.

C'est bien quand c'est présenté comme ça, mais dans la réalité on aime nos vieux fournisseurs…  Positif positif positif…

## Logiciels libres utilisés présentement

Selon le « Catalogue de logiciles » sur GCpedia, certains ministères (Environnement, Santé, Travaux Publiques et Agriculture) ont commencé à tester et utiliser des systèmes d'exploitation libres basés sur Linux ou BSD.  Les navigateurs web FireFox et Chrome sont aussi utilisé un peu partout par ceux qui ont le droit de les installer sur leur poste de travails.  L'application de gestion de projets Redmine est utilisée par Santé Canada et l'Office national du film.  Les systèmes de gestion de contenu web (CMS) sont très populaire et plusieurs site web du gouvernement utilisent des logiciels libres.  Drupal est utilisé par plusieurs ministères comme : Agriculture, Services frontaliers, École de la fonction publique, Transport, Défense Nationale, Pêches et océans, Industrie, Ressources naturelles, Travaux publiques, Statistiques.

C'est correct, mais on remarque le manque de direction.  Les prochains exemples sont des applications Web disponible à tous les employés sur le réseau du GC.

### GCpedia - MediaWiki

GCpedia est le WikiPedia du GC et il utilise le même logiciel libre, c'est à dire MediaWiki.  Il y a beaucoup de contenu du GCpedia mais c'est pas toujours très organisé et les traductions ne sont pas toutes faites.

### GCconnex - Elgg

GCconnex est le réseau social du GC et il fonctionne sur Elgg, un logiciel libre qui imite les fonctionnalités de bases de Facebook.

### GCcode GitLab

GCcode est basé sur Gitlab, un logiciel libre qui offre les mêmes fonctionnalités que GitHub.  C'est donc une plateforme pour que les employés publient leurs codes sources en utilisant le système de gestion de version Git.  Le but est de favoriser la collaboration.  Je crois que c'est assez nouveau, il y a présentement 10 projets publics sur l'Intranet du GC.

### WET-BOEW

Finalement, je pense qu'on ne peut pas parler de logiciels libres au gouvernement du Canada, sans parler de la Boite â Outils de l'Expérience Web (BOEW) développé par le Conseil du Trésor.  Elle rassemble différents composants réutilisables et prêts-à-utiliser pour la conception et la mise à jour de sites Web innovateurs en assurant la normalisation des sites Internet. Tous ces composants réutilisables sont des logiciels libres mis à la disposition des ministères et des collectivités Web externes.  Le projet est public sur GitHub.

Pas pire.
