---
layout: default
permalink: /fr_FR/changelog.html
title: Historique des versions
---

# Changelog - Jeedom Design Studio

## 0.90.57-beta - Animations festives enrichies
- Noël : Père Noël et traîneau avec rennes, sapins, cadeaux, guirlandes, étoiles et neige.
- Nouvel An : feux d'artifice, compte à rebours décoratif, confettis et célébrations.
- Saisons et fêtes : compositions propres au printemps, à l'été, à l'automne, à l'hiver, à Halloween et à Pâques.
- Trois niveaux au choix : **Simplifié**, **Normal** et **Dense**. Compatibilité des valeurs enregistrées `low`, `medium`, `high`.
- Test manuel de chaque thème sans modifier la commande INFO Jeedom, qui reste prioritaire hors prévisualisation.
- Effets non interactifs (clics inchangés), réduction automatique sur mobile et respect des préférences d'accessibilité.
- Le même frontend React enrichi est compilé pour le site distant OVH en lecture seule.

## 0.90.56-beta - Animations événementielles
- Pilotage prioritaire des animations par commande INFO Jeedom.
- Test manuel de chaque animation, sans écrire dans Jeedom, et retour immédiat au pilotage automatique.
- Thèmes Noël, Nouvel An, printemps, été, automne, hiver, fêtes, Halloween et Pâques.
- Réglages d'intensité, vitesse, pages autorisées et activation sur smartphone.
- Transmission des paramètres au site distant PHP/React en lecture seule.

## 0.90.55-beta - Copier / Coller le style
- Copie du style d'une tuile vers plusieurs tuiles du même type, y compris sur différentes pages.
- Les commandes, les affectations, les titres et les positions ne sont pas copiés.

## 0.90.56-beta (File, historique)

- Animations globales : Noël, Nouvel An, saisons, fêtes, Halloween et Pâques.
- Pilotage prioritaire par commande INFO Jeedom ; OFF ou donnée inconnue n'affiche rien.
- Prévisualisation manuelle de chaque animation sans envoyer d'action à Jeedom et sans sauvegarder le mode test.
- Intensité, vitesse, pages et autorisation mobile configurables.
- Calque transparent ne bloquant aucun clic, réduction des animations respectée.
- Publication distante React : export des paramètres et de la commande INFO.

## 0.90.17-beta (File)
- Import Virtual : Action/Liste avec options Jeedom valeur|libelle et lien vers Info.
- Tuiles Ballon, Soufflants, vue interactive Modes Soufflants.
- Synchronisation INFO sans execution d'actions au chargement.
- Scénario AutoConso non modifié.

## 0.90.13-beta

- Smartphone : correction du surdimensionnement vertical introduit en 0.90.12.
- Les hauteurs mobiles sont désormais bidirectionnelles : une tuile peut être agrandie si son contenu dépasse, mais aussi réduite si la hauteur précédente était excessive.
- Les profils de départ sont plus compacts pour les cartes riches (Météo, Linky, PowerMeter, Résumé Énergie, Monitoring...) et pour les tuiles forcées en pleine largeur.
- Le calcul dynamique ne se base plus sur `content.scrollHeight`, qui incluait la hauteur GridStack déjà appliquée et empêchait le rétrécissement.
- Le layout mobile dérivé est réappliqué après mesure et GridStack est compacté afin de supprimer les trous verticaux résiduels.
- Aucun changement du layout Desktop.

## 0.90.12-beta

- Correction du layout smartphone : certaines tuiles riches pouvaient être tronquées ou donner l’impression de disparaître à 100 % alors que le rendu PC était correct.
- Hauteurs minimales mobiles recalibrées pour Météo, Linky, PowerMeter, Résumé Énergie, Monitoring et les principales tuiles riches.
- Ajout d’un ajustement dynamique de hauteur : Design Studio mesure le contenu réel d’une tuile mobile et agrandit sa cellule GridStack si nécessaire.
- Les deux demi-tuiles d’une même ligne reçoivent une hauteur cohérente afin d’éviter que la ligne suivante remonte sous la plus petite.
- La hauteur du canevas smartphone est recalculée jusqu’au dernier widget et les conteneurs principaux ne masquent plus les éléments qui dépassent.
- La correction est limitée à la vue smartphone : les coordonnées et dimensions Desktop `x/y/w/h` restent strictement inchangées.
- Conservation intégrale des corrections Linky/ZLinky 0.90.11-beta et autosauvegarde 0.90.9-beta.
- Aide intégrée et `CONTEXTE_PROJET.md` mis à jour.

## 0.90.11-beta

- Correction ZLinky TIC : l'auto-configuration conserve désormais la commande de puissance apparente choisie (PAPP/SINSTS/CCASN) et n'est plus remplacée quelques secondes plus tard par une ancienne migration Linky en W.
- Le polling LIVE se reconstruit automatiquement après une auto-configuration puisque la liste des IDs de commandes change ; un nouveau tick est lancé immédiatement avec les nouveaux bindings.
- Les anciennes tuiles Linky restent migrées vers une puissance active lorsque cela est nécessaire, mais les tuiles reconnues comme ZLinky sont protégées contre cette migration historique.
- Ajout d'un marqueur persistant `linkyAutoSource=zlinky` et de l'équipement source afin de stabiliser les mises à jour ultérieures.
- Lecture ZLinky renforcée côté PHP : pour les commandes de puissance instantanée, si le cache Jeedom et `execCmd()` divergent temporairement entre 0 et une valeur non nulle, la valeur non nulle est conservée ; un vrai flux nul reste 0 lorsque les deux lectures valent 0.
- Aide et CONTEXTE_PROJET.md mis à jour.

## 0.90.10-beta

- Nouveau **mode Conception Mobile** : sur smartphone, la conception utilise désormais la même disposition responsive dérivée que le Dashboard.
- Les coordonnées et dimensions Desktop `x/y/w/h` ne sont jamais réécrites depuis le téléphone.
- Réordonnancement tactile des tuiles sur smartphone via `mobileOrder`, sans impact sur le layout PC.
- Le redimensionnement GridStack est désactivé en Conception Mobile ; la largeur mobile reste réglable via `Disposition smartphone` (Auto / Demi / Pleine largeur).
- Barre Conception mobile simplifiée : logo, état de connexion et menu `⋮` regroupant Enregistrer, Import Jeedom, Thème, Aide, Dashboard, Kiosque, Aperçu, Backup/Restore.
- Navigation pages et panneaux Widgets/Propriétés adaptés au tactile.
- Watermark de version rendu plus discret sur smartphone.
- Conservation des corrections 0.90.9-beta d’autosauvegarde robuste.
- Aide intégrée et `CONTEXTE_PROJET.md` mis à jour.

