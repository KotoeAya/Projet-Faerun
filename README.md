##⚔️ Faërun — Stratégie Java au tour par tour
Projet de simulation d'un affrontement tactique entre deux factions ennemies, développé en Java. L'armée Bleue 🔵 et l'armée Rouge 🔴 progressent l'une vers l'autre sur un plateau configurable, leurs combattants formés depuis leurs forteresses d'origine.

##🌟 Ce que propose le jeu

Un plateau linéaire dont la taille est définie au lancement
Quatre classes de combattants aux profils distincts :

🧝 Elfe — inflige le double des dégâts de base
🪨 Nain — encaisse deux fois moins de dégâts
👑 Chef Elfe — puissance d'attaque quadruplée
🏰 Chef Nain — résistance quadruplée aux coups


Des combats case par case lorsque des unités adverses se croisent
Un système de Coup Divin : lorsqu'un guerrier atteint le maximum de dégâts possible, une exception dédiée (CoupDivinException) est levée
Deux modes de jeu : avancement automatique ou validation manuelle à chaque tour
Un mode accumulation permettant à plusieurs unités de se regrouper avant d'engager le combat
Rendu visuel ASCII directement dans le terminal


##📁 Arborescence du projet
src/jeu/
├── Application.java                          # Entrée du programme, boucle principale
├── guerrier/
│   ├── Guerrier.java                         # Classe abstraite commune à toutes les unités
│   ├── GuerrierUtilitaire.java               # Peuplement des armées dans les châteaux
│   ├── type/
│   │   ├── Elf.java
│   │   ├── Nain.java
│   │   ├── ChefElf.java
│   │   └── ChefNain.java
│   └── miscellaneous/
│       ├── ComparaisonGuerrierDefense.java   # Tri des unités par défense
│       └── CoupDivinException.java           # Exception pour les frappes maximales
└── plateauDeJeu/
    ├── Plateau.java                          # Logique de déplacement et gestion du plateau
    ├── PlateauUtilitaire.java                # Affichage terminal et configuration initiale
    ├── carreau/
    │   ├── Carreau.java                      # Représente une case (potentiel champ de bataille)
    │   └── CarreauUtilitaire.java            # Résolution des combats sur une case
    └── chateau/
        ├── Chateau.java                      # Forteresse produisant et entraînant les unités
        └── Couleur.java                      # Enum BLEU / ROUGE

##🔧 Environnement requis

Java JDK 11 ou supérieur
IntelliJ IDEA recommandé (fichier .iml et conf/debug-logging.properties inclus)


##🎮 Aperçu d'une partie
╔════════════════════════════════════════════════════════╗
║                    JEU DE FAËRUN                       ║
╚════════════════════════════════════════════════════════╝

Longueur du plateau : 10
Mode accumulation   : non
Mode continu        : oui

╔════════════════════════════════════════════════════════╗
║                    DÉBUT DU JEU                        ║
╚════════════════════════════════════════════════════════╝

[🔵🔵🔵] [  ] [  ] [  ] [  ] [  ] [  ] [  ] [  ] [🔴🔴🔴]
                        ... tour 4 ...
[  ] [  ] [🔵⚔️🔴] [  ] [  ] [  ] [  ] [  ] [  ] [  ]
La partie prend fin dès qu'une armée est intégralement anéantie.

##👤 Auteur
Réalisé dans le cadre de l'UE R2.01, BUT Informatique 1ère année — IUT2 de Grenoble.
