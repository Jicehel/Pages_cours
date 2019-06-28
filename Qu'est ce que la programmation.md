## Qu’est-ce que la programmation ?

Dans ce chapitre, nous allons ensemble comprendre les bases de la programmation. 
Ne vous inquiétez pas, nous allons partir de zéro, aucune connaissance n'est requise pour suivre ce tutoriel.


### La programmation
La **programmation**, c’est l’action de **programmer** quelque chose, c’est-à-dire établir à l'avance une suite d'opérations; planifier, déterminer à l'avance le moment et les modalités d'une action.
En informatique, c’est l’ensemble des activités liées à la définition, l'écriture, la mise au point et l'exécution de **programmes informatiques**.


### Le programme

Une **instruction** est un ordre, une action que le processeur doit suivre.
Un **programme** est une suite d'**instructions** et de **données** écrites à l'avance par le programmeur, susceptible d'être exécutée par un ordinateur ou autre système électronique programmable. 
Cela peut être un jeu vidéo, un tableur, un traitement de texte, une animation de leds, un système d’alarme, un système de contrôle d’un circuit de train électrique…
Lorsque vous mettez le programme en marche, le système applique alors les instructions dans l’ordre dans lequel elles ont été placées dans le programme afin d’atteindre l’objectif attendu, ou du moins c'est ce que l'on espère obtenir...

<p align="center"><img class="fit-picture"       src="https://i.goopics.net/8gkm7.png"      alt="Schéma d'un programme" /></p>


#### Pour information:
Les instructions sont liées à un langage, vous ne pouvez pas en inventer. Ce sont les composants élémentaires de ce langage. Quand vous communiquez avec quelqu'un vous utilisez des mots du dictionnaire de ce langage. C'est pareil pour un langage de programmation: vous devez utiliser les instructions définies afin que le programme puisse s'éxecuter.

![Programme binaire](https://www.institut-pandore.com/wp-content/uploads/2016/11/binaryCode.gif)

Autre difficulté: les systèmes informatiques classiques (on n'étudiera pas la programmation quantique dans ce cours...) ne comprennent que des 0 et des 1 mais il serait quasiment impossible de programmer directement sous cette forme...C'est ce que l'on appelle la programmation binaire et la mémoire est remplie de "cases" contenant soit un 0, soit un 1. C'est ce que l'on appelle un bit. Pour manipuler ces bits les systèmes utilisent un ensemble de composants électroniques: “des portes logiques” capablent de faire un traitement élémentaire. Nous n'étudierons pas en détail ces 'portes' mais pour information, elles peuvent être de type: VRAI, FAUX, NON (NOT), OUI, ET (AND), NON-ET (NAND), OU (OR), NON-OU (NOR), OU exclusif (XOR), NON-OU exclusif ou équivalence (XNOR), ...


#### A retenir:
**Binaire** : Qui n'est composé que de 0 et de 1.
**Langage machine** : Ensemble des instructions compréhensibles par l'ordinateur, elles sont écrites en binaire.
**Bit** : Unité du binaire. Chaque 1 ou 0 est appelé un bit. Par exemple, 1101 contient 4 bits. Ce mot vient de l'anglais.

Pour communiquer avec un système, il nous faut donc utiliser un " traducteur ", c'est à dire quelque chose qui va pouvoir traduire un langage plus facile à utiliser pour un être humain en un langage compréhensible par le système. Ce que l'on écrit s'appelle le **code source** et le système qui le traite pour le traduire pour l'ordinateur peut soit directement l'interpréter, c'est à dire qu'il traite les instructions les unes à la suite des autres mais le programme aura toujours besoin de cet interpréteur afin de pouvoir être exécuté ou être compilé une fois pour toute grâce à un comilateur qui transformera ce code source en exécutable (c'est à dire en programme binaire directement compréhensible par le système).


#### A retenir:
**Langage interprété**: Un langage interprété est un langage ou chaque ligne d’instruction est lue et traduite pour être exécutée. 
Un programme auxiliaire (l'interpréteur) est nécessaire à son exécution pour traduire au fur et à mesure les instructions du programme.
C'est le cas actuellement du Python sur la Gamebuino META: le code source est interprété sur la console mais vous n'avez pas à le compiler

![Programme interprété](http://data.france-ioi.org/Course/general_interpreted_vs_compiled/schema_interpreted_FR.png)


**Langage compilé**: Avec un langage compilé, le développeur du logiciel écrit son code source puis effectue une opération appellée **compilation** à partir d’un logiciel spécial appelé **compilateur**. Ce programme va convertir l’ensemble du code source en code machine. Pour exécuter le programme, il n’y a alors besoin que de ce fichier compilé: l'**exécutable**.
C'est le cas actuellement pour le C++ sur la Gamebuino META, avant de pouvoir exécuter le code de vos jeux, vous devez les compiler puis mettre l'executable obtenu sur la carte mémoire pour pouvoir l'exécuter.
Avec la Gamebuino META, nous utilisons ce type de langage

![Programme compilé](http://data.france-ioi.org/Course/general_interpreted_vs_compiled/schema_compiled_FR.png)


### Apprendre à écrire des programmes

Sauf dans des cas très simples, on ne crée pas un programme en se lançant directement dans l’écriture du code source mais on prend un peu de temps pour réflèchir à ce que l'on veut faire afin de le décomposer en sous parties simples et en essayant de réfléchir au cas particuliers. Cela permet d'essayer de traiter le problème dans son intégralité, en se concentrant sur une seule partie à la fois et de structurer son programme. Avec le temps, le fait de structurer son programme permet aussi de pouvoir réutiliser des parties que l'on a déjà codées dans un autre programme, mais nous verrons ça plus tard.
Le fait de structurer son programme permet aussi d'obtenir un code source plus lisible.
Le fait d'avoir réfléchit un peu aux différents problèmes possibles et aux cas particuliers permet également d'éviter beaucoup d’erreurs (bogues) et le temps investi au début de votre projet évitera d'en perdre plus, plus tard, lors de la recherche de ces bogues et autres défauts que vous verriez apparaitre lors de vos tests.
La première étape pour écrire un programme est donc l’analyse de ce qui est à faire et la suite d’opérations à réaliser pour y arriver en le décomposant en plusieurs petits ensemble d'instruction visant à effectuer des tâches simples.

Prenons un exemple de la vie quotidienne: Je veux faire cuire des pâtes, il va me falloir sortir une casserole, mettre de l’eau dans la casserole, ajouter du gros sel, mettre la casserole sur le feu. Il faudra ensuite attendre que l'eau boue avant d'y verser les pâtes puis attendre de nouveau que le temps de cuisson soit écoulé avant de les égouter puis de les servir dans un plat
Nous avons réfléchit à une progression logique de suite de tâches à effectuer.
Il existe un formalisme pour l'écriture de ces tâches en informatique: c'est ce que l'on appelle l'alogrithmique. Nous ne l'étudierons pas dans ce chapitre pour ne pas le surcharger.

#### A retenir:

**alogrithmique** étude et production de règles et techniques impliquées dans la définition et la conception d'algorithmes, c'est-à-dire de processus systématiques de résolution d'un problème en décrivant précisément les étapes à suivre pour résoudre ce problème.   
**algorithme**: suite ordonnée d’opérations permettant de résoudre un problème donné
