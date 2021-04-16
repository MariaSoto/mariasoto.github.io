---
title: Data assimilation
date: 2020-05-12T18:07:16.000+06:00
featureImage: images/portfolio/meteo.png
thumbnail: images/portfolio/meteo.png
service: Kalman Filter and Time Series
client: Applied Mathematics Laboratory
shortDescription: Data assimilation for the growth curve of calves. Application of the Kalman Filter and Time Series. This study was carried out for an applied mathematics laboratory.
challenge: Application de l’assimilation de données à un système d’équations différentielles Partielles qui simule la croissance d'un animal en fonction de son poids initial et de sa consommation alimentaire.
solution: Proposition d'un modèle en Séries Chronologiques et d'un filtre de Kalman pour l'assimilation de données 

---

# Assimilation de données 
------------------------------------
L'assimilation de données est le procédé qui consiste à corriger, à l'aide d'observations, l'état d’un système souvent modélisé par un modèle mathématique. Elle a été largement exploitée dans la prévision météorologique et dans le domaine de la géoscience.  
L'assimilation de données c'est un ensemble des méthodes qui permettent de combiner de manière optimale les informations disponibles sur un système [Blayo](https://www.eccorev.fr/IMG/pdf/Assimilationdonnees_EBlayo.pdf) :  
- Équations mathématiques, décrivant le modèle physique 
- Observation, mesures physiques de la réalité à travers des capteurs 
- Statistiques d'erreurs :  erreurs d'observation et du modèle  

L'assimilation de données est considérée comme une méthode ``prédicteur/correction''. Une prévision, calculée au pas de temps précédent et valable à l'instant considéré, est utilisée comme prédicteur. Les observations disponibles permettent de corriger cette ébauche pour estimer au mieux l'état réel du système. 

Les méthodes les plus emblématiques sont le 3 D-Var (approche variationnelle agissant à un temps fixé) le 4D-Var (approche variationnelle issue du contrôle optimal appliquée sur une fenêtre temporelle) et le Filtre de Kalman et ses variantes ( EKF, EnKF, LETKF). 


# Cas d’étude 
------------------------------------

Dans notre cas concrètement, un laboratoire en mathématique appliqué souhaitait explorer l’application de l’assimilation de données à un système d’équations différentielles Partielles (EDP).  Le système d’EDP simule la croissance d'un animal en fonction de son poids initial et de sa consommation alimentaire. Pour ce faire nous avons le modèle en EDP et des observations du poids qui comportent une erreur de mesure. 

Nous avons procédé comme dans la plupart des travaux d’assimilation de donnée avec un système complexe [Whale et all.](https://www.sciencedirect.com/science/article/abs/pii/S146350031500116X), [Sungil et all.](https://www.sciencedirect.com/science/article/abs/pii/S0920410520302461), [Harter et all.](https://www.sciencedirect.com/science/article/abs/pii/S1364682608000953). L’utilisation du système mathématique pour la génération des données puis l’ajustement sur ces données d’une méthode statistique ou une intelligence artificielle comme les réseaux de neurones. Ainsi nous avons ajusté un modèle en [Séries Chronologiques](https://fr.wikipedia.org/wiki/S%C3%A9rie_temporelle#:~:text=Une%20s%C3%A9rie%20temporelle%2C%20ou%20s%C3%A9rie,sp%C3%A9cifique%20au%20cours%20du%20temps) ARIMA(1,1,0).

Comme notre modèle est linéaire nous avons appliqué un [Filtre Kalman](https://en.wikipedia.org/wiki/Kalman_filter) classique pour notre assimilation de données. Le filtre de Kalman est bien connu et bien souvent utilisé pour l'estimation stochastique  incluant des erreurs de mesures. Par exemple, pour le cas des capteurs  où  des grandeurs  sont mesurées à chaque instant mais avec de perturbations.   

Le filtre de Kalman est composé par deux étapes : prédiction et mis à jour.  La phase de prédiction utilise l'état estimé de l'instant précédent pour produire une estimation de l'état actuel. Dans l'étape de mise à jour, les observations de l'instant courant sont utilisées pour corriger l'état prédit dans le but d'obtenir une estimation plus précise. 

La Figure ci-desous présente les résultats de l’assimilation de données avec les séries chronologiques et le filtre de Kalman. La ligne verte représente le modèle en EDP. La ligne noir représente le vrai état du système (dans les cas réels cette état n’est souvent pas disponible). Les point blues sont les mesures du poids qui sont sujet aux erreurs. La ligne rouges présentent l'estimation du poids réel d’un individu  avec  le filtre de Kalman. Finalement, les points jaunes représentent les prédictions réalisées avec l'assimilation de données.

 

Dans ce cas d’étude nous pouvons voir le potentiel de l’assimilation de données pour l’estimation d’un état réel d’un système complexe en prenant en compte les erreurs du modèle et des mesures.   

 