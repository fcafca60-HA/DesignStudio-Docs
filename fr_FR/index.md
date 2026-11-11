> **Version actuelle : V0.90.70-beta** — Nouvelle tuile WLED et copie des GIF/images des Virtual via Copier Style.

---
layout: default
permalink: /fr_FR/
title: Jeedom Design Studio - Guide utilisateur
---

# Jeedom Design Studio

**Version 0.90.70-beta — WLED, correctif de copie des GIF Virtual (validation Jeedom en attente)**

Créez et personnalisez des pages de supervision Jeedom : tuiles interactives, températures, éclairage, énergie, thermostats, historique, Smart Layout, seuils de couleurs, animations et mode Kiosque.

> Version Beta : faites une sauvegarde de vos pages avant la mise à jour et vérifiez les autorisations des utilisateurs.

> **Licence :** utilisation gratuite dans les conditions de la [licence non commerciale](./licence.html). Toute exploitation commerciale du logiciel nécessite une autorisation écrite préalable.

## Accès rapide

- [Licence et conditions d’utilisation](./licence.html)
- [Démarrer en quelques étapes](./quickstart.html)
- [Historique des changements](./changelog.html)
- [Tutoriels et vidéos](./tutoriels.html)
- [Animations festives - Simplifié / Normal / Dense](./animations.html)
- [Site Web distant PHP/React](./remote.html)
- [Aide détaillée intégrée](./help.html)
- [QuickStart illustré (PDF)](./QuickStart_DesignStudio.pdf)

## Installation via le Market Jeedom (Beta)

1. Dans Jeedom, ouvrez **Plugins > Gestion des plugins > Market**.
2. Recherchez **Jeedom Design Studio**, puis choisissez **Installer beta**.
3. Activez le plugin et réglez les autorisations.
4. Ouvrez **Plugins > Organisation > Jeedom Design Studio**.
5. Dans l'éditeur, sélectionnez **+ Jeedom > Importer TOUT le Dashboard Jeedom**.
6. Vérifiez les types des équipements proposés, cliquez sur **Créer le Dashboard validé** et enregistrez.

**Aucune compilation React ni installation de Node.js n'est nécessaire avec la version GitHub/Market Beta**, car les fichiers React sont précompilés dans `app/`. La version File destinée aux essais peut en revanche nécessiter `build_frontend.sh`.

## Modifier les tuiles

- **Propriétés > Données** : relier les commandes INFO/ACTION du bon équipement Jeedom.
- **Propriétés > Style** : couleurs, polices, halos, Smart Layout et seuils dynamiques.
- **Propriétés > Visibilité** : afficher ou masquer des éléments selon les commandes disponibles.
- **Copier Style / Coller Style** : appliquer un style à plusieurs tuiles compatibles, sans modifier leurs données ni leurs positions.
- **Pages** : laisser la mise en page automatique ou définir une résolution personnalisée avec défilement.

## Animations évènementielles (0.90.57)

Dans **Connexion Jeedom > Animations évènementielles**, associez une commande INFO texte aux valeurs `OFF`, `NOEL`, `NOUVEL_AN`, `PRINTEMPS`, `ETE`, `AUTOMNE`, `HIVER`, `FETE`, `HALLOWEEN`, `PAQUES`. Vous pouvez **tester chaque effet manuellement** sans écrire dans Jeedom ; arrêter le test rétablit le pilotage normal par la commande INFO.

## Site distant PHP/React

La publication distante est facultative. Elle transmet uniquement les pages choisies et les valeurs INFO vers un site PHP sous HTTPS, signé avec une clé HMAC. Le site déporté est en **lecture seule** ; il utilise le même moteur React et ne peut pas exécuter de commandes Jeedom.

