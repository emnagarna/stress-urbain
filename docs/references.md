---
title: Travail réalisé
---

<style>
    @media screen and (min-width: 76em) {
        .md-sidebar--primary {
            display: none !important;
        }
    }
</style>

# Références

<!---
> :bulb: Cette page rassemble les **principales sources et ressources utilisées dans le cadre du projet**.  
> 
> Elle permet également de préciser **comment ces ressources ont contribué au travail réalisé**.


## Références utilisées


> Selon la nature du projet, vous pouvez notamment référencer :
>
> * articles scientifiques ou techniques ;
> * livres et ouvrages de référence ;
> * documentation officielle ;
> * normes et spécifications ;
> * bibliothèques, frameworks et outils importants ;
> * jeux de données et API ;
> * projets ou solutions existantes étudiées ;
> * rapports, études ou publications institutionnelles ;
> * ressources Web pertinentes.
>
> Il n'est pas nécessaire de répertorier chaque page consultée. Privilégiez les références qui ont **réellement soutenu, orienté ou influencé votre travail**.

### Présentation des références

> Pour chaque référence importante, fournissez :
>
> * les informations permettant d'identifier et de retrouver la source ;
> * une courte justification de **1 à 2 phrases** expliquant son rôle dans le projet.
>
> La justification peut notamment indiquer si la référence a servi à :
>
> * comprendre le problème ;
> * comparer des approches ;
> * orienter un choix technique ;
> * concevoir ou implémenter une solution ;
> * définir une méthode d'évaluation ;
> * interpréter des résultats.

### Exemple

> **Mozilla Developer Network.** *Web APIs*.
> https://developer.mozilla.org/
>
> Cette documentation a été utilisée comme référence principale pour comprendre le fonctionnement des API Web exploitées dans l'application et valider certains choix d'implémentation.

> **Nom de l'auteur.** *Titre de l'article*. Nom de la publication, année.
>
> Cet article a permis de comparer différentes approches au problème étudié et a contribué au choix de la méthode retenue dans le projet.

## Utilisation de l'intelligence artificielle

> Documentez les principaux usages de **systèmes d'intelligence artificielle générative ou d'assistants basés sur des modèles de langage** dans le cadre du projet.
>
> L'objectif n'est pas de retranscrire l'ensemble des conversations ou requêtes effectuées, mais de rendre explicite **le rôle joué par ces outils dans votre démarche**.

### Pour chaque outil utilisé

> Indiquez, lorsque pertinent :
>
> * le nom de l'outil ou du modèle utilisé ;
> * les principales tâches pour lesquelles il a été employé ;
> * la manière dont les résultats produits ont été vérifiés, adaptés ou intégrés au projet ;
> * les limites ou problèmes rencontrés lors de son utilisation.

### Exemple

> **ChatGPT — OpenAI**
>
> Utilisé principalement pour explorer différentes stratégies de traitement des données et générer des pistes d'implémentation. Les propositions obtenues ont été vérifiées à partir de la documentation officielle et adaptées à l'architecture du projet avant leur intégration.

> **GitHub Copilot**
>
> Utilisé ponctuellement pour assister la rédaction de code répétitif et de tests. Le code généré a été révisé et testé par l'équipe avant d'être conservé dans le projet.

-->

## Références utilisées

<!-- > Ajoutez vos références ci-dessous en utilisant une présentation cohérente. -->


### Semaine 1, recherche de projets similaires

**Christian Nold.** *Bio Mapping / Emotional Cartography*.
biomapping.net (2004–).

Projet de reference pour la cartographie des emotions en ville,
combinant capteurs de reponse galvanique de la peau et GPS. A
servi a situer ce projet par rapport aux approches existantes et
a identifier leurs limites (methode difficile a reproduire,
dependante de capteurs biometriques).

**Kittelson & Associates et al.** *Urban Emotions*. Allemagne.

Projet combinant capteurs, telephones intelligents et donnees
participatives pour identifier les points de stress pour les
pietons et cyclistes. A confirme la pertinence d'une approche
geolocalisee et participative.


### Semaine 2, ponderation par les normes et par les données réelles

### a- Sources de ponderation par les normes (approche qualitative)

**Ville de Montréal.** *Plan d'action Vision Zéro*.
https://montreal.ca/articles/vision-zero-se-deplacer-en-securite-pied-en-velo-et-en-auto-14584

Utilisé pour identifier les amenagements prioritaires en matiere
de securite pietonne (ilots refuges, saillies de trottoir, zones
scolaires) et justifier le poids attribue a certaines categories
de problemes.

**Ville de Longueuil.** *Guide d'implantation des passages pour
piétons* (2023).
https://cms.longueuil.quebec/sites/default/files/medias/documents/2023-08/Guide%20implantation%20passages%20pi%C3%A9tons.pdf

Consulté pour comprendre les normes municipales entourant
l'implantation des passages pietons et appuyer le poids eleve
attribue a cette categorie.

**Vivre en Ville.** *Traverses piétonnes surélevées et trottoirs
traversants, priorité piéton* (mars 2017).
https://carrefour.vivreenville.org/storage/app/media/publications/Articles-de-fond-Encyclopedique/intersection-conviviale/traverses-pietonnes-surelevees-et-trottoirs-traversants-priorite-pieton.pdf

Utilisé pour appuyer la ponderation des categories liees aux
trottoirs.

**Office des personnes handicapées du Québec.** *Guide
d'accompagnement, mobilier urbain* (2019).
https://cdn-contenu.quebec.ca/cdn-contenu/adm/org/ophq/Administration/Guides/Accessibilite-mobilier-urbain.pdf

Consulté pour ponderer les categories liees au mobilier urbain
(bancs, poubelles), peu couvertes par les guides de securite
routiere.

**CERIU.** *Guide de bonnes pratiques de réparation de nids de
poule* (2010).
https://ceriu.qc.ca/system/files/2018-06/GUIDE-de-bonnes-pratiques-de-reparation-de-nids-de-poule.pdf

Utilisé pour confirmer la reconnaissance municipale du nid de
poule comme probleme d'entretien recurrent.

**Direction de santé publique de Montréal.** *Rapport synthèse
sur les collisions impliquant des piétons*.
https://collections.banq.qc.ca/document/s/t/1kieDjKbHUajctklpe9XMQ

Source du constat qu'a volume de circulation egal, les
intersections situees sur des arteres comptent 2.4 fois plus de
pietons blesses que les intersections locales. A justifie
l'ajustement de poids applique aux boulevards.

### b- Sources de ponderation par les données réelles (quantitatif)

**Ville de Montréal / Données Québec.** *Collisions routières*.
https://donneesquebec.ca/recherche/dataset/vmtl-collisions-routieres

Jeu de donnees geolocalisees de 218272 collisions survenues
depuis 2012 (CSV/GeoJSON, licence CC BY 4.0). Croise avec les
types de zones OSM pour calculer un taux de victimes pietonnes
par type de zone, servant de base quantitative a l'ajustement de
poids.

### Semaine 3 