## 0.90.9-beta

- Correction renforcée de l’autosauvegarde : `project.json` ne contient plus les valeurs LIVE éphémères des commandes Jeedom liées.
- Les rafraîchissements de température, puissance, batterie/LQI, historique, logs, flux, scénarios et équipements ne déclenchent plus de sauvegarde.
- Autosauvegarde **single-flight** : une seule requête `projectSave` peut être active par onglet ; une modification arrivée pendant l’écriture est regroupée puis rejouée une seule fois.
- Verrou serveur `flock()` autour du contrôle de révision et de l’écriture afin d’empêcher deux sauvegardes concurrentes de valider la même ancienne révision.
- Garde-fou serveur : si le JSON reçu est identique au projet déjà enregistré, aucune copie, aucun backup et aucune écriture disque ne sont effectués.
- Les fichiers temporaires de sauvegarde utilisent désormais un nom unique avant le renommage atomique.
- La protection 409 contre l’écrasement d’une modification réellement effectuée depuis un autre onglet/utilisateur est conservée.
- `CONTEXTE_PROJET.md` et l’aide intégrée sont mis à jour.

## 0.90.8-beta

- Amélioration du mode smartphone Dashboard/Kiosque sans modifier le layout Desktop.
- Barre supérieure mobile simplifiée : logo compact, échelle réduite et accès Jeedom par icône.
- Navigation des pages plus dense et scrollable horizontalement.
- Suppression des hauteurs minimales Desktop sur mobile afin d’éviter les grandes zones vides, notamment avec la tuile Monitoring.
- PowerMeter et Résumé Énergie compactés pour les petits écrans.
- Boutons d’action plus grands pour un usage tactile.
- Badge utilisateur masqué sur le Dashboard smartphone pour éviter de recouvrir les informations ; le Kiosque conserve son contrôle de verrouillage.
- Conservation intégrale des évolutions Linky/ZLinky 0.90.7-beta.
- Aide intégrée et `CONTEXTE_PROJET.md` mis à jour.

## 0.90.7-beta

- Correction du rafraîchissement temps réel de la tuile Linky/ZLinky : les commandes INFO sont désormais lues en priorité depuis le cache Jeedom, puis via `execCmd()` uniquement en repli. Cela évite qu'un `PAPP` valide repasse temporairement à 0 après l'auto-configuration.
- Toutes les commandes liées par l'assistant ZLinky continuent d'être rafraîchies automatiquement sans relancer l'assistant.
- Nouveau code couleur des flux : **orange** en soutirage `Réseau → Maison`, **rouge** lorsque le soutirage devient fort, **vert** en injection `Maison → Réseau`, gris/bleu en équilibre.
- Libellé neutre clarifié : `Équilibre` / `Flux nul` au lieu de `Réseau = Maison`.
- Aide et `CONTEXTE_PROJET.md` mis à jour.

## 0.90.6-beta

- Correction de l’assistant **LiXee ZLinky TIC** après validation sur un vrai ZLinky TIC LiXee v0.0.1.
- Détection de profil basée en priorité sur les **commandes réellement alimentées**, et non plus seulement sur la présence de leurs noms.
- En **TIC Historique**, priorité stricte à `PAPP`, `IINST`, `HCHC`, `HCHP`, `PTEC`, `ISOUSC` et `BASE` lorsqu’elles sont disponibles.
- En **TIC Standard**, priorité à `SINSTS`/`SINSTI`, `IRMS1`, `URMS1`, `EAST`, `EASF01`/`EASF02`, `LTARF`/`NTARF`.
- Les commandes Standard présentes mais nulles/inutilisables ne forcent plus un faux profil « Mixte / auto ».
- Lors d’une reconfiguration, les anciennes affectations Linky automatiques sont nettoyées pour éviter de conserver `CCASN`, `CCAIN`, `UMOY1`, `BBRHC*` ou d’autres valeurs erronées d’un profil précédent.
- En TIC Historique sans commande d’injection exploitable, l’injection reste non affectée et son affichage est automatiquement absent.
- Ajout du binding `Intensité souscrite` pour l’assistant. Si `ISOUSC` est disponible, la puissance de référence de la jauge est calculée automatiquement (ex. 60 A × 230 V ≈ 13,8 kVA).
- Les données absentes (tension, fréquence, index total, etc.) restent non affectées et ne créent plus de cases vides sur la tuile.
- Conservation des unités fournies par Jeedom : `VA/kVA` pour `PAPP`/`SINSTS`, `W/kW` lorsqu’une puissance active est réellement fournie.
- Mise à jour de l’aide intégrée et de `CONTEXTE_PROJET.md`.

## 0.90.3-beta

- Refonte visuelle complète de la tuile **Linky** avec flux d’énergie animé et bidirectionnel Réseau ↔ Maison.
- Trois présentations : **Mini**, **Standard** et **Expert**, avec sélection automatique selon la taille de la tuile.
- Jauge de puissance dynamique avec intensité visuelle proportionnelle à la consommation/injection.
- Couleurs dynamiques : vert Linky en soutirage normal, orange/rouge selon les seuils configurés, turquoise en injection.
- Nouvelles données Linky optionnelles : tension, intensité, fréquence, index total, HC, HP, tarif et dernière communication.
- Chaque élément de la tuile peut être affiché/masqué depuis l’onglet **Visibilité**.
- Sens import/injection inversable et zone neutre configurable pour éviter les changements de sens autour de 0 W.
- Mode Expert avec tendance historique intégrée et accès aux historiques Jeedom par clic sur les valeurs historisées.
- Auto-détection Linky enrichie pour tension, fréquence, index total et dernière communication.
- Aide en ligne et `CONTEXTE_PROJET.md` mis à jour.

## 0.90.2-beta

