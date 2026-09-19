---
title: Suivi du projet
---

<style>
    @media screen and (min-width: 76em) {
        .md-sidebar--primary {
            display: none !important;
        }
    }
</style>

# Suivi de projet

<!--
> :bulb: Cette page documente l’évolution du projet dans le temps.
> Elle sert à rendre visibles les décisions, ajustements et apprentissages.
> Les entrées peuvent être hebdomadaires ou bi-hebdomadaires.  
> N'oubliez pas d’effacer ou de mettre en commentaires les notes (`>`) avant la remise finale.
-->

---

## Semaine 1 (4–10 Septembre)

### Objectifs de la période
<!--- Clarifier la problématique
- Explorer les solutions existantes
- Produire un premier prototype conceptuel
-->

- Explorer des idées de représentation visuelle du stress sur une carte, pour un premier meeting avec le superviseur
- Rechercher des projets similaires existants
- Définir une première version des catégories de stress et du flux de signalement
- Esquisser l'architecture technique et l'interface

### Travail réalisé

!!! abstract "Avancement"
    - [x] Idées de représentation du stress sur la carte
        - agrégation par zone ou quartier,
          segments de rue plutôt que points isolés
    - [x] Idées de visualisation pour le dashboard urbaniste
        - Filtres, slider temporel, classement des zones les
          plus problématiques, comparaison avant / après
    - [x] Recherche de projets similaires
        - Bio Mapping (Christian Nold), Urban Emotions
          (Allemagne), Your Emotional City (Berlin),
          Emotional Maps (Příbram), Mappiness (UK)
    - [x] Modèle de données initial
        - Tables signalements, types_stress, zones, avec
          PostgreSQL et l'extension PostGIS
    - [x] Choix de la solution cartographique
        - Leaflet avec les tuiles OpenStreetMap, gratuit et
          sans clé API, plutôt que Google Maps
    - [x] Sketchs d'interface
        - Formulaire de signalement côté citoyen, dashboard avec carte de chaleur côté urbaniste
<!--- 
    - [x] Analyse de solutions existantes
        - Comparaison de trois outils similaires
    - [x] Prototype basse fidélité (Figma)
    - [ ] Validation utilisateur
        - Reportée à la semaine suivante
-->

### Décisions et ajustements

!!! info "Décisions"
    - Catégories de stress initiales proposées : danger perçu, confusion, surcharge sensorielle, inconfort, accessibilité (version qui sera revue en semaine 2)
    - Leaflet + OpenStreetMap ( a voir mapbox aussi ) retenu plutôt que Google Maps 
<!--- 
> À compléter uniquement si des choix structurants ont été faits
> ou si l’orientation du projet a évolué.

!!! info "Décisions"
    - Abandon de l’approche X jugée trop complexe
    - Reformulation de la problématique suite aux premières analyses

    - Aucune difficulté technique majeure cette semaine, phase de recherche et de conception
--> 

### Difficultés rencontrées

<!--- 
> À compléter uniquement si des obstacles ont eu un impact réel
> sur l’avancement du projet.

!!! warning "Difficultés"
    - Problème de configuration du plugin Mermaid
        - Confusion entre `mkdocs-mermaid2-plugin` (pip)
          et `mermaid2` (nom du plugin)
        - Résolu après nettoyage et configuration correcte dans `mkdocs.yml`
-->

## Semaine 2 (11–17 Septembre)

### Objectifs de la période

- Redéfinir les catégories de problèmes signalables et leur échelle de gravité
- Concevoir le mécanisme de détection automatique de zone (école, hôpital, type de route, etc.)
- Développer un script pour calculer des poids de gravité justifiés à partir de données réelles, plutôt qu'estimés à l'intuition


### Travail réalisé

