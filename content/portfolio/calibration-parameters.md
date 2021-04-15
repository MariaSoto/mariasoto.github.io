---
title: Calibrating the parameters of a Signal Detection Library
date: 2015-10-01T12:49:27.000+06:00
thumbnail: images/portfolio/satellite.jpg 
service: Parameter Calibration 
client: Aerospace and defense company
shortDescription: Implémentation d'une métaheuristiques pour la calibration des paramètres d'une librairie de détection des signaux satellite.
challenge: Détermination de la valeur de paramètres afin d’optimiser la détection des signaux satellite
solution: Modélisation mathématique de la problématique et implémentation des métaheuristiques 
---

------------------------------------
Ce travail a été réalisé pour une entreprise dans le domaine de l’aérospatiale et la défense experte dans le domaine de la détection et le traitement de signaux satellites. Sa librairie de détection dépende principalement de quatre paramètres : Detection Threshold, Bandwidth, PSD et Fe.  Les valeurs données à ces paramètres font varier la qualité de la détection des signaux.  

L’entreprise souhaite déterminer l’ensemble des valeurs à ces paramètres qui vont permettre d’optimiser la détection des signaux satellite.  Auparavant, plusieurs études ont été réalisées par rapport à ces paramètres sans arriver à un résultat concluant.  

Pour ce besoin, j’ai d’abord travaillé sur la compréhension des besoins du client ainsi qu'approfondir la connaissance des critères qui permettent de qualifier la bonne détection des signaux et comment les paramètres influent le comportement de détection.  Ensuite, j’ai modélisé cette problématique a travers d’un modèle d'[optimisation combinatoire](https://en.wikipedia.org/wiki/Combinatorial_optimization). La solution optimale de ce type de problème dans la pratique peu prendre trop de temps.  En effet, ce type de problème sont [Np-difficile](https://en.wikipedia.org/wiki/NP-hardness). Cependant, il existe des solutions approchées comme les [métaheuristiques](https://en.wikipedia.org/wiki/Metaheuristic) qui permettent d’obtenir de bons résultats. Les métaheuristiques peuvent être des méthodes de l’intelligence artificielle comme les algorithmes génétiques.  Ainsi, j’ai proposé une métaheuristique à [Voisinage Variable](https://en.wikipedia.org/wiki/Variable_neighborhood_search) qui a permis de trouver une bonne combinaison des valeurs aux paramètres de la librairie de détection des signaux sans un temps machine très court.  