- Nettoyage final de la branche Market Beta avant publication.
- Compatibilité annoncée : Jeedom Core 4.5 minimum, Debian 11 et Debian 12. Cette mention concernait uniquement cette ancienne Beta ; la métadonnée actuelle autorise Debian 13.
- Frontend Market limité au mode plugin Jeedom : suppression du mode autonome, des champs URL/clé API et de l’ancienne configuration locale du navigateur.
- Toutes les commandes ACTION compatibles (`other`, `slider`, `select`, `color`, etc.) restent exécutées nativement par Jeedom via `cmd::byId()->execCmd()` après contrôle des droits.
- Protection contre l’écrasement silencieux lors d’éditions simultanées : contrôle de révision serveur avant toute sauvegarde du projet.
- Branche `beta` générée automatiquement comme runtime propre : frontend précompilé, sans `source/`, `node_modules`, script de build ni fichiers de préparation Market.
- Aucun npm/Node.js, aucune dépendance système, aucun démon et aucune modification du système sur le Jeedom cible.
- Licence clarifiée pour autoriser la distribution officielle du runtime compilé gratuit sans imposer la présence du code source dans la branche Market.

## 0.90.1-beta

- Première préparation Beta Market gratuite à partir de la 0.82.27.
- Frontend précompilé obligatoire ; aucun build exécuté sur le Jeedom cible.
- Droits Thermostat et flux système renforcés pour les utilisateurs non administrateurs.
- Batch limité à 1000 commandes, écriture `lastUsedAt` Kiosque limitée à une fois toutes les 10 minutes.
- Protection anti-bruteforce des PIN.
- Sauvegarde tournante du projet (5 versions) et limites de sécurité : 200 pages, 2500 tuiles, 20 Mo.
- Journal natif `designstudio`, traçage des ACTION et autosauvegarde optimisée héritée de 0.82.27.

## 0.82.27

- Correction de l’autosauvegarde du projet : les rafraîchissements des valeurs Jeedom ne provoquent plus d’écriture de `project.json`.
- Ajout d’une empreinte de configuration persistante qui ignore les valeurs runtime, historiques, logs, flux et états dynamiques.
- Debounce de 1,5 s après une vraie modification de conception, avec une seule sauvegarde après la dernière modification.
- Le changement de page seul ne déclenche plus de sauvegarde.
- Le bouton « Enregistrer Jeedom » reste une sauvegarde forcée immédiate.

## 0.82.26

- Journalisation des commandes ACTION étendue à tous les chemins d'exécution utilisés par Design Studio.
- Une action exécutée depuis une tuile Équipement est maintenant tracée dans le journal `designstudio` avec l'identifiant, le nom et le sous-type de la commande Jeedom.
- Les actions utilisant le chemin générique (`exec`) sont également journalisées, pas uniquement `execNative`.
- Niveau `debug` : demande d'exécution ; niveau `info` : confirmation d'exécution ; les erreurs restent journalisées en `error`/`warning`.
- Aucun changement du fonctionnement des commandes ou des tuiles.

## 0.82.25

- Correction de la journalisation native Jeedom.
- Création explicite du fichier `designstudio` à l'installation, à la mise à jour et à l'ouverture de la configuration du plugin.
- Le journal apparaît désormais dans **Logs et surveillance** même si les messages `Info` ou `Debug` sont filtrés.
- `writeLog()` s'assure également de l'existence du journal avant chaque écriture.
- Aucun changement du fonctionnement des tuiles, Dashboard ou Kiosque.

## 0.82.24
- Ajout d’une vraie journalisation native Jeedom via `log::add('designstudio', ...)`.
- Le fichier de log `designstudio` est désormais créé dès l’installation ou la mise à jour du plugin.
- Les erreurs AJAX et les erreurs de lecture/sauvegarde de `project.json` sont journalisées sans interrompre le fonctionnement du plugin.
- Création/révocation des jetons Kiosque journalisée au niveau Info.
- Exécution native des commandes ACTION journalisée uniquement au niveau Debug afin d’éviter de remplir inutilement le log en utilisation normale.
- Le niveau de log reste entièrement piloté par le réglage standard Jeedom dans la page de configuration du plugin.
- Aucun polling, rafraîchissement de commande ou historique normal n’est journalisé en Info afin d’éviter tout spam et toute écriture disque excessive.
- Aucune modification des tuiles, du format des projets ou du fonctionnement Dashboard/Kiosque.

## 0.82.23
- Correction des boutons **Exécuter** des tuiles **Équipement** : les commandes Jeedom `ACTION / other` sont désormais exécutées nativement par Jeedom (`cmd::execCmd()`), comme le bouton **Tester** de Jeedom. Cette correction couvre notamment les commandes du plugin **Script** sans que Design Studio n’exécute directement le fichier `.sh`.
- Les contrôles de droits Jeedom, permissions Kiosque et protections PIN restent appliqués avant toute exécution.
- Correction de l’ouverture de l’aide intégrée : le bouton **❓ Aide** ouvre maintenant `/plugins/designstudio/help.php`.
- Le fichier HTML d’aide reste stocké dans `docs/fr_FR/help.html`, mais il est servi par un point d’entrée PHP authentifié pour contourner les règles Apache/Jeedom pouvant interdire l’accès direct aux fichiers HTML de `docs`.
- Aucun changement du fonctionnement des tuiles, dashboards ou configurations existantes.

## 0.82.22
- Ajout d’un bouton **❓ Aide** dans la barre de la page Conception.
- Ouverture de l’aide locale dans une nouvelle fenêtre, sans quitter le projet en cours.
- Nouvelle aide HTML autonome avec recherche instantanée, navigation rapide et catalogue des tuiles par catégorie.
- Documentation des onglets Général / Données / Visibilité / Style, de l’affectation groupée des commandes Jeedom, des historiques, booléens, animations, alertes, échelles et du Résumé Énergie.
- Ajout d’un guide de dépannage rapide et de conseils d’utilisation.
- Aucun changement dans le format des projets, les données des tuiles ou le fonctionnement Dashboard/Kiosque.

## 0.82.21
- Échelle d’affichage séparée selon le contexte : Conception/Aperçu, Dashboard et Kiosque.
- Le réglage du Dashboard est maintenant directement disponible dans sa barre supérieure.
- Le Kiosque conserve un sélecteur flottant compact toujours accessible.
- Chaque mode mémorise sa propre échelle sur le navigateur/appareil, sans modifier les dimensions GridStack enregistrées.
- Migration douce : l’ancien réglage local `jds-canvas-scale` sert uniquement de valeur initiale si aucun réglage spécifique n’existe encore.

## 0.82.20
- Le réglage d’échelle est maintenant disponible en Dashboard et en Kiosque, via un contrôle compact toujours accessible.
- Les choix Auto, 100 %, 90 %, 80 %, 75 % et 67 % restent mémorisés localement par appareil.
- En mode mobile, Auto conserve 100 %, mais une échelle manuelle peut désormais être choisie.
- Aucun changement des positions ou dimensions GridStack sauvegardées.

## 0.82.19

