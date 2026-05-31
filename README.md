## Faërun — Jeu de Stratégie Militaire

Simulation d'un jeu de stratégie au tour par tour développé en Java. Dans ce projet, deux armées (Bleu et Rouge) s'affrontent sur un champ de bataille linéaire configurable. Chaque camp entraîne ses troupes depuis son propre château pour tenter d'annihiler les forces adverses.

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

Contexte du projet : Réalisé dans le cadre du module R2.01 (Développement d'applications) — BUT Informatique (1ère année) à l'IUT2 de Grenoble.

## Compétences

-Langage Principal : Java

-Architecture : Conception modulaire et découpage en packages (guerrier, plateauDeJeu, carreau)

-Modélisation : Conception de diagrammes de classes UML avant implémentation

## Structure du projet

```
src/jeu/
├── Application.java                    # Point d'entrée — initialisation et boucle de jeu
├── guerrier/
│   ├── Guerrier.java                   # Classe abstraite de base pour tous les guerriers
│   ├── GuerrierUtilitaire.java         # Initialisation des armées dans les châteaux
│   ├── type/
│   │   ├── Elf.java                    # Guerrier Elfe (force ×2)
│   │   ├── Nain.java                   # Guerrier Nain
│   │   ├── ChefElf.java                # Chef Elfe
│   │   └── ChefNain.java               # Chef Nain
│   └── miscellaneous/
│       ├── ComparaisonGuerrierDefense.java   # Comparateur pour trier par défense
│       └── CoupDivinException.java           # Exception pour les coups spéciaux
└── plateauDeJeu/
    ├── Plateau.java                    # Gestion du plateau et de la progression des guerriers
    ├── PlateauUtilitaire.java          # Affichage et saisie des paramètres du plateau
    ├── carreau/
    │   ├── Carreau.java                # Une case du plateau (peut être un champ de bataille)
    │   └── CarreauUtilitaire.java      # Logique de combat sur une case
    └── chateau/
        ├── Chateau.java                # Château qui entraîne et produit des guerriers
        └── Couleur.java                # Énumération BLEU / ROUGE
```

## Déroulement d'une partie

```
╔════════════════════════════════════════════════════════╗
║                      JEU DE FAËRUN                     ║
╚════════════════════════════════════════════════════════╝

Longueur du plateau : 10
Mode accumulation : non
Mode continu : oui

╔════════════════════════════════════════════════════════╗
║                      DÉBUT DU JEU                      ║
╚════════════════════════════════════════════════════════╝

[🔵🔵🔵] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [ ] [🔴🔴🔴]
                      ... tour 4 ...
[  ] [ ] [🔵⚔️🔴] [ ] [ ] [ ] [ ] [ ] [ ] [  ]
```

Le jeu se termine lorsqu'une des deux armées est entièrement éliminée.

Projet réalisé dans le cadre du **module R2.01** — BUT Informatique 1ère année, IUT2 Grenoble.