1. Installer et configurer le site PHP distant avec son identifiant d'installation et une clé HMAC distincte.
2. Dans Jeedom, ouvrir la **Publication distante** du plugin, fournir l'URL API HTTPS et la même clé, puis choisir les pages.
3. Publier maintenant pour tester. Le rafraîchissement récurrent utilise la fréquence configurée.
4. Sur le serveur distant, placer le bundle React de la **même version** sous `react/` ; le workflow GitHub génère `resources/designstudio-remote-react-assets.zip` dans la branche `beta`.
5. Ne jamais écraser `config.php` ni `private/` lors d'une mise à jour du site distant.

## Sécurité et sauvegarde

Le projet Design Studio est stocké localement dans `plugins/designstudio/data/project.json`. **Exportez votre projet avant un import complet ou une mise à jour majeure.** Les droits d'exécution des commandes sont toujours ceux de Jeedom. Les secrets HMAC ne doivent jamais être publiés sur GitHub.


## Animations festives 0.90.57

Dans **Connexion Jeedom > Animations événementielles**, sélectionnez une commande INFO texte Jeedom puis définissez le niveau **Simplifié**, **Normal** ou **Dense**, et la vitesse. Les thèmes (NOEL, NOUVEL_AN, PRINTEMPS, ETE, AUTOMNE, HIVER, FETE, HALLOWEEN, PAQUES) peuvent tous être prévisualisés avec **Tester l'animation**, même sans commande Jeedom configurée. **Arrêter le test** revient au pilotage Jeedom sans écrire dans ses commandes. Les animations sont désactivées par défaut. Pour OVH, mettez à jour le bundle React distant de la même version et republiez les informations.


## Caméra Jeedom — 0.90.62 GitHub Beta

La tuile Camera est **générique** : elle utilise l’identifiant d’un équipement du plugin Camera officiel, jamais une URL propre à une marque. Dans **+ Jeedom > Importer TOUT le Dashboard Jeedom**, les équipements `camera` sont proposés même sans commande INFO ; le type Caméra est reconnu automatiquement. Vérifiez la sélection avant de créer le dashboard ; un import complet remplace le projet courant.

Dans **Propriétés > Style**, choisir un rafraîchissement **Manuel / 2 / 5 / 10 / 30 / 60 secondes** et le cadrage **Contenir / Remplir**. Un clic sur l’image l’agrandit. Le proxy Jeedom sert un JPEG pour les sources HTTP JPEG/MJPEG ; pour les autres configurations il utilise `getSnapshot()` du plugin Camera officiel, avec des résultats qui dépendent du modèle et de la configuration. Pas de PTZ dans cette tuile. Les flux et identifiants caméra ne sont **jamais publiés vers OVH** ; sur le site distant la tuile n’affiche pas la vidéo. Le proxy exige une session Jeedom et les droits de l’équipement.

La version **GitHub Beta/Market** comporte le front-end React précompilé par GitHub Actions. Il ne faut pas lancer `build_frontend.sh` après une installation depuis le Market.


## Vérification Config — Beta 0.90.63

Dans l’éditeur, cliquez sur **🛡 Vérification Config** après **Enregistrer Jeedom** pour identifier les commandes absentes, les thermostats non résolus, les erreurs de type INFO/ACTION et les actions communes à plusieurs tuiles. Le diagnostic est en lecture seule. [Aide complète](./help.html).


### Nouveau en V0.90.69-beta : placement fin par page

Dans **Paramètres de la page → Dimensions du canevas**, choisissez la grille historique de 12 colonnes (par défaut) ou une grille de 24/48 colonnes pour placer plus précisément les widgets sur des fonds de plan. Aucune ancienne page n’est convertie automatiquement. La conversion est explicitement confirmée, avec refus si une réduction provoquerait des collisions ou débordements. Grille visuelle facultative en conception uniquement. Les tuiles Texte Micro utilisent leurs paramètres de police, fond, alignements et animations.

**Version beta non validée sur Jeedom :** déploiement Market interdit jusqu’aux tests manuels.