- Ajout d’un réglage d’échelle du canevas : Auto, 100 %, 90 %, 80 %, 75 % et 67 %.
- Le mode Auto calcule l’échelle selon la largeur disponible avec une référence de 1920 px, bornée entre 67 % et 100 %.
- L’échelle ne modifie pas les coordonnées ni les dimensions GridStack enregistrées.
- La barre d’outils et les panneaux Propriétés/Widgets restent à taille normale ; seul le canevas est mis à l’échelle.
- Le choix est mémorisé localement par navigateur/PC et n’est pas enregistré dans le projet Jeedom.
- Le mode compact mobile conserve une échelle de 100 % pour ne pas perturber son layout dédié.

## 0.82.18

- Le popup d’affectation groupée mémorise maintenant automatiquement le dernier équipement Jeedom utilisé pour la tuile.
- Après une première affectation, la sélection suivante s’ouvre directement sur les autres commandes du même équipement.
- Ajout de l’indication « Équipement courant », de l’option « Rester sur cet équipement » et du bouton « Voir toutes les commandes » pour changer rapidement de racine.
- Lorsqu’une tuile possède déjà des commandes, Design Studio retrouve automatiquement leur équipement à l’ouverture du popup.
- Aucun changement du format des designs ni des affectations existantes.

## 0.82.17

- Nouvel écran **Affectation groupée des données** dans l’onglet Données : toutes les données d’une tuile sont visibles et affectables dans un seul tableau.
- Sélecteur rapide Objet → Équipement → Commande avec recherche, filtrage INFO/ACTION, valeur courante et auto-détection prudente des données non affectées.
- L’ancien mode d’affectation individuel reste disponible sous **Affectation individuelle / options avancées** afin de préserver toutes les fonctions existantes.
- Ajout d’un bouton historique dans l’en-tête de toute tuile contenant des commandes INFO : il ouvre toutes les données historiques de la tuile.
- Résumé Énergie : production solaire et consommation maison sont maintenant cliquables même lorsqu’elles sont calculées depuis MPPT / U×I / flux automatiques ; les historiques sources correspondants sont ouverts.
- Les liens historiques directs existants restent inchangés.

## 0.82.16

- Nouveau sélecteur **Aspect visuel booléen** pour les tuiles Ouverture, Présence, Fuite et Fumée.
- La tuile Ouverture propose désormais : Classique, Porte animée, Fenêtre animée, Contact magnétique, LED animée, Halo d’état et Minimaliste.
- Les styles LED, Halo et Minimaliste sont également disponibles pour les autres capteurs booléens du groupe.
- Les nouveaux visuels suivent l’inversion booléenne configurée dans Données et respectent les options de Visibilité existantes.
- Les animations existantes (halo, pulsation, icône, clignotement doux) restent disponibles et se combinent avec le nouveau visuel.
- Compatibilité ascendante : le style Classique reste utilisé par défaut pour les tuiles existantes.

## 0.82.15

- Ajout d’une inversion générique pour les commandes INFO booléennes associées à une tuile (valeur principale ou donnée secondaire).
- L’inversion agit uniquement dans Design Studio : texte, icône, couleur et animation sont cohérents sans modifier la commande Jeedom.
- La tuile Ouverture peut désormais corriger un contact NF/NO inversé et masquer indépendamment le libellé Ouvert/Fermé via l’onglet Visibilité.
- Extension aux Virtuals : chaque commande binaire peut être inversée individuellement.
- Animation d’état disponible pour toute tuile contenant une information booléenne, avec Halo, Pulsation, Icône animée ou Clignotement doux.
- Compatibilité conservée : aucune inversion ni animation nouvelle n’est imposée aux dashboards existants.

## 0.82.14

- PowerMeter : ajout dans **Visibilité** des réglages Icône éclair, Valeur de puissance, Unité et Libellé d’état.
- Le libellé **Consommation / Production / Équilibre** peut maintenant être masqué indépendamment, y compris sur les Mini tuiles.
- Compatibilité conservée : les anciens PowerMeter restent inchangés tant que l’option n’est pas décochée.

## 0.82.13

- Virtual Jeedom : ajout d’une option **Afficher le libellé / nom de la commande** pour chaque élément.
- Permet de conserver uniquement la valeur et son unité sur les petites tuiles (ex. Ballon/Solaire) sans afficher « Consommation ».
- Comportement rétrocompatible : le libellé reste affiché par défaut sur les tuiles existantes.
- Aucun changement du calcul, des animations ou des autres widgets.

## 0.82.12

- Résumé Énergie : ajout d’un bouton discret **Détails / Performance** ouvrant un popup dédié.
- Calcul temps réel de l’**autoconsommation** (PV non exporté / PV produit) et de l’**autonomie** (consommation non importée / consommation maison).
- Analyse sur **1 h, 3 h, 6 h, 12 h, 24 h, 7 j et 30 j** à partir de l’historique Jeedom.
- Compatible avec les sources Solplanet déjà gérées : PV direct, somme MPPT, ou calcul tension × courant.
- Affichage des énergies PV, maison, import, export, charge/décharge batterie et graphique de flux.
- Les indicateurs temps réel sur la tuile principale restent **désactivés par défaut** afin de préserver son rendu actuel ; ils peuvent être activés dans Style / Visibilité.

## 0.82.11

- La tuile **Synthèse températures** adapte désormais automatiquement son rendu aux dimensions réelles de la tuile (étroite, standard, large, mini/micro).
- Les formats étroits réduisent le cadran, la courbe et les lignes MAX/MOY/MIN pour éviter tout débordement.
- Les formats larges utilisent l’espace horizontal et placent MAX/MOY/MIN sur une seule ligne.
- Les choix de l’onglet **Visibilité** restent prioritaires : masquer un élément libère l’espace pour les autres.
- Aucun changement de comportement pour les autres widgets.

## 0.82.10

- Nouvelle tuile **Synthèse températures** pour afficher une température moyenne avec **MAX / MOY / MIN** issus de commandes Jeedom (Virtual compris).
- Nouveau rendu moderne : jauge circulaire lumineuse, tendance, statut Stable / hausse / baisse et blocs MAX / MOY / MIN.
- Onglet **Visibilité** complet : jauge centrale, tendance, indicateur de tendance, MAX, MOY, MIN et sous-titre sont tous masquables indépendamment.
- Si une donnée MAX ou MIN n'est pas associée, elle peut être masquée depuis Visibilité ; la valeur moyenne utilise la commande principale.
- Historique de la moyenne réutilisé pour la courbe et l'indicateur de tendance lorsque disponible.
- Compatibilité conservée avec les versions précédentes ; aucun widget existant n'est modifié automatiquement.

