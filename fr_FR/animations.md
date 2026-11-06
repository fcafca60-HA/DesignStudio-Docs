---
layout: default
permalink: /fr_FR/animations.html
title: Animations festives Design Studio
---

# Animations festives - V0.90.57 Beta

Les animations s'affichent au-dessus du Dashboard sans intercepter les clics. Elles sont désactivées par défaut.

## Démarrer

1. Dans **Connexion Jeedom**, ouvrir **Animations événementielles du Dashboard**.
2. Sélectionner une **commande INFO texte** qui indique le thème demandé (`NOEL`, `NOUVEL_AN`, `PRINTEMPS`, `ETE`, `AUTOMNE`, `HIVER`, `FETE`, `HALLOWEEN`, `PAQUES` ou `OFF`).
3. Cocher **Activer le pilotage par Jeedom**.
4. Choisir le niveau **Simplifié**, **Normal** ou **Dense** ; régler la vitesse, les pages et le smartphone.
5. Cliquer sur **Tester l'animation** pour prévisualiser le thème choisi. **Arrêter le test** rend immédiatement la main à Jeedom, sans modifier la commande.

## Choisir le niveau

| Niveau | Scène affichée |
|---|---|
| **Simplifié** | Bandeau décoratif léger et environ 10 particules |
| **Normal** | Bandeau, personnages (dont le traîneau de Noël), éléments latéraux et 24 particules |
| **Dense** | Décors complets autour du Dashboard, scintillements et 42 particules |

Les anciens réglages `low`, `medium`, `high` restent compatibles : ils représentent respectivement Simplifié, Normal et Dense.

## Effets proposés

- **Noël** : Père Noël et traîneau, rennes, sapins, guirlandes, cadeaux, étoiles et neige.
- **Nouvel An** : feux d'artifice, confettis, compte à rebours décoratif.
- **Printemps** : fleurs, pétales, papillons et feuillage.
- **Été** : soleil, palmiers, décor de vacances.
- **Automne** : feuilles et tons chauds ; **Hiver** : cristaux et bonhommes de neige.
- **Fêtes** : ballons et confettis ; **Halloween** : citrouilles et chauves-souris ; **Pâques** : fleurs et œufs.

## Performance et sécurité

Aucune commande ACTION n'est exécutée et aucune requête AJAX supplémentaire n'est déclenchée par l'animation. Sur smartphone, les décors volumineux sont volontairement masqués. La préférence système de réduction des mouvements arrête les effets. Le calque a `pointer-events: none`.

## Site Web distant

La même animation peut apparaître sur OVH à condition de publier la commande INFO et les paramètres, puis d'installer le bundle React distant **de la même version**. Le récepteur PHP et ses secrets ne doivent pas être remplacés pour une simple mise à jour des décors.
