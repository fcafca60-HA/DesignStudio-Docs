---
layout: default
permalink: /fr_FR/quickstart.html
title: QuickStart
---

# QuickStart - Installation et démarrage

1. Dans le Market Jeedom, installez **Jeedom Design Studio** en canal **Beta** et activez-le.
2. Configurez, si nécessaire, les utilisateurs, droits d'accès et le mode Kiosque.
3. Ouvrez **Plugins > Organisation > Jeedom Design Studio**.
4. Cliquez sur **+ Jeedom > Importer TOUT le Dashboard Jeedom**.
5. Contrôlez les types détectés et les éléments « à vérifier », puis choisissez **Créer le Dashboard validé**.
6. Cliquez sur **Enregistrer Jeedom**, puis sur **Dashboard**.

**Attention** : l'import complet remplace le projet actuel. Faites d'abord une sauvegarde (**Backup PC**) si vous avez déjà un Dashboard personnalisé.

La distribution Market est précompilée. Vous n'avez pas à lancer `npm`, Node.js ni `build_frontend.sh`.

[Guide complet](./) · [QuickStart PDF](./QuickStart_DesignStudio.pdf) · [Tutoriels](./tutoriels.html)


## Animations festives 0.90.57

Dans **Connexion Jeedom > Animations événementielles**, sélectionnez une commande INFO texte Jeedom puis définissez le niveau **Simplifié**, **Normal** ou **Dense**, et la vitesse. Les thèmes (NOEL, NOUVEL_AN, PRINTEMPS, ETE, AUTOMNE, HIVER, FETE, HALLOWEEN, PAQUES) peuvent tous être prévisualisés avec **Tester l'animation**, même sans commande Jeedom configurée. **Arrêter le test** revient au pilotage Jeedom sans écrire dans ses commandes. Les animations sont désactivées par défaut. Pour OVH, mettez à jour le bundle React distant de la même version et republiez les informations.


### Importer une caméra officielle

L’assistant **Importer TOUT le Dashboard Jeedom** reconnaît les équipements du plugin Camera officiel, même sans commande INFO. Vérifiez le type **Caméra** puis choisissez un rafraîchissement **Manuel, 2, 5, 10, 30 ou 60 s** dans **Propriétés > Style**. La caméra reste réservée à Jeedom ; aucun flux n’est envoyé au site distant.