## 0.82.9

- Refonte visuelle du widget **Relais Zigbee** : interrupteur graphique moderne et proportions plus compactes.
- Animation fluide ON/OFF avec déplacement du curseur, halo vert doux et témoin lumineux lorsque le relais est actif.
- Le clic sur l’interrupteur utilise directement les commandes Activer/Désactiver déjà associées.
- Ajout des options de visibilité propres au relais Zigbee : interrupteur, état, sous-titre, puissance, LQI et dernière communication.
- Les nouveaux relais Zigbee utilisent désormais la largeur standard (3 colonnes) pour mieux s’aligner avec les autres tuiles compactes. Les relais déjà placés ne sont pas redimensionnés automatiquement afin de préserver les dashboards existants.
- Aucun changement sur le moteur d’alertes de page ni sur les autres widgets.

# Changelog

## 0.82.8

- Ajout d’un onglet **Alertes** dans la configuration de chaque page.
- Une alerte est définie par une commande Jeedom INFO, un opérateur, une valeur attendue et un niveau Information / Attention / Alarme.
- Les règles d’une page sont combinées en OU et restent totalement indépendantes du type de widget.
- Animation de l’onglet de page quand une règle est vraie : halo, pulsation ou clignotement.
- Association facultative d’une règle à une tuile pour afficher un halo directement sur l’élément concerné.
- Affichage de la valeur LIVE et du résultat vrai/faux dans l’éditeur de règle.
- Aucun changement de comportement pour les pages existantes : sans règle, l’affichage reste strictement inchangé.

## 0.82.7

- Correction de l’onglet **Visibilité** pour les tuiles Température et Humidité.
- Une tuile Température permet désormais de masquer indépendamment la valeur principale, l’humidité, la batterie, le sous-titre et la courbe.
- Les informations secondaires facultatives (humidité, batterie) ne sont plus affichées avec un tiret lorsqu’aucune commande Jeedom n’est associée : icône, valeur et unité disparaissent entièrement.
- Les réglages de visibilité existants restent compatibles avec les anciens designs.

## 0.82.6
- Ajout d’un onglet **Visibilité** dans les propriétés des tuiles.
- Tous les éléments restent visibles par défaut pour préserver les designs existants.
- Réglages détaillés disponibles pour Lumière, Thermostat, Volet, Prise/Relais classique, Ouverture, Présence, Fuite et Fumée.
- Réglages communs disponibles pour toutes les tuiles : titre, icône d’en-tête et badge LIVE/source.
- La tuile Lumière conserve intégralement la commande directe par clic sur l’ampoule et ses animations.

## 0.82.5
- Tuile Lumière : l’ampoule peut maintenant être utilisée directement comme commande ON/OFF.
- Nouveau réglage par tuile : **Ampoule cliquable + boutons ON/OFF**, **Ampoule cliquable uniquement** ou **Boutons ON/OFF uniquement**.
- Le clic sur l’ampoule utilise les commandes ON/OFF déjà associées et respecte la sécurité des actions Design Studio / les droits Jeedom.
- Les animations, halos, réglages de luminosité et de couleur existants sont conservés.

## 0.81.1
- Barre supérieure allégée : suppression du bloc redondant « Projet • page active ». Le nom de la page reste disponible dans la navigation des pages.

## 0.76.44
- Qualité de l’air : suppression des doublons des mesures secondaires.
- Nouveau réglage : Blocs détaillés / Badges compacts / Masquées.
- Blocs détaillés par défaut.

## 0.76.42
- Corrige le format Compact des tuiles Répéteur Zigbee : le preset passe à 4 colonnes x 3 lignes.
- Le rendu compact est désormais activé par le format de carte, pas uniquement par la hauteur manuelle.
- Les nouveaux répéteurs importés utilisent directement le format Compact.
- Le graphique historique se compresse correctement dans la faible hauteur.

## 0.76.41
- Répéteur Zigbee : hauteur par défaut réduite pour un format plus compact, proche du rendu RP01.
- Adaptation automatique du signal, de la valeur LQI, de l'animation radio et de l'historique quand la tuile est basse.
- Les métadonnées secondaires sont masquées dans ce format compact pour préserver la lisibilité.
- Le format haut reste disponible si la tuile est redimensionnée verticalement.

## 0.76.40
- Nouvelle tuile **Répéteur Zigbee** dédiée aux routeurs / range extenders.
- LQI affiché en grand avec 5 barres radio animées et halo coloré selon la qualité du lien.
- Seuils LQI configurables : Excellent / Bon / Moyen / Faible / Critique.
- Historique LQI en fond, avec les réglages globaux de présentation de courbe (type, hauteur, opacité).
- Dernière communication compatible avec les indicateurs globaux vert / orange / rouge et pulsation.
- Auto-détection des équipements Zigbee de type routeur/répéteur lorsqu'un LQI est disponible.

## 0.76.39
- Présentation des courbes harmonisée globalement pour les widgets historisés compatibles.
- Thermostat et TRV : courbe configurable (Standard, Grande, Arrière-plan transparent, Arrière-plan + remplissage), hauteur et opacité réglables.
- TRV : affichage de la courbe historique ajouté.

## 0.76.38
- Widget Logs : suppression par défaut du second titre interne pour éviter le doublon avec le titre de la tuile.
- Le panneau sombre du log occupe désormais toute la hauteur disponible de la tuile, avec défilement interne si nécessaire.
- Taille de police du log réglable de 8 à 16 px.
- Interligne réglable : Compact, Normal ou Aéré.
- Option pour réafficher l’en-tête interne du log si souhaité.

## 0.76.37
- AlarmPanel : nouveau mode **Surveillance communications / LogManager**.
- Lecture directe d’un log Jeedom au format AlarmCom avec extraction famille, équipement, dernière communication et durée d’inactivité.
- Synthèse graphique : nombre d’alertes, absents, familles concernées et durée la plus ancienne.
- Liste compacte colorée orange/rouge utilisant les seuils globaux de surveillance communication.
- Le mode Centrale d’alarme existant reste inchangé.

