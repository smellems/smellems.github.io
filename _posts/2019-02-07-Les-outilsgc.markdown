---
layout: post
title: "Les OutilsGC"
ref: gctools
date: 2019-02-06 00:00
categories: b
lang: fr
---

Depuis 2 ans et 5 mois, je suis en affectation au Secrétariat du Conseil du Trésor (SCT) dans l'équipe des OutilsGC, actuellement appelée la Division de la Mobilisation numérique.

Pas trop longtemps avant, mon équipe et moi avions gagné la compétition Code OutilsGC. Ma première tâche a été d'organiser la seconde édition, le Marathon de programmation (Hackathon) des OutilsGC qui a eu lieu le en avril 2017. Je n'avais jamais organisé un événement aussi gros (même un petit) et j'ai eu de la chance de trouver Alexandrine et Jennifer (en utilisant les micro-missions sur le Carrefour de carrière) pour m'aider avec tout ça. C'était vraiment un moment stressant avec beaucoup de courriels et de téléphones. Gérer les inscriptions, la formation des équipes et obtenir l'approbation des notes de breffage! Je me souviens d'être au Labo ISED à 6:00 du matin et de me demander si quelqu'un allait venir. Voir mon [blogue sur mon expérience d'organisation du Hackathon](https://medium.com/@DerekAlton/lessons-from-the-field-da467ea7362e#8634).

Grâce au support de mon directeur, j'ai pu passer la majorité de mon temps à travailler avec les équipes d'Architecture d'entreprise, du Gouvernement Ouvert et d'autres au SCT pour influencer les politiques, directives et orientations favorables à l'utilisation de logiciels libres et de normes ouvertes au GC. Finalement, l'équipe des OutilsGC était la cachette parfaite pour travailler avec tous les autres employés du SCT-BDPI! Voir mon autre blog sur [Faire entrer les logiciels libres et normes ouvertes dans le gouvernement du Canada](../../../2019/02/07/Faire-entrer-logiciels-libres-normes-ouvertes-dans-gc.html).

Pour le reste de mon temps, j'ai essayé d'influencer la direction des OutilsGC en proposant plusieurs applications et prochaines étapes pour, selon moi, nous mettre en meilleure position pour attirer des développeurs (hackathon, projet d'un ministère ou temps libre) à travailler avec nous sur le code, qui est disponible sur [Github](https://github.com/gctools-outilsgc). Mais aussi pour nous amener vers l'idéal que j'avais des OutilsGC.

J'aime vraiment les OutilsGC, et encore plus ce qu'ils représentent. Les outils de collaborations numériques du GC sont des logiciels libres! Ils sont utilisés à l'interne depuis plus de 10 ans et ils permettent la collaboration externe depuis plus de 2 ans. L'équipe des OutilsGC est une petite équipe interne qui assure le support, la maintenance et le bureau d'aide des outils pour les 250 000 fonctionnaires fédéraux et beaucoup plus d'utilisateurs possibles avec la collaboration externe.

En novembre 2013, une présentation au Conseil des DPI a comparé le coût de continuer à utiliser des logiciels libres avec une petite équipe agile à celui de l'acquisition d'une suite intégrée comme Sharepoint. Les logiciels libres coûtaient ~2 à 3 millions de dollars par an, les SaaS ~7 à 10 millions de dollars par an et sur les lieux (On-premises) ~12 à 30 millions de dollars par an, sans inclure le coût de la formation et de la migration du contenu des OutilsGC actuels. Ça me semble correct et c'est proche du budget réel de l'équipe des OutilsGC.

Mes recommandations pour l'avenir des OutilsGC sont les mêmes depuis le début et à un certain point j'avais convaincu la gestion puis on s'était [engagé dans la bonne direction pour mettre à jour GCconnex et GCcollab](https://github.com/gctools-outilsgc/gcconnex/tree/elgg2.3_upgrade). Jusqu'à ce qu'on choisisse une autre direction.

## Mettre à jour nos logiciels

Dans mon [deuxième blogue](https://smellems.github.io/b/2016/11/22/Developpement-outilsgc-surtout-gcconnex.html), après avoir rejoint l'équipe des OutilsGC, j'ai soulevé la problématique de l'utilisation des anciennes versions de Elgg pour GCconnex et GCcollab. Pour tirer plus d'avantages des logiciels libres que nous utilisons il faut rester à jour et profiter des améliorations et correctifs faits par la communauté.

La version de Elgg utilisée est 1.12 qui vas seulement continuer de recevoir des mises à jour de sécurité jusqu'à la sortie de Elgg 3, qui est attendu au cours des deux prochaines années. Idéalement GCconnex et GCcollab utiliseraient la plus récente version de Elgg 2 avec des plus récents _plugins_ aussi.

## Ne pas garder de _forks_

Combien de fois je me suis fait dire ça? Et je suis le premier à le dire aussi. GCconnex et GCpedia sont des _forks_ de Elgg et MediaWiki auquel des modifications ont été apportées depuis plus que 10 ans. Pas étonnant qu'il ne soit pas facile de les maintenir et de les mettre à jour, car nous devons nous assurer que nos modifications fonctionnent toujours.

Au lieu de faire des _forks_, il faudrait utiliser les versions upstream (sans modifications) des logiciels libres. La configuration et les _plugins_, modules ou extensions devraient être utilisés pour "modifier" le logiciel. Les [repos des OutilsGC](https://github.com/gctools-outilsgc) ne devraient pas avoir de _forks_ des logiciels qu'on utilise, mais plutôt nos _plugins_, nos thèmes et nos configurations (ex. : Kubernetes, Docker, etc.). Toutes modifications à des logiciels libres existants doivent être faites en collaboration avec la communauté. Par exemple pour améliorer l'accessibilité ou ajouter des traductions.

On veut être responsable du moins de code possible. En contribuant nos modifications on s'assure que les prochaines versions vont supporter nos améliorations et corrections en plus de contribuer à la pérennité du logiciel et d'influencer la direction du développement. On laisse à la communauté la tâche de continuer de supporter les logiciels libres que nous utilisons, ce qui nous permet de se concentrer sur nos besoins et ceux des utilisateurs.

## Plus de Ops, moins de Dev

Oui, les OutilsGC ont besoin de développeurs, mais je ne crois pas que nous devrions continuer de supporter des versions modifiées de logiciels libres (beaucoup de code). On ne devrait pas développer des nouvelles fonctionnalités (encore plus de code) sans utiliser un logiciel libre qui rencontre déjà la majorité des besoins. On devrait développer des thèmes si nécessaires, peut-être quelques _plugins_ et ça devrait être suffisant. J'imagine plus de gestion de l'infrastructure infonuagique, les déploiement et des mises à jours des logiciels libres utilisés plutôt que du développement actif de nouvelles fonctionnalités. Sans oublier le bureau d'aide et l'équipe de sensibilisation qui jouent des rôles très important pour supporter les utilisateurs.

## Revenir à la base

Au fil du temps, les différentes plateformes des OutilsGC ont accumulé trop de fonctionnalités différentes ce qui complique beaucoup la maintenance et le support. En plus, ces fonctions sont des fork de _plugins_ pour Elgg, intégrés directement dans le code de GCconnex et GCcollab. Les dernières versions des _plugins_ sont souvent incompatibles avec notre version de Elgg. C'est pourquoi ça serait bon de mettre en ordre nos fonctionnalités actuelles, avant d'ajouter d'autres applications pour répondre aux besoins des utilisateurs.

On a commencé en désactivant CometChat (le chat intégré dans GCconnex et GCcollab), mais j'aurais aimé aller beaucoup plus loin en désactivant les _plugins_ de forums, sondages, calendrier d'événements, idées, pages, badges de profil, sous-groupes, questions, messages, widget, dashboard. Garder seulement les groupes, discussions, blogues, j'aime (like), profile, collègues, membres, activités et biens sur le Carrefour de carrière.

## Tout le monde sur GCcollab

La mise en ligne de GCcollab a été très importante pour permettre la collaboration à l'extérieur du GC, mais a sûrement créé de la confusion chez les utilisateurs. “Est-ce que j'utilise GCconnex ou GCcollab?”

Depuis le début, le but était d'amener tous les utilisateurs de GCconnex sur GCcollab parce que cette plateforme permet la collaboration à l'externe et a l'avantage d'être hébergée sur “le nuage”. La prochaine version des OutilsGC devrait permettre à la fois la collaboration interne et externe. Il sera nécessaire de faire la migration des utilisateurs existants avec leur contenu vers la nouvelle plateforme tout en gardant la possibilité de partager des choses entre employés du GC seulement (niveaux d'accès). La même chose devrait s'appliquer à GCpedia et [GCwiki](https://wiki.gccollab.ca/Main_Page).

### Pourquoi garder Elgg?

Cette question est revenue souvent, “Pourquoi garder Elgg”? Ma réponse...”parce qu'on est déjà là”. On a déjà une expertise dans le support et le développement de la plateforme. Elgg répond aux besoins des utilisateurs parce que ses _plugins_ sont développés pour offrir les fonctionnalités de collaboration de base (ex. : groupes, discussions, collègues, etc.). GCconnex et GCcollab ne sont pas de bons exemples que Elgg ne respecte pas les exigences de performance.

La plus grande critique est que la communauté n'est pas forte, mais elle continue toujours d'avancer. Puisque la communauté n'est pas très grande, il y a une opportunité pour l'équipe des OutilsGC de contribuer au développement et d'influencer la direction. Je pense que d'autres plateformes comme Drupal, Odoo, NextCloud pourraient être bonnes, mais contrairement à Elgg, le focus de ces communautés n'est pas la collaboration numérique. La solution ne devrait pas être de développer nous-même des solutions à partir de rien.

## Suite de logiciels libres pour le GC

J'aurais aimé qu'on soit déjà rendu là - qu'on ait simplifié les OutilsGC et qu'on n'ait jamais arrêté de travailler sur la mise à jour vers Elgg 2. Une fois que ça aurait été fait on aurait pu aller de l'avant avec nos utilisateurs et ajouter des fonctionnalités à travers d'autres logiciels libres indépendants, mais regroupés par un utilisateur unique (Single Sign-on) et un portail. Et c'est là que ça devient vraiment intéressant!

On ne veut pas recréer le monolith qu'on avait avec Elgg 1. On veut créer une suite de logiciels libres à jour, auxquels on contribue pour améliorer les prochaines versions. On travaillerait aussi sur rendre la navigation entre les différents outils plus facile pour les utilisateurs. J'aurais aimé qu'on soit en une meilleure position pour démontrer que les OutilsGC sont déjà LA solution pour la collaboration numérique au GC avant l'arrivée de grosses solutions propriétaires.

Voici une liste de logiciels libres qui font déjà ou pourraient faire partie des OutilsGC sans vraiment agrandir l'équipe l'actuelle ni son financement.

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

Éventuellement, peut-être que certaines de ces applications seront incluses parmis les OutilsGC, mais ce n'est présentement pas la direction qui a été choisie. J'ai hâte de voir ce que vont devenir les OutilsGC, dans les prochaines années.
