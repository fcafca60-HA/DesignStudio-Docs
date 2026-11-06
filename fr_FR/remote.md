---
layout: default
permalink: /fr_FR/remote.html
title: Site distant PHP/React
---

# Site Web distant en lecture seule

Le site distant reçoit les pages et valeurs INFO publiées par Design Studio et utilise un **moteur React compilé de même version** que le plugin Jeedom. Il ne peut pas exécuter les commandes ACTION.

## Préparation du serveur PHP

1. Préparer un hébergement HTTPS prenant en charge PHP.
2. Installer le récepteur PHP distant. Un **starter de référence historique** est fourni dans la branche Beta sous `resources/designstudio-remote-php-starter-0.90.39.zip`. Vérifiez les règles de sécurité et la compatibilité de votre hébergeur avant une nouvelle installation de production ; ne remplacez pas une instance distante existante qui fonctionne par un starter plus ancien.
3. Conserver **`config.php`**, **`private/`**, les identifiants d'installation et la clé HMAC lors des mises à jour.
4. Configurer la même clé HMAC dans la fiche Jeedom, rubrique **Publication distante**, en renseignant l'URL HTTPS de réception `.../api/push.php` et la sélection des pages.
5. Cliquer **Publier maintenant** puis vérifier le résultat et les journaux.

## Installer le frontend React distant

Le workflow de publication GitHub Beta génère `resources/designstudio-remote-react-assets.zip`. Décompressez **son dossier `react/`** à la racine de l'application PHP. Cette archive n'est pas le récepteur PHP ; elle contient le moteur React et CSS du Dashboard.

À chaque évolution du code React, utilisez le bundle de **la version correspondante**. La modification de données, de couleurs, de tuiles ou de pages dans Jeedom ne nécessite généralement pas de nouveau bundle React, si les composants sont déjà pris en charge.

## Rafraîchissement et sécurité

- Les valeurs sont publiées de Jeedom vers le site PHP selon la fréquence configurée et au clic sur **Publier maintenant**.
- Le navigateur distant peut actualiser les données reçues sans exécuter de commandes Jeedom.
- N'envoyez jamais vos clés et mots de passe dans les captures ou dans le dépôt GitHub public.
- Le dossier `private/` doit rester protégé de tout accès Web ; les scripts d'installation ne doivent pas rester librement exposés après configuration.

[Retour au guide](./) · [QuickStart](./quickstart.html)


## Animations festives 0.90.57

Dans **Connexion Jeedom > Animations événementielles**, sélectionnez une commande INFO texte Jeedom puis définissez le niveau **Simplifié**, **Normal** ou **Dense**, et la vitesse. Les thèmes (NOEL, NOUVEL_AN, PRINTEMPS, ETE, AUTOMNE, HIVER, FETE, HALLOWEEN, PAQUES) peuvent tous être prévisualisés avec **Tester l'animation**, même sans commande Jeedom configurée. **Arrêter le test** revient au pilotage Jeedom sans écrire dans ses commandes. Les animations sont désactivées par défaut. Pour OVH, mettez à jour le bundle React distant de la même version et republiez les informations.
