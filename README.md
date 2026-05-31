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

Polymorphisme : Gestion uniforme des unités sur le plateau lors des combats, indépendamment de leur type précis.

Modélisation UML : Traduction des contraintes du cahier des charges en diagramme de classes (relations de composition entre le Plateau et ses Carreau, héritage des Guerriers).

2. Gestion des Exceptions Métier
Création et levée d'une exception personnalisée (CoupDivinException) pour capturer et traiter un événement de jeu spécifique (lorsqu'un guerrier inflige le maximum de dégâts possibles).

3. Algorithmique & Structures de Données
Tri Personnalisé : Implémentation de l'interface Comparator (via ComparaisonGuerrierDefense) pour ordonner les unités selon leur potentiel défensif lors des phases critiques.

Structures linéaires : Gestion de la progression et des collisions sur un tableau de cases (Carreau).

4. Qualité logicielle & Tests Unitaires
Mise en place de plans de tests avec JUnit pour valider l'intégrité des calculs de dégâts (multiplicateurs de force des Elfes, réduction de dégâts des Nains) et le comportement du plateau.

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
