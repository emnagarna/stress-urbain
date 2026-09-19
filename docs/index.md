---
title: Vue d'ensemble du projet
---

<style>
    @media screen and (min-width: 76em) {
        .md-sidebar--primary {
            display: none !important;
        }
    }
</style>

# Vue d'ensemble du projet

!!! info "Informations générales"
    **Session**: Automne 2026  
    **Auteur(s)**: Emna Garna (20262504)  
    **Thème(s)**: Cartographie du stress urbain.  
    **Superviseur(s)**: Louis Edouard Lafonatant.  
    **Collaborateur(s):** <!-- Nom de(s) collaborateur(s) et partenaire(s)` -->  

## Description du projet

<!--:bulb: N'oubliez pas d'effacer ou mettre en commentaires les notes (`>`) en début de section-->


### Contexte

<!--
> Présentez le contexte général dans lequel s’inscrit votre projet (social, organisationnel, technologique, éducatif, environnemental, etc.).-->

Les environnements urbains sont concus a partir de plans, de normes
et de modeles qui capturent difficilement l'experience vecue des
usagers. Certaines situations generant du stress, danger percu,
confusion, surcharge, inconfort, ne sont pas visibles lors de la
conception ou difficilement mesurables a posteriori. Ce projet vise
a combler cet ecart en permettant aux citoyens de signaler des
moments de stress vecus dans l'espace urbain, afin de produire une
representation collective et exploitable pour les concepteurs,
urbanistes, ingenieurs, decideurs.



### Problématique

<!-- 
> Décrivez le problème central ou la question de recherche que votre projet cherche à adresser, pourquoi s'y intéresser et les faiblesses des solutions actuelles. 
> Le problème doit pouvoir être compris indépendamment de la solution envisagée.
-->

Comment capter, structurer et analyser des experiences subjectives
situees, le stress vecu, pour en faire des indicateurs utiles a la
conception et a l'amelioration des environnements urbains.

<!-- 
Les approches existantes de cartographie emotionnelle, comme le
projet Bio Mapping de Christian Nold ou le projet Urban Emotions
en Allemagne, reposent souvent sur des capteurs biometriques
ponctuels ou des methodes difficiles a reproduire d'une ville a
l'autre. Ce projet cherche a proposer une methode plus structuree
et reutilisable, basee sur des categories de problemes concretes
plutot que sur une mesure emotionnelle brute.-->

### Proposition et objectifs

<!-- 
> Présentez votre proposition de projet et les objectifs visés. Expliquez en quoi votre approche répond à la problématique identifiée. 
> Assurez-vous d'avoir, dans la mesure du possible, des objectifs mesurables, raisonnnables dans le temps et non redondants entre eux.
-->

Le projet propose une plateforme a deux volets, une application
ou les citoyens signalent des problemes urbains concrets et
actionnables (absence de passage pieton, trottoir manquant,
minuteur de traverse trop court, nid de poule, absence de
mobilier urbain, etc.), et un site web destine aux urbanistes
pour visualiser ces signalements sur une carte et prioriser les
interventions.

Contrairement a une approche basee sur le ressenti general (bruit,
affluence), les categories de problemes ont ete definies pour
correspondre a des enjeux qu'une municipalite peut directement
corriger.

Objectifs du projet :

* Collecter des signalements de stress geolocalises aupres des citoyens.
* Detecter automatiquement le type de zone autour du citoyen (ecole, hopital, station de transport, parc, commerce, type de route) pour filtrer les categories de problemes pertinentes.
* Structurer ces donnees selon une echelle de gravite coherente entre les categories.
* Produire des visualisations et analyses utiles pour les concepteurs (carte de chaleur, classement des zones prioritaires).

### Méthodologie

<!--
> Expliquez comment vous comptez aborder le projet : démarche générale, grandes étapes prévues, itérations, types de validations envisagées.
-->
* **Detection de zone** : la position du citoyen est croisee avec les donnees OpenStreetMap (via l'API Overpass pour un signalement ponctuel, ou un extrait local du Quebec pour l'analyse a grande echelle) afin de determiner le type de zone(ecole, hopital, station de transport, parc, commerce, type de route).
* **Echelle de gravite** : chaque probleme signale se voit attribuer un poids de 1 a 5, compose de trois facteurs, un poids de base propre au probleme (danger intrinseque), un
ajustement selon le type de zone (calcule a partir des donnees reelles de collisions de la Ville de Montreal), et un coefficient de vulnerabilite de la population (appuye sur le cadre Safe System Approach de la FHWA et des etudes sur la vulnerabilite des enfants pietons).
* **Validation des poids** : les poids ont ete etablis en combinant deux approches independantes, une analyse quantitative a partir du jeu de donnees Collisions routieres de la Ville de Montreal (218272 collisions depuis 2012), et une analyse qualitative basee sur des guides et normes municipales existants (Vision Zero Montreal, guide de Longueuil, Vivre en
Ville, etc.).

### Validation et Évaluation

<!--
> Indiquez comment vous évaluerez que votre solution répond aux objectifs du projet (ex. scénarios d’usage, tests, retours utilisateurs, indicateurs qualitatifs ou quantitatifs).
-->

## Échéancier

!!! info
    Le suivi complet est disponible dans la page [Suivi de projet](suivi.md).

| Activités                      | Début   |   Fin   | Livrable                            | Statut      |
|--------------------------------|---------|---------|-------------------------------------|-------------|
| Ouverture de projet            | 4 mai   | 15 mai  | Proposition de projet               | ✅ Terminé  |
| Études préliminaires           | 4 mai   | 22 mai  | Document d'analyse                  | 🔄 En cours |
| Présentation + Rapport         | 7 aout  | 14 aout | Présentation + Rapport              | ⏳ À venir  |
