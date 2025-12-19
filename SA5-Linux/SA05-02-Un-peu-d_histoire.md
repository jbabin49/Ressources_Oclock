<h1 align=center>Un peu d'histoire</h1>

Origines et évolution des systèmes d'exploitation jusqu'à Linux.

---

# Les années 50
Les premiers ordinateurs étaient de simples machines à calculer électroniques ou électro-mécaniques.

Les systèmes d'exploitation étaient à l'époque très simples : ils étaient conçus pour fonctionner sur une machine spécifique, et ne pouvaient effectuer qu'un nombre très limité de tâches (des calculs mathématiques).

En réalité, on ne parle même pas de système d'exploitation sur ces premiers ordinateurs ! Les programmes lancés sur la machine manipulaient directement les ressources matérielles de la machine, sans passer par un intermédiaire.

---

# Interopérabilité et partage
Les ordinateurs ne pouvaient pas communiquer entre-eux.

Une entreprise qui changeait d'ordinateur devait entrer à nouveau toutes les données nécessaires aux calculs dans la nouvelle machine.

Autre problème : les ordinateurs ne pouvaient être utilisés que par une seule personne à la fois, l'opérateur.

Cette personne (ou équipe de personnes) chargait des cartes perforées dans un lecteur puis lançait les calculs. Ces cartes contenaient les instructions d'un programme ou des données.

C'est pour résoudre ce problème d'interopérabilité (communication entre deux systèmes) et pour permettre à plusieurs personnes de travailler sur un même ordinateur que le premier projet de création d'un système d'exploitation "moderne" a vu le jour.

---

# Multics
MULTIplexed Information and Computing Service

Le projet Multics a été lancé en 1964, conjointement par le MIT, les Laboratoires Bell (AT&T) et par General Electric.

Ce projet a apporté de nombreux concepts novateurs :
- temps partagé
- multitâche préemptif
- système de fichiers hiérarchique
- multi-utilisateurs
- sécurité

Ces concepts ont été repris dans la plupart des systèmes d'exploitation modernes, Multics a influencé tous les systèmes qui lui ont succédé.

Multics a été développé sur et pour des machines GE 645, mainframe 36-bits conçu spécialement pour ce système. Le premier GE 645 a été livré au MIT en janvier 1967.

Malgré les nombreuses innovations de Multics, il avait également des défauts : sa taille et sa complexité ne lui permettait que de fonctionner sur des machines très coûteuses et imposantes. Plusieurs chercheurs des laboratoires Bell, frustrés par ces défauts, ont commencé à quitter le projet.

Les laboratoires Bell ont fini par se retirer du projet en 1969, lassés par le temps que prenait le projet à être réalisé. Peu de temps après, en 1970, General Electric décident de fermer et revendre leur division informatique à Honeywell.

Honeywell ont continué à développer Multics et l'ont commercialisé jusqu'en 1985. Plus de 80 mainframe coûtant plusieurs millions de dollars ont été installés chez des industriels, universités (dont certaines universités françaises !) et gouvernements dans ces années-là. Honeywell fut racheté par Bull à la fin des années 80, qui continuèrent à distribuer Multics jusqu'à l'an 2000 (année au cours de laquelle le dernier système Multics en production fut éteint définitivement).

---

# Unix
Unics = Uniplexed Information and Computing Service

Les derniers chercheurs des Laboratoires Bell à quitter le projet Multics furent Ken Thompson, Dennis Ritchie, Douglas McIlroy et Joe Ossanna. Ils décidèrent de mettre à profit l'expérience acquise sur le projet Multics sur un plus petit projet, sans nom et sans soutien financier.

Le nom Unics fut proposé en 1970 par Brian Kernighan, un autre chercheur des laboratoires Bell. La même année, le projet reçu un financement par le biais de la mise à disposition d'une machine PDP-11/45 (jusque-là, Unix était développé sur PDP-7).

Entre 1972 et 1973, Dennis Ritchie développa le langage C, conçu pour construire des programmes/utilitaires pour le système Unix. En 1973, la version 4 d'Unix fut réécrite en C. La version 5, sortie également en 1973, fut la première à être commercialisée à des universités.

Unix fut commercialisé pour la première fois à des entreprises à partir de sa version 6, sortie en 1975. En 1975, Ken Thompson pris un congé sabatique, et fut invité comme professeur à l'université de Berkeley. Il aida l'université à installer la version 6 d'Unix sur leur machine PDP-11 et travailla sur une implémentation du langage Pascal pour Unix.

Deux étudiant de l'université de Berkeley, Chuck Haley et Bill Joy, ont par la suite amélioré l'implémentation Pascal de Ken Thompson. Ils ont également ajouté au système un éditeur de texte écrit par Bill Joy, appelé ex. En 1977, Bill Joy commença à compiler cette version enrichie d'Unix, d'autres universités ayant montré un intérêt pour ce projet.

