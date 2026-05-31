## Faërun - Jeu de Stratégie Militaire

Simulation d'un jeu de stratégie au tour par tour développé en Java. Dans ce projet, deux armées (Bleu et Rouge) s'affrontent sur un champ de bataille linéaire configurable. Chaque camp entraîne ses troupes depuis son propre château pour tenter d'annihiler les forces adverses.

Contexte du projet : Réalisé dans le cadre du module R2.01 (Développement d'applications) - BUT Informatique (1ère année) à l'IUT2 de Grenoble.

## Fonctionnalités

- **Deux Chateau** qui s'affrontent sur un plateau linéaire configurable
- **4 types de guerriers** avec des statistiques différentes :
- **Elfe** - Force ×2 par rapport à la base
- **Nain** - Dégâts reçus / 2 par rapport à la base
- **Chef Elfe** - Force ×4 par rapport à la base
- **Chef Nain** - Dégâts reçus / 4 par rapport à la base
- **Système de combat** - les guerriers s'affrontent case par case lors de leurs rencontres
- **Coups divins** - Événements générés lorsqu'un guerrier attaque avec le max de dégâts possible, situation gérée via exception (`CoupDivinException`)
- **Affichage du plateau** dans le terminal avec rendu ASCII

## Compétences

- Langage Principal : Java

- Architecture : Conception modulaire et découpage en packages (guerrier, plateauDeJeu, carreau)

- Modélisation : Conception de diagrammes de classes UML avant implémentation

## Objectifs du Projet

L'objectif principal était de concevoir un moteur de jeu autonome, capable de simuler de bout en bout un affrontement tactique équilibré entre deux factions. Les sous-objectifs incluaient :

- Modéliser un écosystème de combat complet avec des règles de statistiques modifiées selon les classes d'unités (Elfes et Nains).

- Gérer une boucle de jeu fluide (gestion des tours, déplacements des unités, résolution des combats).

- Assurer la robustesse du code face aux comportements inattendus et aux situations critiques du jeu.

## Techniques et Savoir-faire Appris

- Programmation Orientée Objet & Conception UML
  - Héritage et Abstraction : Création d'une classe abstraite Guerrier factorisant les attributs communs, dérivée en sous-classes spécifiques (Elf, Nain) pour spécialiser les comportements.

  - Polymorphisme : Gestion uniforme des unités sur le plateau lors des combats, indépendamment de leur type précis.

  - Modélisation UML : Traduction des contraintes du cahier des charges en diagramme de classes.

- Gestion des Exceptions Métier
  - Création et levée d'une exception personnalisée (CoupDivinException) pour capturer et traiter un événement de jeu spécifique (lorsqu'un guerrier inflige le maximum de dégâts possibles).

- Algorithmique & Structures de Données
  - Structures linéaires : Gestion de la progression et des collisions sur un tableau de cases (Carreau).

- Qualité logicielle & Tests Unitaires
  - Mise en place de plans de tests avec JUnit pour valider l'intégrité des calculs de dégâts (multiplicateurs de force des Elfes, réduction de dégâts des Nains) et le comportement du plateau.

## Déroulement d'une partie

```
===== DEBUT DE LA BATAILLE =====

Taille du plateau (5, 10, 15) : 10

=== TOUR DU JOUEUR BLEU ===

 Entrainer des troupes :  

1.Nain
2. Elfe
3. Chef Nain
4. Chef Elfe
5. PRET
Choix : 1

=== TOUR DU JOUEUR ROUGE ===

 Entrainer des troupes :  

1.Nain
2. Elfe
3. Chef Nain
4. Chef Elfe
5. PRET
Choix : 1

===== TOUR 1 =====

Etat du plateau au debut du tour

  |  GBleu |       |       |       |       |       |       |       |       |  GRouge |

Etat du plateau a la fin du tour

  |       |  GBleu |       |       |       |       |       |       |  GRouge |       |

===== TOUR 5 =====

Etat du plateau au debut du tour

  |       |       |       |       |  GBleu |  GRouge |       |       |       |       |

Le guerrier bleu rencontre le guerrier rouge

Etat du plateau avant la bataille

  |       |       |       |       |       |  GBleu  GRouge |       |       |       |       |


Nain BLEU frappe Nain ROUGE !
      -> Dégâts infligés : 9
      -> PV restants de la cible : 91
Nain ROUGE frappe Nain BLEU !
      -> Dégâts infligés : 11
      -> PV restants de la cible : 89
  ------------------------------

===== TOUR 9 =====

Etat du plateau au debut du tour

  |       |       |       |       |       |       |       |       |  GBleu |       |

Etat du plateau a la fin du tour

  |       |       |       |       |       |       |       |       |       |  GBleu |

 FIN DE LA GUERRE ! VAINQUEUR : BLEU
```

Le jeu se termine lorsqu'une des deux armées est entièrement éliminée.
