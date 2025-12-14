# SA5E03 - Linux / Sécurité et administration

Pour pratiquer les notions du jour, votre mission est d’installer une VM Rocky Linux (le successeur de CentOS, la version communautaire de Red Hat Entreprise Linux).

Sur cette VM, vous devez :
1. Créer un nouvel utilisateur
2. Permettre à cet utilisateur de lancer des commandes avec sudo
3. Créer un groupe, mettre le nouvel utilisateur et l’utilisateur créé lors de l’installation dans ce groupe
4. Créer un dossier /home/partage_fichier et modifier ses permissions pour que les membres du groupe créé précédemment aient les droits de lecture et d’écriture, mais qu’aucun autre utilisateur du système n’y ait accès.
5. Créer un dernier utilisateur et vérifier qu’il n’a pas accès au dossier créé précédemment
6. Bonus : faire en sorte qu’aucun mot de passe ne soit demandé pour lancer la commande rpm

## 1. Créer un nouvel utilisateur

Pour créer le nouvel utilisateur `alice`, on utilise la commande : `sudo useradd -m -c "Alice" alice`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `useradd` : ajouter un utilisateur
* `-m` : créer automatiquement le dossier personnel `/home/alice`
* `-c "Alice"` : commentaire (gecos) pour donner le nom complet de l'utilisateur par exemple
* `alice` : login, le nom de l'utilisateur pour se connecter

<img width="678" height="139" alt="useradd" src="https://github.com/user-attachments/assets/2617cbf1-b21b-44da-a139-d42e4a91d308" />

Pour ajouter un mot de passe au compte d'Alice, on utlise la commande : `sudo passwd alice`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `passwd` : modifier un mot de passe
* `alice` : utilisateur pour qui on veut modifier le mot de passe

Le mot de passe `alice` que j'ai utilisé ici n'est pas sécurisé et on nous le dit.

<img width="646" height="202" alt="passwd" src="https://github.com/user-attachments/assets/37a84e40-a786-441e-b507-d2e6714651dd" />

## 2. Permettre à cet utilisateur de lancer des commandes avec sudo

Pour permettre à Alice de lancer des commandes avec sudo, il faut l'ajouter au groupe sudo.

Pour se faire, on utilise la commande : `sudo usermod -aG wheel alice`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `usermod` : modifier un utilisateur
* `-aG` : `a` pour ajouter sans écraser les groupes secondaires déjà existant, `G` pour la liste du/des groupe(s) à ajouter
* `wheel` : le groupe auquel on veut ajouter l'utilisateur (le groupe super-user est wheel et pas sudo sur Rocky Linux), on les sépare par une virgule si on veut ajouter plusieurs groupes (groupe1,groupe2...)
* `alice` : le nom de l'utilisateur concerné

<img width="678" height="139" alt="usermod_wheel_alice" src="https://github.com/user-attachments/assets/3b311c01-4f2f-4322-a034-c42a4e2145d7" />

## 3. Créer un groupe, mettre le nouvel utilisateur et l’utilisateur créé lors de l’installation dans ce groupe

Pour créer un groupe on va utiliser la commande : `sudo groupadd -U alice,bob aliceetbob`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `groupadd` : ajouter un groupe
* `-U` : pour lister les utilisateurs qu'on veut ajouter au groupe
* `alice,bob` : les utilisateurs à ajouter au groupe, séparés par une virgule
* `aliceetbob` : nom du groupe qu'on veut créer

<img width="671" height="112" alt="groupadd_aliceetbob" src="https://github.com/user-attachments/assets/fb4b26d2-8640-49f4-acbe-6cb17673d970" />

## 4. Créer un dossier /home/partage_fichier et modifier ses permissions pour que les membres du groupe créé précédemment aient les droits de lecture et d’écriture, mais qu’aucun autre utilisateur du système n’y ait accès.

Pour créer le dossier /home/paratge_fichier on utlise la commande `sudo mkdir /home/partage_fichier`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `mkdir` : créer un dossier
* `/home/partage_fichier` : chemin du dossier à créer

<img width="682" height="167" alt="mkdir_partage_fichier" src="https://github.com/user-attachments/assets/d55df990-fc13-42fd-9378-72387730f47c" />