## 0.76.36
- Synchronisation intelligente des tuiles Virtual avec les commandes Jeedom : ajout des nouvelles commandes, retrait des commandes supprimées et conservation des personnalisations pour les commandes toujours présentes.
- Synchronisation automatique périodique des Virtual et bouton manuel **Synchroniser avec le Virtual Jeedom** dans l’onglet Données.
- Nouveau rendu **Cockpit graphique** pour les Virtual.
- Nouvelles présentations par commande : texte, voyant binaire, badge ACTIF/INACTIF, grande valeur et image/GIF conditionnelle.
- Taille/importance paramétrable par commande : petite, normale, large ou principale.
- Les personnalisations de nom, visibilité, média et ordre sont conservées lors de la synchronisation.

## 0.76.35
- Point de surveillance de communication Zigbee : orange pulsant lentement, rouge pulsant rapidement, vert fixe.
- Animation limitée au rond de couleur, sans animation du texte ou de l’horodate.
- Le paramètre global d’animation s’applique désormais aux deux niveaux d’alerte.

## 0.76.34
- Surveillance visuelle discrète de la dernière communication des équipements : point vert/orange/rouge placé sur la même ligne que l’horodate.
- Seuil global configurable : délai d’avertissement et délai d’absence.
- Pulsation rouge discrète optionnelle uniquement pour les équipements considérés absents.
- Les réglages de surveillance sont sauvegardés dans le projet et inclus dans les backups PC.

## 0.76.33
- Ajout d’un **Backup PC** de la configuration complète Design Studio au format JSON.
- Le nom du fichier contient automatiquement le **nom du Jeedom** et l’**horodatage local** : `DesignStudio-NOMJEEDOM-AAAA-MM-JJ_HH-mm-ss.json`.
- Le bouton d’import devient **Restaurer PC** et permet de recharger une sauvegarde JSON.
- Le bouton serveur est renommé **Enregistrer Jeedom** pour distinguer clairement sauvegarde serveur et backup local.

## 0.76.32
- Ajout d’un bouton **Délier cette commande** dans l’onglet Données pour la valeur principale et toutes les données secondaires.
- Confirmation avant suppression de l’association ; aucune commande Jeedom n’est supprimée.
- La liaison « Dernière communication » désactive automatiquement son affichage lorsqu’elle est déliée.

## 0.76.31
- Navigation des pages corrigée : la page active est automatiquement ramenée dans la zone visible.
- Zone des onglets élargie et flèches de défilement plus efficaces.
- Bandeau de page compacté : titre, nombre de widgets et rappel de navigation sur une seule ligne.

## 0.76.30
- Qualité de l’air : mêmes réglages de courbe que Température/Humidité (standard, grande, arrière-plan, arrière-plan rempli), hauteur et opacité réglables.
- Navigation des pages : les flèches font maintenant réellement défiler la barre d’onglets sans changer de page ; Alt+← / Alt+→ conserve la navigation page précédente/suivante.
- Barre d’onglets élargie : suppression de la limite à 70vw/920px en aperçu, défilement horizontal fluide à la molette et scrollbar fine disponible.

## 0.76.29
- Troncature visuelle automatique des titres de tuiles trop longs avec ellipsis, sans modifier le nom réel.
- Le nom complet reste disponible au survol via une infobulle native.
- Correction globale pour les formats Standard, Compact, Mini, Dense et Micro afin d’éviter les décalages de mise en page.

## 0.76.28
- Prise connectée : simplification du libellé d’état.
- Affichage `Active` / `Inactive` à la place de `Prise active` / `Prise arrêtée`.
- Aucun changement sur les commandes ON/OFF, les bindings, le halo ou les dimensions de la tuile.

## 0.76.27
- Ajout d’une option **Inverser la logique visuelle du relais** dans les propriétés des tuiles Relais.
- L’état ACTIF/INACTIF, le HALO et l’action affichée suivent alors la logique fonctionnelle inverse.
- Cas d’usage visé : fil pilote de radiateur où un relais électrique actif correspond à un chauffage arrêté.
- Les commandes Jeedom ON/OFF restent inchangées ; seule leur interprétation fonctionnelle dans la tuile est inversée.

## 0.76.26
- Relais : libellé simplifié en **ACTIF / INACTIF** (suppression de « CONTACT »).
- Halo renforcé automatiquement pour les relais en densité Compacte et Dense afin qu'il reste bien visible sur les petites tuiles.
- LED d'état active plus lumineuse et pulsation renforcée en petit format, sans modifier le rendu des grandes tuiles.

## 0.76.25
- Restauration de l'animation HALO sur les nouvelles tuiles **Prise connectée** et **Relais**.
- Le halo suit la couleur active de la tuile et reste visible en dispositions Aérée, Compacte et Dense.
- Ajout d'une pulsation sur l'icône de prise et sur la LED du relais quand l'équipement est actif.
- Aucun changement des liaisons Jeedom ni des dimensions des widgets existants.

## 0.76.23
- Prises connectées et relais : nouvelles densités Aérée / Compacte / Dense, avec Compacte par défaut pour réduire les espaces vides.
- Relais : bouton de commande et voyant réorganisés pour une carte plus courte et plus lisible.
- Historique Température / Humidité / Prise : nouveaux modes Standard, Grande courbe, Arrière-plan transparent et Arrière-plan + remplissage.
- Courbe de fond plus haute, transparente et non interactive afin de préserver la lisibilité des valeurs et des commandes.
- Aucun changement des bindings Jeedom existants ni des types de widgets.

## 0.76.22
- Correctif de compilation Vite de la tuile Cycle solaire introduite en 0.76.21.
- Correction de la fermeture JSX du bloc des phases astronomiques.
- Aucune modification fonctionnelle des widgets 0.76.21.

## 0.76.21
- Séparation visuelle des équipements ON/OFF avec deux nouveaux types : **Prise connectée** et **Relais**.
- Prise connectée : interrupteur glissant animé, puissance, énergie, tension, courant et historique optionnel.
- Relais : voyant d’état, commande Activer/Désactiver et action Impulsion optionnelle.
- Monitoring système : nouveau rendu cockpit avec indicateur de santé, jauges RAM/Disque/Swap/CPU et synthèse réseau/charge.
- Nouveau widget **Cycle solaire** avec arc lever/coucher, position du soleil, phase du jour, altitude, azimut et phases astronomiques en mode Expert.
- Auto-détection améliorée lors de l’import Dashboard : distinction prise/relais et reconnaissance des équipements lever/coucher du soleil.
- Tous les nouveaux rendus suivent les thèmes de page, y compris le thème Clair.

