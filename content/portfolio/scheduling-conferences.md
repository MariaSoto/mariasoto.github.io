---
title: Scheduling Conferences
date: 2020-08-12T18:19:35.000+06:00
thumbnail: images/portfolio/conferences.png
service: GRASP and Tabu Search metaheuristics
client: Event company
shortDescription: Planning and optimization of training events and scientific conférences.
challenge: Optimizing the assignment of training to rooms and participants to training, while maximizing overall participants satisfaction. Taking into account the availability and wishes of the participants.
solution: Mathematical formalization of the problem and development of resolution algorithms based on GRASP and Tabu-Search metaheuristics. Implementation and deployment of the web interface.
---


# Planification d'événements
------------------------------------

Un organisateur des formations planifie chaque année pour ses adhérents une convention annuelle sur 2 jours. Durant cette convention plus de 180 formations sont proposées à plus de 500 participants. Ce groupement souhaite réduire et simplifier ce processus d'élaboration des plannings de formation et d'affectation des participants tout en répondant aux souhaits d'inscription des participants de manière maximale.  L’organisateur souhaite automatiser l'affectation des formations aux salles et des participants aux formations. Ainsi, les objectifs sont :   
- Pour chaque personne déterminer son planning des formations en satisfaisant au mieux ses priorités et en prenant en compte sa disponibilité. 
- Pour chaque formateur déterminer les formations à dispenser en prenant en compte sa disponibilité. 
- Pour chaque formation dispensée assigner une salle et une plage horaire en minimisant les coûts liés à l’utilisations des salles. 

Afin de résoudre cette problématique, j’ai proposé un modèle linéaire en nombre entiers en définissant deux types de variables de décision binaires. Le premier pour l’affectation de participants aux formations et le deuxième type pour l’affectation des formations aux salles et créneaux horaires. Les contraintes de cette problématique sont liées au respect de la capacité des salles et des disponibilités de participants, formateurs et salles. De plus, chaque personne doit être assignée à au moins une session d'une formation.  

L’organisateur souhaite maximiser la satisfaction globale de toutes les personnes inscrites. La satisfaction d’une personne est calculée comme la somme des priorités des formations affectées au participant. 

## Métaheuristique GRASP 

Afin de trouver une solution de bonne qualité et rapide, j’ai implémenté la métaheuristiques [GRASP](https://en.wikipedia.org/wiki/Greedy_randomized_adaptive_search_procedure) qui est efficace dans la construction des solutions.  En comparaison à d’autres méthodes telles que les algorithmes génétiques ou les algorithmes à voisinages multiple, cette méthode n’a pas besoin de codage et gestion de la population des solutions ou l’implémentation des voisinages complexes. 

Cette méthode itérative, exécute un certain nombre de fois la construction et l’amélioration des solutions. La meilleure solution trouvée est gardée.  Une solution est construite en deux phases : la phase de construction gloutonne aléatoire de la solution puis la phase d’amélioration de la solution.  

A chaque itération une formation est affectée aux créneaux horaires et un ensemble de participants est affecté à la formation. Les formations les plus intéressantes à affecter sont placées dans une liste appelée RCL (*Restricted Candidate List*), c'est la partie gloutonne de l'algorithme. La formation à affecter est choisie aléatoirement, c'est la partie aléatoire de l'algorithme. Cette partie permet de diversifier la génération des solutions. 

L’algorithme s’arrête après un nombre d’itérations fixe ou si la solution ne peut pas être améliorer.   

Les résultats obtenus par l’algorithme ont été satisfaisants, et le client a décidé de continuer avec le projet. Ainsi, j’ai développé une interface web pour la gestion des inscriptions des participants, le lancement de la métaheuristique d’optimisation et la visualisation des plannings. 

 
# Conférences Scientifiques 
--- 

La problématique de la planification d'événements est commune à des autres conférences et manifestations comme par exemple les conférences scientifiques. 

Dans la planification des conférences scientifiques il y a moins de contraintes. L’ensemble de formateurs n’est plus d’intérêt, nous avons un ensemble de speakers qui sont aussi les participants de la conférence.  Les sessions sont composées par des talks. L'ensemble de salles et de créneaux horaires sont limités. La capacité des salles n’est pas une contrainte par contre le type de salles est pris en compte (salle classique ou amphithéâtre).  Les souhaits et disponibilité des participants sont nécessaires dans l’assignation des sessions aux créneaux horaires et salles. 

## Métaheuristique Tabu Search
Afin de résoudre cette problématique, j’ai implémenté une métaheuristique [Tabu Search](https://en.wikipedia.org/wiki/Tabu_search), avec une liste tabu mis à jour avec le principe FIFO. La liste tabu agit comme la mémoire courte de la méthode et lui permet d’échapper des minima locaux.  Cette méthode permet d’obtenir une bonne planification dans un temps raisonnable.  

J’ai aussi développé une interface utilisateur à travers de web service afin de mettre à disposition la métaheuristique ([Complex-Event](https://complex-event.com/)). 