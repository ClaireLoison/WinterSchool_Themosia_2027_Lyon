# Support pour les discussions, tout peut être modifié

## Jour 1: introduction à la MD [Florian/Natacha]

### Matin: Cours théorique: 
- principes de la MD; notions de champs de forces/modèle d’eau, brève présentation des stratégies de paramétrisation; intégrateurs, thermostats/barostats, notions importantes de mécanique statistique (fonction de partition, distribution de Boltzmann, énergie libre)
- survol de quelques exemples? (pour illustrer le genre de questions qui peuvent être abordées avec la MD)
- Présentation de l’adenylate kinase : notion de catalyse, importance de l’environnement d’une réaction, relation structure/propriété, propriété générales des protéines, importance des changements et des fluctuations de conformations, besoin de dynamique/statistique.
- Ensembles générés par l’IA (Otten et al.)    
- MD en pratique: vocabulaire et présentation des types de fichiers, présentation du workflow préparation du système → minimisation → chauffage/équilibration → production

### Après-midi: TP: 

- préparation de la boîte et minimisation/chauffage/équilibration; avant de partir on lance la production overnight
GROMACS (avec les tutos); VMD; montrer comment est organisé un fichier de topologie et comment on peut éventuellement le modifier; inspecter les fichiers du champ de forces;

## Jour 2: Analyse des trajectoires [qui?]

### Matin Cours théorique
 suite du cours du jour 1? ou présentation machine learning/IA pour l’analyse des trajectoires? Autre chose?
### Après-midi TP: 
Analyse des trajectoires en Python (Jupyter notebooks; MDAnalysis/mdtraj sklearn pour le ML?)

- aborder la question de la stochasticité/reproductibilité des simulations; “expériences numériques”;
- comment valider les simulations? Répliques, comparaison, et comparaison avec des données expérimentales
- données FRET [à retrouver] : calcul des distances correspondantes et comparaison

## Jour 3: enhanced sampling and free energy profiles along collective variables [Florian]
### Matin cours théorique: 
- mécanique statistique: définition de l’énergie libre, du profil d’énergie libre le long d’une variable collective; lien hauteur de barrière/taux / théorie de Kramers;  
- umbrella sampling: set up, reconstruction du PMF avec MBAR
- méthodes adaptatives: bases théoriques de la wt metadynamics et/ou ABF
- String method in collective variables?

## Jour 4: Markov State Models (?) [Claire]
(définitions, clustering / clustering cinétique, principes variationnels; implied timescales? Chapman-Kolmogorov test? TICA; VAMPnets?)

### Cours / TP 

#### Remarque : L’analyse des trajectoires au jour 1 pourrait contenir des notions qu’on va utiliser ensuite en général ou en MSM
1. la notion de clustering (distances dans un espace a beaucoup de dimensions)
2. des mesures de  descripteurs : distances/angle => liaison hydrogene, salt-brige  
3. la notion de réduction de dimensionalité (prendre une simple : PCA)
4. la notion de PMF
5. les  transitions entre deux états et leurs caractéristiques

#### Notions du cours
- définition d’un MSM
- Liens avec expérience (le FRET ou les expériences RMN)
- Objectif  : définir un MSM dont les paramètres sont issus d’une MD (nombre de clusters, definition des clusters, calcul d’une matrice de transition)
- Validation des MSM
- Cas simple avec une trajectoire de MD ‘idéale’  où on voit beaucoup de transition et la projection est simple (TP : MSM sur  rotation d’un methyle)
- Difficultés et solutions pour des transitions conformationnelles 
        ◦ clustering : réduction de dimension  plus ‘intelligente’ (PCA=> TICA, Vampnets, autres)
        ◦ clustering en deux étapes :  structural, puis cinétique.

- Avantages du MSM :
        ◦ bases théoriques solides
        ◦ outils numériques disponibles
        ◦ exploitation du modèle sur des temps non visibles sur la trajectoire 
        ◦ calculs de  cinétiques, éventuellement à long terme, dans tous les cas possibles  TP
        ◦ comparaison avec l’expérience
        ◦ exploitation de plusieurs trajectoires indépendantes
        ◦ exploitation des trajectoires hors-équilibre
- Désavantages du MSM
        ◦ difficile de vraiment valider
        ◦ difficile de mesurer des barres d’erreur
        ◦ hypothèses sur les probabilités conditionelles
        ◦ biais du choix des trajectoires

#### TP1 : MSM sur rotation d’un methyle
#### TP2 : MSM sur trajectoire Cui
#### TP2 : Simulations/Analyses d'un MSM

## Jour 5 : QM/MM for enzymatic reactivity [Natacha]
### matin: théorie/méthodes 
### TP: reaction mechanism and profile 

# Notes Claire 

-  Pour le jour 1, je proposerai de faire la préparation du fichiers de position initial à partir des fichiers de la PDB, pour que les personnes aient toutes les étapes et aussi se posent les questions associées :  
1. un fichier PDB représente des informations d’un système très spécifique dans des conditions spéciales, lequel dois-je choisir  et quelles sont les hypothèses associées ?  
1. un fichier PDB contient des informations partielles (hydrogène, état de protonation), et des informations “jetées” (position des molécules d’eau, ligand  ou ions parfois, plusieurs positions parfois, residus manquants, mutations,...).
1. comment je complète ces informations ?  







