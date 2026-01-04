# Modèle de données — version 0.1

## Vue d’ensemble
Le système repose sur une entité principale représentant un élève.
Chaque élève est caractérisé par des informations socio-éducatives et des scores académiques.
Des indicateurs dérivés (score moyen, profil académique) sont calculés à partir des résultats et utilisés pour l’analyse et la visualisation.

## Entité Élève
L’élève constitue l’unité centrale du système.
Il est décrit par :
- des informations socio-éducatives,
- des résultats académiques par matière,
- des métadonnées liées au contexte d’apprentissage.

## Indicateurs dérivés
À partir des scores académiques, le système calcule :
- un score moyen global,
- un profil académique (à risque, moyen, performant).

Ces indicateurs sont utilisés à des fins :
- d’analyse descriptive,
- de visualisation,
- et plus tard d’exposition via une API.


# 📌 API — Endpoints exposés - Version 0.2
1. Liste des étudiants

Endpoint
GET /api/students/

Description
Retourne la liste des étudiants avec leurs scores académiques, informations socio-éducatives et indicateurs calculés.

Champs retournés

name

math_score

english_score

science_score

test_preparation_course

lunch

parental_education

average_score (calculé)

profile (calculé)

Filtres disponibles

profile

test_preparation_course

lunch

parental_education

Exemples

/api/students/?profile=À risque

/api/students/?lunch=standard

2. Statistiques par profil

Endpoint
GET /api/students/stats/

Description
Retourne des agrégats par profil académique afin d’analyser la répartition et les performances globales des élèves.

Données retournées

profile

count (nombre d’élèves)

avg_score (moyenne des scores)

Utilisation

visualisation

tableaux de bord

indicateurs de suivi académique