La première version de BSD (Berkeley Software Distribution) fut publiée le 9 Mars 1978. Ce n'était qu'un "add-on" pour Unix version 6, à l'époque. La famille BSD était née !

D'autres versions d'Unix et de BSD ont suivi, mais on va pas y passer 3 jours donc une image fera l'affaire :

Les descendants des premiers systèmes Unix sont toujours utilisés de nos jours :
- MacOS, basé sur BSD/FreeBSD.
- FreeBSD, un descendant open-source de BSD, utilisé sur certains équipements réseau (pfSense est basé sur FreeBSD !)
- NetBSD, OpenBSD, DragonFlyBSD, relativement peu utilisés mais encore maintenus !
- Oracle Solaris
- HP-UX
- IBM AIX
- etc.

---

# Philosophie UNIX
Les développeurs qui travaillent sur les systèmes UNIX suivent certains principes :
- Écrivez des programmes qui effectuent une seule chose, et qui le font bien.
- Écrivez des programmes qui collaborent.
- Écrivez des programmes pour gérer des flux de texte, car c'est une interface universelle.

On ajoute parfois d'autres principes, comme le principe KISS : Keep It Simple, Stupid (à comprendre dans le sens "ne pas compliquer inutilement les choses").

---

# POSIX
POSIX est une famille de normes techniques, définie par l'IEEE (groupe IEEE 1003). Ces normes définissent des standards et spécifications pour les éléments de base d'un système d'exploitation :
- ligne de commande
- nombreux utilitaires/programmes de base
- entrées/sorties
- gestion du réseau
- gestion des threads
- etc.

C'est grâce au respect de ces normes que les commandes utilisées sur Unix, Linux, BSD ou MacOS ne diffèrent pas (ou peu), par exemple.

---

# Le projet GNU
Avant, il faut qu'on parle du projet GNU.

GNU is Not Unix

Tout a commencé avec une imprimante laser Xerox 9700 :
En 1980, Richard Matthew Stallman (souvent appelé rms) était développeur au AI Lab du MIT. Dans ce laboratoire, il y avait une imprimante laser qui occupait un étage entier, loin de là où travaillaient les développeurs. Cette imprimante était utilisée par plusieurs personnes, qui ne savaient pas si leur document était sorti de la file d'attente ou s'il y avait eu un bourrage papier avant de se déplacer. C'était une perte de temps importante de devoir retourner à son poste relancer l'impression après un échec.

Pour résoudre ce problème, Richard Stallman a modifié le pilote de l'imprimante pour qu'un message soit envoyé à l'utilisateur une fois son document imprimé, ou qu'un message soit envoyé à tous les utilisateurs dans la file d'attente en cas de bourrage papier. L'histoire aurait pu s'arrêter là, mais le MIT a décidé de remplacer cette imprimante par une Xerox 9700. Richard Stallman, voulant implémenter cette fonctionnalité sur la nouvelle imprimante, a demandé à Xerox le code source du pilote. Xerox a refusé.

Cette expérience a convaincue rms de l'importance pour les utilisateurs de pouvoir modifier/enrichir librement les logiciels dont ils ont besoin pour travailler.

En Septembre 1983, rms annonce qu'il commence à travailler sur un système d'exploitation compatible avec Unix, très populaire à l'époque mais qui avait l'inconvénient d'être propriétaire. On dit d'un logiciel qu'il est "propriétaire" (proprietary en anglais) quand son contrat de licence stipule que seul l'auteur du logiciel a le droit d'y apporter des modifications et de le distribuer. La "compatibilité" avec Unix était nécessaire pour que les utilisateurs de ce dernier puissent facilement basculer sur le nouveau système développé par Richard Stallman.

Le projet GNU était né ! Le nom GNU, acronyme récursif de GNU is Not Unix, a été choisi pour symboliser le fait que GNU était comme Unix, sans être Unix. Contrairement à Unix, le système d'exploitation GNU devait être complètement libre (free, en anglais). Richard Stallman a quitté son travail au MIT (craignant que le MIT s'attribue son travail) et a fondé en 1985 la Free Software Foundation (FSF).

Attention, le terme free ne doit pas être traduit en Français par gratuit, mais par libre. La FSF indique d'ailleurs :
Free as in free speech and not free beer.

---

# Logiciel libre et copyleft
La notion de logiciel libre était née ! Pour encadrer légalement ces logiciels, rms et la FSF ont créé en 1989 une licence spécifique, intitulée GNU General Public Licence, abregée GNU GPL. La dernière version de cette licence est la v3.