Pour modifier les permissions pour que seulement alice et bob qui sont membres du groupe aliceetbob aient les droits de lectures et d'écriture, mais qu'aucun autre utilisateur n'y ait accès, on va utliser deux commandes :
* Pour modifier le groupe propriétaire du dossier on utilise : `sudo chgrp aliceetbob /home/partage_fichier`
  * `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
  * `chgrp` : pour modifier le groupe propriétaire
  * `aliceetbob` : nom du nouveau groupe propriétaire
  * `/home/partage_fichier` : chemin du dossier concerné
 
* Pour modifier les droits du dossier, on utilise : `sudo chmod 770 /home/partage_fichier`
  * `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
  * `chmod` : pour modifier les droits
  * `770` : pour donner les droits complets à l'utilisateur et au groupe propriétaire et aucun droit aux autres utilisateurs
 
<img width="652" height="171" alt="chgrp_chmod" src="https://github.com/user-attachments/assets/5b8394b8-66ed-47ff-bf5e-f9ae7364029c" />

## 5. Créer un dernier utilisateur et vérifier qu’il n’a pas accès au dossier créé précédemment

Pour créer un utilisateur, on réutlise : `sudo useradd -m -c "Espion" espion`

Pour vérifier qu'il n'a pas accès au dossier on utlise : `sudo su espion`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `su` : "switch user", pour changer d'utilisateur dans le terminal
* `espion` : le nom de l'utilisateur que l'on veut utliser

Ensuite on essaye de parcourir le dossier avec : `cd /home/partage_fichier`

<img width="666" height="170" alt="verif_droits_dossier" src="https://github.com/user-attachments/assets/f789bb2e-3167-4c4b-ac46-8421917e0363" />

## 6. Bonus : faire en sorte qu’aucun mot de passe ne soit demandé pour lancer la commande rpm

Pour faire ceci, on doit modifier un fichier sudoers et on va utliser la commmande : `sudo visudo /etc/sudoers.d/rpm`
* `sudo` : permet d'éxécuter la commande en tant que super-utilisateur
* `visudo` : accéder à l'éditeur pour éditer les fichiers sudoers
* `/etc/sudoers.d/rpm` : chemin du fichier que l'on va modifier pour créer une règle pour la commande rpm(le fichier sera créé s'il n'existe pas)

<img width="666" height="96" alt="visudo" src="https://github.com/user-attachments/assets/9dabfeed-d768-4d21-bc00-052d04a02ae6" />

Pour plus de sécurité, on va donner les droits d'éxécuter rpm snas mot de passe à alice et bob seulement.

Dans le fichier, on va écrire : 
`
User_Alias ALICEBOB = alice,bob
ALICEBOB ALL=(ALL:ALL) /etc/rpm
`

* `User_Alias ALICEBOB = alice,bob` :
  * `User_Alias` : on crée un alias d'utilisateur
  * `ALICEBOB` : nom de l'alias
  * `= alice,bob` : liste des utlisatzeurs dans l'alias, séparés par une virgule
 
* `ALICEBOB ALL=(ALL:ALL) NOPASSWD: /etc/rpm` :
  * `ALICEBOB` : alias concerné par la règle (ou %groupe ou user)
  * `ALL=` : OÙ (sur quelle machine du domaine)
  * `(ALL:ALL)` : EN_TANT_QUE (utilisateur:groupe)
  * `NOPASSWD: /etc/rpm` : QUOI (ici, éxécuter rpm sans mot de passe)

<img width="653" height="124" alt="sudoers_rpm" src="https://github.com/user-attachments/assets/53197e1e-89e3-4260-948d-944ffbc77926" />

Avec `tail`, on vérifie le contenu de /etc/sudoers.d/rpm :

<img width="652" height="144" alt="verif_sudoers" src="https://github.com/user-attachments/assets/20ecdce8-69b9-49c2-95a9-86828b789b61" />

On vérifie que la règle marche en éxécutant `rpm -qa` pour lister tout les paquets présents sur le système. Pas besoin du mot de passe ou de l'éxecuter en sudo.

<img width="633" height="366" alt="exec_rpm" src="https://github.com/user-attachments/assets/96a354de-3b5f-43e6-96b8-bbb04f7f2275" />