!!! abstract "Avancement"
    - [x] Redéfinition des catégories de problèmes
        - Passage de critères sensoriels (bruit, affluence) à des problèmes concrets et actionnables par une municipalité (trottoir absent, passage piéton absent,
        minuteur trop court, nid de poule, mobilier urbain manquant, etc.)
    - [x] Recherche de sources officielles pour   justifier lespoids de gravité
        - Guides municipaux et provinciaux (Vision Zéro Montréal, Longueuil, Vivre en Ville, OPHQ, CERIU), cadre Safe System Approach de la FHWA
    - [x] Développement d'un script Python pour calculer les
          poids à partir de données réelles
        - Script conçu et implémenté personnellement pour lire
          le jeu de données Collisions routières de la Ville de
          Montréal (218272 collisions) et le croiser avec les
          zones extraites d'OpenStreetMap
        - Script débogué et exécuté localement 
    - [x] Découverte de projets plus proches du projet
        - 311 Montréal, application officielle de la Ville
          permettant aux citoyens de signaler des problèmes
          urbains, sans scoring de gravité ni détection de
          zone
        - FixMyStreet (Royaume-Uni) et SeeClickFix
          (États-Unis), plateformes de signalement citoyen
          avec des catégories similaires, qui ont
          validé le choix de catégories concrètes et
          actionnables par une municipalité

### Décisions et ajustements

!!! info "Décisions"
    - Passage d'une interrogation Overpass en temps réel (pour
      l'analyse à grande échelle) à un extrait OSM local du
      Québec, l'API publique étant trop instable pour une
      requête couvrant l'île de Montréal au complet
    - Séparation du poids en trois facteurs distincts (base,
      zone, vulnérabilité) plutôt qu'un poids unique par zone,
      pour éviter qu'un problème mineur (ex. absence de banc)
      hérite du même poids qu'un problème de sécurité directe
      dans la même zone
    - Correction manuelle du poids de la zone autoroute, le
      taux calculé était artificiellement bas car la Ville de
      Montréal exclut les collisions autoroutières de son jeu
      de données ; le poids retenu s'appuie plutôt sur les
      guides de sécurité routière


### Difficultés rencontrées

!!! warning "Difficultés"
    - Le script réalisé pour lire le fichier de collisions de
      la Ville de Montréal et détecter les zones environnantes
      interrogeait initialement l'API Overpass en temps réel
      pour couvrir l'île de Montréal au complet
        - Cette partie du script provoquait des timeouts
          répétés du serveur public Overpass, même après avoir
          ajouté des tentatives automatiques dans le code
        - Résolu en modifiant le script pour télécharger un
          extrait OSM local du Québec (Geofabrik) et
          l'interroger avec geopandas plutôt qu'avec un
          service en ligne
    - Dans le fichier OSM(OpenStreetMap), les tags comme `amenity`, `leisure`
      et `shop` étaient absents en tant que colonnes directes
      et devaient être extraits du champ `other_tags`
        - Résolu en ajoutant une extraction par expression
          régulière dans le script avant le filtrage

## Semaine 3 (18–24 septembre)

### Objectifs de la période
- Réviser le score de gravité calculé en semaine 2, suite à un
  commentaire du superviseur sur la nécessité de différencier
  la gravité selon le contexte, pas seulement selon le type de
  problème ( Ajouter un facteur de pondération supplémentaire à la formule
  de calcul des poids)
- Trouver des échelles de pondération déjà établies et documentées dans la littérature en sécurité routière
- Figma


### Travail réalisé

!!! abstract "Avancement"
    - [x] Révision du score calculé en semaine 2
        - Le superviseur a souligné qu'un accident près d'une
          école devrait peser plus lourd qu'un accident sur une
          autoroute, celle-ci étant supposée être une zone
          protégée, ce que le score basé uniquement sur les
          taux de collision par zone ne reflétait pas
    - [] Recherche d'échelles de pondération déjà utilisées et
          reconnues
    - [] Créer maquette sur Figma
    - []  
    - []  



### Décisions et ajustements

!!! info "Décisions"
    - 

### Difficultés rencontrées

!!! warning "Difficultés"