## 0.76.20
- Ajout d’un assistant **Changer le type de tuile** depuis les propriétés d’une tuile existante.
- Analyse automatique de compatibilité avant conversion : liaisons conservées, réaffectées et non reprises.
- Deux modes : conversion sur place ou création d’une copie convertie, plus sûre pour comparer le résultat.
- Conservation de la position, de la taille, du titre, du sous-titre et du style général.
- Possibilité d’annuler immédiatement la dernière conversion ou de supprimer la copie créée.
- Les commandes Jeedom incompatibles ne sont jamais supprimées : seules leurs associations à la tuile changent.

## 0.76.19
- Correctif de compilation JSX dans `App.tsx` (gestionnaire `onClick` du compteur énergie classique).
- Aucun changement fonctionnel par rapport aux nouveaux compteurs énergie de la 0.76.18.

## 0.76.18
- Nouveau rendu **Moderne graphique** pour les compteurs d’énergie, sélectionnable sans supprimer le style Classique.
- Mode **Automatique / Monophasé / Triphasé** par widget.
- En monophasé : jauge de puissance, tension, courant, énergie et facteur de puissance selon les données disponibles.
- En triphasé : trois jauges L1/L2/L3 avec puissance, tension et courant, plus calcul visuel du déséquilibre entre phases.
- Choix du graphisme **Anneaux / jauges** ou **Barres graphiques**.
- Puissance maximale de jauge paramétrable.
- Affichage activable indépendamment pour tension, courant, fréquence, énergie consommée, énergie produite et historique.
- Couleurs automatiques vert / orange / rouge selon les seuils existants ; bleu pour la production/injection.
- Compatibilité avec les thèmes de page, y compris le thème Clair.

## 0.76.17
- Amélioration de la lisibilité des noms de tuiles dans le thème Clair : couleur automatique fortement contrastée.
- Les micro-tuiles utilisent désormais la couleur de texte du thème au lieu d'un gris fixe.
- Nouveau réglage par tuile dans l'onglet Style : couleur du nom en mode Auto selon thème ou couleur personnalisée.

## 0.76.16
- Normalisation complète des composants internes pour tous les thèmes.
- Thème Clair : suppression des zones noires résiduelles dans les tuiles énergie, chauffage, Virtual, historique et composants secondaires.
- Les couleurs d'état et d'alerte restent inchangées.

## 0.76.15
- Ajout de 5 thèmes de Dashboard : Sombre actuel, Clair, Bleu nuit, Chaleureux et Minimal.
- Nouveau **thème global** utilisé par défaut sur toutes les pages.
- Chaque page peut désormais conserver le thème global ou choisir son propre thème.
- Les anciens projets restent en thème Sombre par défaut : aucun changement visuel imposé après mise à jour.
- Les thèmes s'appliquent à la structure du Studio, au canvas, aux tuiles, panneaux et contrôles tout en conservant les couleurs d'état des widgets.

## 0.76.14
- Nouvelle tuile **Qualité de l’air** plus visuelle et animée, pensée pour les capteurs CO₂ / environnement.
- Affichage enrichi : CO₂ principal, VOC, formaldéhyde / CH₂O, température, humidité, PM2.5 / PM10, pression, bruit, lux selon les commandes disponibles.
- Ajout des informations **Dernière communication**, **LQI** et **Batterie** dans les liaisons disponibles du widget.
- Codes couleurs par niveau et accès direct à l’historique sur chaque valeur historisée.

## 0.76.13
- Tuile Batterie rendue adaptable : détection automatique ou choix manuel entre pourcentage, état HIGH/MEDIUM/LOW et tension mV/V.
- En mode tension, seuils batterie vide/pleine paramétrables (2500/3000 mV par défaut) et conversion visuelle en niveau.
- Les états texte conservent leur libellé tout en pilotant la couleur et le remplissage de la batterie.

## 0.76.12
- Correction des micro-tuiles qui pouvaient s'ecraser en traits horizontaux.
- Suppression du forçage `height:auto!important` sur le conteneur GridStack Micro.
- La hauteur de la micro-tuile est maintenant entièrement pilotée par GridStack (`gs-h=1`).
- Alignement visuel identique aux autres tuiles avec un inset de 4 px.

## 0.76.10

- Recalage vertical des Micro tuiles pour aligner leur bord supérieur sur les autres cartes.
- Conservation de la grille verticale haute résolution introduite en 0.76.9.
- Aucune modification des autres formats ou widgets.

## 0.76.9
- Grille verticale divisée en demi-lignes : les Micro tuiles occupent désormais une vraie demi-hauteur GridStack.
- Migration automatique des positions/hauteurs des projets 0.76.8 et antérieurs, sans modifier leur apparence.
- Deux Micro tuiles peuvent être empilées directement l’une sous l’autre.
- Les autres formats conservent leurs dimensions visuelles.

## 0.76.8

- Alignement du bord supérieur des Micro tuiles sur celui des autres tuiles de la même ligne.
- Correction limitée au positionnement visuel Micro ; aucune modification des autres formats ou widgets.

## 0.76.5

- Nouveau format **Micro tuile**, plus dense visuellement que Mini.
- Batterie Micro : nom, jauge proportionnelle compacte et pourcentage sur une seule ligne.
- Couleurs dynamiques conservées : vert >=90 %, orange 30-89 %, rouge <30 %.
- Le format Micro masque les informations secondaires pour rester lisible.
- Aucun changement fonctionnel aux autres types de tuiles.

## 0.76.4

- Tuile Batterie : pictogramme de batterie proportionnel au pourcentage réel.
- Couleur du pictogramme et de la jauge : vert >= 90 %, orange de 30 à 89 %, rouge < 30 %.
- Conservation de l'animation de fond ajoutée en 0.76.3.
- Aucun changement sur les autres types de tuiles.

## 0.76.3
- Tuile Batterie uniquement : animation de fond selon le pourcentage restant.
- Vert pour une batterie >= 90 %, orange de 30 à 89 %, rouge sous 30 %.
- Animation légère compatible Mini/Compact/Standard et désactivée si le navigateur demande une réduction des animations.
- Aucun changement sur les autres types de tuiles, l'import, l'historique ou le thermostat.

## 0.76.2
- Auteur du plugin : DesignStudio.
- Détection Linky/TIC renforcée dans l’assistant de migration.
- Nouveau rendu animé pour compteurs de puissance mono, multi-canal et bidirectionnels.
- Détection des canaux power_a/power_b/power_ab, courant, tension, énergie et énergie produite.
- Seuils visuels configurables : vert, orange, rouge.
- Valeur négative signalée comme production/injection.

## 0.76.0
- Nouvelle tuile Linky/Téléinfo enrichie en W, HP/HC, intensité, index et animation.
- Détection/import ZLinky_TIC renforcés.