On désigne cette licence (et d'autres licences équivalentes) comme une licence copyleft, par opposition à copyright. Le principe ? Vous êtes libres de modifier, partager, redistribuer un logiciel sous licence libre. La seule contrainte est que vos modifications doivent être partagées avec les mêmes droits.

---

# Le projet GNU, suite
Unix étant un système modulaire, rms et la FSF ont pu développer les composants du système GNU brique par brique. La première brique que rms a développé a été le compilateur pour langage C, GNU GCC (GNU Compiler Collection), disponible dès juin 1984. Il a ensuite rapidement porté son éditeur de texte Emacs, qui n'était jusque-là pas compatible Unix.

Les briques principales du système d'exploitation GNU sont les suivantes :
- GNU GCC, le compilateur
- GNU C libraby (glibc)
- GNU Core Utilities (coreutils)
- GNU Debugger (GDB)
- GNU Binary Utilities (binutils)
- GNU Bash

Toutes ces briques (on reviendra en détail sur certaines) étaient prêtes au tout début des années 90. Il ne manquait qu'une chose : le noyau.

La production d'un noyau GNU nommé Hurd est lancée en 1990. La dernière version de ce noyau est la 0.9, sortie en décembre 2016. Il n'est toujours pas considéré comme étant terminé et complètement opérationnel.

Au début des années 90, le système d'exploitation GNU est donc loin d'être utilisable, faute de noyau. Mais un autre projet open-source va proposer une solution à ce problème : Linux !

---

# Linux
Au début des années 90, un étudiant Finlandais du nom de Linus Torvalds a acheté un micro-ordinateur de type PC, équipé d'un microprocesseur intel 386, pour se former à cette plateforme. Ce PC était livré avec MS-DOS, sur lequel Linus a joué quelques jours à Prince of Persia. Habitué aux systèmes Unix, Linus a rapidement remplacé MS-DOS par le système d'exploitation Minix pour des fins pédagogiques.

Minix était conçu autour d'un micro-noyau, volontairement simple pour que son architecture soit comprise facilement par les étudiants d'Andrew Tanenbaum. Linus préférait le système Unix qu'il utilisait à l'université, mais ne pouvait pas se permettre de l'acheter pour sa machine personnelle. Andrew Tanenbaum ne souhaitait pas faire évoluer Minix. Linus a donc décidé de créer son propre noyau de système d'exploitation.

Le message posté par Linus sur le groupe Usenet comp.os.minix, le 25 août 1991, marque le début du projet Linux. Ce qui allait devenir le noyau Linux avait une architecture différente de Minix : un noyau monolithique pour Linux, un micro-noyau pour Minix.

Pour l'anecdote, Andrew S. Tanenbaum aurait répondu à Linus avec ce message :
"Je pense que concevoir un noyau monolithique en 1991 est une très mauvaise idée. Estime-toi heureux de ne pas être un de mes étudiants. Tu n'obtiendrais pas une bonne note pour une telle conception."

La première version complète fut la v0.02, publiée le 5 octobre 1991. Cette version embarquait déjà plusieurs outils GNU (bash et GCC, par exemple). En 1992, Linus décide de publier son noyau sous licence GNU GPL, décision qui a permis à la communauté GNU de s'associer à la communauté naissante autour de ce nouveau noyau. Cette collaboration a donné naissance au système d'exploitation GNU/Linux.

Encore une anecdote : Linus voulait appeler son noyau Freax (contraction des mots free, freak et x pour Unix). Ari Lemmke, qui gérait le serveur FTP sur lequel Linus uploadait son travail, a décidé de renommer le noyau pour l'appeler Linux sans consulter Linus (ce dernier trouvait le nom Linux trop égocentrique).

Tux, le manchot (pas un pingouin !) dessiné par Larry Ewing, devient la mascotte du projet Linux en 1996.

La mise à disposition du code du noyau Linux a suscité beaucoup d'intérêt auprès de la communauté de Minix et des informaticiens en général. Des milliers de développeurs bénévoles à travers le monde ont contribué et contribuent encore à son développement. De nombreuses entreprises (Intel, IBM, Valve, Novell, etc.) collaborent aujourd'hui au côté des développeurs bénévoles, et Linus Torvalds est toujours le coordonnateur du projet (il se qualifie lui-même de "dictateur bienveillant").

Le développement de Linux est effectué exclusivement par Internet : notamment par des échanges de mails et grâce à l'utilisation de Git, développé également par Linus Torvalds. Le modèle de développement de Linux est considéré comme un exemple de réussite pour un projet open-source.

En 2024, le noyau Linux est toujours en développement actif, de nouvelles fonctionnalités et des nouveaux pilotes de périphériques sont implémentés pour suivre l'évolution de l'informatique. Au moment où j'écris ces lignes, la dernière version du noyau est la 6.10, publiée le 14 juillet 2024. La version stable est la 6.9.9 (publiée 3 jours avant).

Une particularité des systèmes GNU/Linux : il n'en existe pas qu'un seul ! Il existe de nombreuses distributions GNU/Linux, on voit ça juste après.

---
