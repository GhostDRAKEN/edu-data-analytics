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