## 0.75.2
- Tuile Météo uniquement : détection renforcée de la vitesse/force du vent (km/h, m/s, generic_type/logicalId et noms de commandes).
- Détection renforcée de la direction du vent.
- Affichage du vent rendu plus visible : vitesse + unité et boussole directionnelle.
- Ajout des liaisons Vent/Direction dans les deux chemins d’import (assistant et import équipement).
- Aucun changement sur Thermostat, Zigbee, Historique, pages ou autres tuiles.

## 0.75.1
- Navigation pages : barre de défilement visuelle masquée tout en conservant le défilement horizontal et les flèches.
- Assistant de migration : « même profil » compare désormais la structure réelle des commandes (type, subtype, generic_type, logicalId, nom, unité et catégories) au lieu d'appliquer le choix à tout un plugin comme z2m.
- Aucun changement sur les tuiles Météo, Thermostat, Zigbee, Historique ou le moteur de Dashboard.

## 0.75.0
- Refonte ciblée de la tuile Météo + prévisions uniquement.
- Icône météo actuelle dynamique selon la condition.
- Animations légères soleil, pluie, nuages, neige et orage.
- Affichage plus dense : température, humidité, vent, pression et pluie uniquement quand disponibles.
- Ajout de la direction du vent avec boussole lorsque la commande existe.
- Prévisions J+1 à J+5 avec icône adaptée à chaque condition.
- Aucun changement volontaire des autres widgets, du thermostat, de l'historique, du responsive général ou de l'assistant de migration.

## 0.74.1
- Interface Analyse / Historique nettement compactée : en-tête, barre de période, cartes des séries, options, statistiques et pied réduits.
- Davantage de hauteur est réservée au graphe sans retirer aucune fonction.
- Les cartes de séries restent horizontales et défilables lorsque plusieurs commandes sont comparées.

## 0.74.0
- Historique accessible sur toutes les commandes INFO liées, même si le drapeau fullData est incohérent.
- Historique cliquable pour puissance/consigne thermostat et état/puissance/énergie des prises/relais.
- Zoom graphique par glisser-déposer à la souris, double-clic ou bouton pour réinitialiser.

## 0.73.2
- Prises / relais : état lisible ON/OFF ou Allumé/Éteint au lieu de 0/1, avec option Valeur brute.
- Animations d’état et affichage W/kWh conservés.

## 0.73.1
- Assistant de migration compacté : compteurs réduits, avertissement sur une ligne et résumé intégré au pied de fenêtre.
- Davantage de hauteur réservée à la liste des équipements à importer.

## 0.73.0

- Thermostat : affichage plus compact afin d'éviter les coupures verticales.
- Suppression de l'affichage du cadenas/verrouillage dans la tuile.
- Boutons de modes plus compacts et adaptés automatiquement à la largeur.
- Aucun changement du mapping ou du moteur natif Thermostat validé.
- Base V0.72 conservée.

## 0.72.0

- Animations d’état complémentaires pour lumière, présence, ouverture, prise, fuite, fumée, volet, portail et alarme.
- Ajout d’une fenêtre de confirmation avant suppression d’une tuile.
- Aucun changement de mapping Thermostat : conservation du fonctionnement validé en 0.71.7.

## 0.71.7
- Correction des actions CONFORT/ECO/OFF des vues ThermoHA.
- Résolution stricte des commandes du Thermostat natif.
- Support du lien `configuration.thermostat` de thermoAlternateView.

## 0.71.7
- Support des wrappers ThermoHA / thermoAlternateView.
- Resolution via `ref_thermostat` puis `map_*`.
- Lecture et actions toujours executees sur le Thermostat Jeedom officiel.

## 0.71.5
- Import Thermostat basé directement sur les eqLogic du plugin officiel Jeedom (`eqLogic::byType("thermostat")`).
- Ajout d’un endpoint natif `thermostatList` et conservation de l’ID eqLogic thermostat dans la tuile.
- Snapshot et actions Thermostat résolus par eqLogic natif, avec fallback par commande.
- Les wrappers/virtuels visuels ne sont plus utilisés pour la liste d’import Thermostat.

## 0.60.5
- Mobile : recomposition séquentielle de la grille 6 colonnes, sans reprendre les x/y Desktop.
- Widgets riches en pleine largeur ; widgets compacts par paires.
- Le layout mobile ne réécrit jamais la disposition Desktop.

## 0.60.5
- Corrige l'affichage du panel Jeedom sur smartphone : ouverture automatique du Dashboard direct pour éviter le recadrage du shell Desktop Jeedom.
- Aucun changement de géométrie sur Desktop PC.

# Changelog

## 0.60.3
- Weather Jeedom : reconnaissance renforcée des commandes `Condition +1`, `+2`, etc., J+ et H+.
- Ajout de page réparé : fenêtre Design Studio interne à la place de `window.prompt()`.
- Pages réordonnables par glisser-déposer des onglets.
- Boutons Déplacer avant/après dans la configuration de page.
- La page d’accueil reste configurable indépendamment de l’ordre.

## 0.60.0
- Import en un clic du Dashboard Jeedom standard.
- Analyse préalable : éléments reconnus, génériques, ignorés et limites de conversion.
- Création automatique d’une page par objet Jeedom.
- Affectation automatique des commandes principales et actions usuelles.
- Fallback en tuile générique pour les équipements non reconnus.

# v0.54.1
- Correction : le bouton 🏠 Jeedom reste visible dans le Dashboard.
- Les actions d’édition restent masquées en mode Dashboard.

# v0.54.1

- Ajout d’un bouton **Jeedom** dans le Dashboard pour revenir à `/index.php` et retrouver les menus Jeedom standards.
- Préparation d’un paquet `designstudio.zip` installable directement depuis **Plugins > Ajouter depuis une autre source > Fichier**.

# Changelog

## 0.51.0
- Ajout de `dashboard.php`, accès Dashboard autonome sans outils de conception.
- Dashboard verrouillé (aucun déplacement/redimensionnement) mais commandes et historiques restent actifs.
- Accès Dashboard protégé par la session administrateur Jeedom.
- Ajout d'un bouton Dashboard dans l'éditeur et dans la configuration du plugin.
- Le Dashboard ne sauvegarde jamais les changements de navigation dans le projet.
- Le Kiosque par token reste séparé et inchangé.

## 0.50.0
- Première version plugin Jeedom.
- Interface React embarquée, relais API PHP local et tokens Kiosque.
