<h1 align=center>Linux : notions de base</h1>

Introduction complète à la ligne de commande, au système de fichiers et aux manipulations essentielles sous GNU/Linux.

---

# Au programme
- interface en lignes de commande
  - prompt
  - commandes usuelles
  - arguments
  - raccourcis et caractères spéciaux
- système de fichiers
  - arborescence et dossiers usuels
  - chemin relatif ou absolu
- entrées, sorties, redirections
- manipulation de fichiers texte

---

# CLI
Command Line Interface

---

# IHM : CLI vs. GUI
Avant l'apogée des interfaces graphiques (GUI - Graphical User Interface) avec l'arrivée de la souris, l'interface homme-machine (IHM) d'un système informatique était la ligne de commande (CLI - Command Line Interface).

Sur Windows et MacOS, la CLI est encore présente, mais n'est généralement pas ou peu utilisée par la plupart des utilisateurs.

Sur GNU/Linux, ce n'est pas le cas ! On peut parfois s'en passer dans certains environnements de bureau, mais ce n'est pas tout le temps judicieux : la CLI est souvent plus efficace qu'une interface graphique, pas besoin de chercher où cliquer parmi des dizaines de menus et boutons !

La CLI impose par contre de lire la documentation (RTFM !), ce qui n'est pas forcément le cas pour les GUI.

Une interface graphique est plus intuitive, mais pas nécessairement plus simple que copier/coller une ligne de commande.

---

# Prompt
Invite de commande, en français.

---

# Commandes usuelles
Voici quelques commandes fréquemment utilisées :
- ls : liste les fichiers et dossiers présents dans un dossier
- pwd : affiche le chemin absolu du dossier courant
- cd : changer le dossier courant
- mv : déplacer un ou plusieurs fichiers/dossiers
- rm : supprimer un ou plusieurs fichiers
- rmdir : supprimer un ou plusieurs dossiers
- mkdir : créer un dossier
- touch : créer un fichier
- sudo : lancer une commande en tant que super-utilisateur (root)
- man : affiche la documentation (manpage) d'une commande
- cat : affiche le contenu d'un fichier
- less : lire un fichier page par page
- head : affiche les premières lignes d'un fichier
- tail : affiche les dernières lignes d'un fichier
- ln : créer un lien vers un fichier
- find : rechercher un ou plusieurs fichiers/dossiers
- grep : recherche une chaîne de caractères dans des fichiers ou depuis l'entrée standard
- shutdown : éteindre l'ordinateur
- reboot : redémarrer l'ordinateur
- df : afficher l'espace disque libre/utilisé
- free : affiche la mémoire vive (RAM) libre/utilisée
- uptime : affiche la durée de fonctionnement de la machine
- uname : affiche des infos sur le système
- file : permet d'identifier un fichier à partir de son type MIME

---

# Arguments
Les commandes peuvent être utilisées avec des arguments pour changer leur comportement, spécifier des paramètres, etc. Les arguments acceptés sont propres à chaque commande !

Exemple pour ls :
- -a : lister tous les fichiers et dossiers, y compris ceux cachés
- -l : afficher plus d'infos sur les fichiers et dossiers
- -h : afficher certaines infos dans un format lisible

---

# Raccourcis et caractères spéciaux
- ~ : chemin vers le dossier de l'utilisateur courant
- . : dossier courant
- .. : dossier parent
- !! : commande précédemment lancée
- * : wildcard
- {,} : sélecteur multiple

---

# Système de fichiers
Sous Linux, tout est fichier !
- périphériques, processus, dossiers, fichiers

Arborescence typique :
```
/               (racine du système de fichier)
├── bin         (binaires / exécutables)
├── boot        (fichiers du chargeur d'amorçage)
├── dev         (périphériques du système)
├── etc         (fichiers de configuration)
├── home        (répertoires personnels des utilisateurs)
│   ├── alice
│   │   ├── Bureau
│   │   └── Documents
│   └── bob
│       ├── Bureau
│       └── Documents
├── media       (points de montage pour médias amovibles)
├── mnt         (point de montage temporaire)
├── opt         (logiciels tiers)
├── proc        (processus en cours d'exécution)
```

---

# Chemin relatif ou absolu
- Chemin absolu : depuis la racine du disque
- Chemin relatif : relatif au dossier courant

Exemple :
- /home/bob/text.txt (GNU/Linux)
- ../Documents/test.txt (chemin relatif)

---

# Entrées, sorties, redirections
Chaque commande possède une entrée standard (stdin) et une sortie standard (stdout), et une sortie dédiée aux erreurs (stderr).

Redirection vers un fichier :
- > ou >> pour rediriger la sortie standard
- 2> pour rediriger les erreurs
- 2>&1 pour rediriger les erreurs dans le même fichier que la sortie standard
- < pour rediriger un fichier vers l'entrée standard

---

# Chaînage de commandes
On peut chaîner des commandes avec le pipe |.
Exemple :
- ls | wc -l
- cat /etc/sysctl.conf | grep "ip_forward"

---

# Manipulation de fichiers texte
- QED, Ed, grep, sed, awk, ex/vi, Vim, Emacs, Nano
- Guerre des éditeurs : Emacs vs Vi

---
