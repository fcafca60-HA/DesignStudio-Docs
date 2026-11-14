# Jeedom Design Studio — Changelog Light

**Historique synthétique des évolutions depuis la série 0.70 jusqu’à V0.90.88-beta RC1**  
*Mise à jour : 14 novembre 2026*

Ce document présente les nouveautés et corrections marquantes pour les utilisateurs. Il complète le [changelog détaillé](changelog.md), qui reste la référence pour les changements techniques. L’historique source disponible commence à **0.71.5** : aucune entrée 0.70.x non documentée n’a été reconstituée.

## V0.90.88-beta RC1 — Animation des lignes de flux
- Nouveau réglage **« Inverser le sens de l’animation »** dans **Propriétés → Style**, à côté des options de halo.
- Sens indépendant pour chaque segment, même si plusieurs segments utilisent la même commande INFO.
- États 0/1/2, couleurs, vitesse et commandes Jeedom inchangés ; option désactivée pour les anciens projets.
- **Statut : RC1 File de test** ; publication GitHub/Market et validation finale à confirmer.

## V0.90.87-beta — Consolidation de la RC6
- Regroupement des corrections de widgets Jeedom natifs validées visuellement dans **V0.90.85 RC6**.
- Alignement des versions et mise à jour de la documentation et des sources pour les distributions File et GitHub.
- Pas de changement voulu du fonctionnement des tuiles, projets et commandes Jeedom par rapport à RC6.

## V0.90.80 à V0.90.85 RC6 — Symboles, flux et widgets natifs
- **Bibliothèque graphique SVG** : modes Classique, Symbole et Hybride ; 45 symboles préinstallés, import de SVG personnels et animations selon l’état.
- **Visibilité conditionnelle** : affichage des tuiles selon des commandes INFO, variables Jeedom et conditions ET/OU.
- **Widgets Jeedom natifs** : intégration des widgets existants, ajustement des tailles et amélioration du rendu Dashboard (météo, héliotrope, graphiques et boussoles) jusqu’à la RC6.
- **Capteur de pression** : nouvelle tuile avec seuils, alertes, mesures secondaires et historiques.
- **Lignes de flux** : tracés droits/coudés, raccordement à la grille, états 0/1/2, couleurs et animation configurables.

## V0.90.58 à V0.90.71 — Nouvelles tuiles et ergonomie
- **Caméras Jeedom** : tuile dédiée et prise en charge améliorée des flux/captures, notamment MJPEG.
- **WLED** : tuile de commande ON/OFF, couleur, luminosité, effets, presets et retour d’état INFO.
- **Éditeur** : grille Desktop 12/24/48 colonnes, texte enrichi, copie de style/visibilité/tuiles et réglages de présentation rationalisés.
- **Interface et déploiement** : améliorations de l’installation File/Market, contrôle des versions et compatibilité des projets.
- **Smart Layout** : meilleure adaptation des petites tuiles, capteurs et Virtuals.

## V0.90.1 à V0.90.17 — Énergie, mobilité et fiabilité
- **Linky / ZLinky TIC** : détection plus précise, flux réseau/maison animés, modes Mini/Standard/Expert et données supplémentaires.
- **Smartphone** : conception tactile, adaptation automatique des hauteurs, sans modifier les positions Desktop.
- **Sauvegarde** : autosauvegarde plus robuste, protection contre les conflits et exclusion des simples changements de valeurs LIVE.
- **Autoconsommation** : nouvelles vues et tuiles de suivi énergétique, ballon et chauffages soufflants.

## V0.81 à V0.82 — Réglages par tuile et suivi énergétique
- **Visibilité** : choix précis des valeurs, icônes, boutons et informations affichées dans les tuiles.
- **Alertes** : règles par page fondées sur des commandes INFO, avec animations visuelles des onglets et tuiles.
- **Interactions** : commandes d’éclairage et relais directement depuis les éléments graphiques ; inversion d’informations booléennes si nécessaire.
- **Énergie et températures** : synthèse de températures, statistiques d’autoconsommation et d’autonomie, nouveaux indicateurs pour PowerMeter et Virtuals.

## V0.76.xx — Widgets et personnalisation
- **Linky et énergie** : compteurs animés, seuils de consommation/injection et meilleure reconnaissance des données TIC.
- **Zigbee** : répéteurs avec LQI, courbes et alertes ; surveillance de la dernière communication.
- **Virtual** : synchronisation des commandes et nouveau rendu Cockpit personnalisable.
- **Tableau de bord** : backup/restauration PC, alarmes de communication, journaux plus lisibles, historiques configurables et présentations compactes.

## V0.71 à V0.75 — Premières évolutions de la série 0.70
- **Thermostat** : import fondé sur le plugin Jeedom officiel, actions Confort/Éco/Off et affichage compact.
- **Météo** : animations de conditions météo, prévisions J+1 à J+5, informations de vent et boussole.
- **Historique** : accès étendu aux commandes INFO et zoom dans les graphiques.
- **Tuiles** : états ON/OFF plus lisibles, animations d’état et confirmation avant suppression.

---

**Compatibilité :** les évolutions sont conçues pour préserver les projets existants et les associations Jeedom. La mention d’une fonctionnalité ne constitue pas une garantie de fonctionnement sur tous les plugins tiers. Pour connaître les correctifs exacts et leurs limitations, consulter le changelog détaillé.
