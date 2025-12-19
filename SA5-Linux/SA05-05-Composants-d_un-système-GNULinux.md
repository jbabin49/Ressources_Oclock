<h1 align=center>Composants d'un système GNU/Linux</h1>

Présentation complète des briques principales qui composent un système GNU/Linux.

---

# Principaux composants
Un système GNU/Linux est construit en assemblant plusieurs briques. Voici les briques principales :
- Shell
- Gestionnaire de paquets
- Chargeur d’amorçage
- init / gestionnaire de services
- Éditeur de texte
- Serveur graphique
- Pilotes de périphériques
- Gestionnaire d’affichage
- Environnement de bureau
- Gestionnaire de fenêtres
- Bibliothèques d’interface graphique
- Explorateur de fichiers
- Outil de configuration réseau
- Serveur & sous-système audio

---

# Shell
## Thompson shell & Bourne shell
Le premier shell est le Thomson shell, créé en 1971 pour la première version d'Unix par Ken Thompson.
Il est remplacé par le Bourne shell, créé en 1977 par Stephen Bourne pour la version 7 d'Unix. Il est resté le shell par défaut des systèmes Unix depuis cette époque-là. Ce shell est souvent abrégé bsh et même sh dans de nombreuses versions d'Unix.
Le Bourne shell a apporté la notion de pipes (redirection de la sortie d'une commande sur l'entrée d'une autre avec `|`), et a inspiré la plupart des shells plus modernes/récents.

## Bash
En 1988, Brian Fox créé le Bourne-Again SHell (bash), pour la Free Software Foundation dans le cadre du projet GNU.
Il est "compatible" avec le Bourne shell (reprend la plupart de ses fonctionnalités), dont il se veut une implémentation libre.
C'est le shell par défaut sur la plupart des systèmes libres basés sur Unix, dont la plupart des distributions GNU/Linux, et également sur MacOS jusqu'en 2019. C'est également le shell utilisé par WSL sous Windows.

## zsh
En 1990, Paul Falstad publie la première version du Z shell, abrégé zsh. Il reprend les fonctions les plus pratiques d'autres shells comme ksh et tcsh. Depuis 2019, il remplace même bash par défaut sur MacOS.

## Autres shells notables
- csh : C shell, syntaxe proche du langage C
- tcsh : TENEX C shell, shell par défaut sur plusieurs versions de BSD
- ksh : Korn shell, compatible Bourne shell, par défaut sur OpenBSD
- fish : Friendly Interactive shell, convivial et simple d'utilisation

## Quel shell sur ma distro ?
Pour connaître la liste des shells installés :
`cat /etc/shells`
Pour connaître le shell utilisé par défaut par votre utilisateur :
`cat /etc/passwd | grep <utilisateur>`
Pour connaître le shell actif à un instant t :
`echo $SHELL`

## Scripts shell
Pour automatiser l'exécution de plusieurs tâches, on peut créer des scripts shell.
Exemple de script basique :
```bash
#!/bin/bash
echo "Bienvenue dans mon super script !"
echo "Vous vous appelez $USER et vous utilisez le shell $SHELL."
echo "Date et heure du système : $(date)"
mkdir ~/temporaire
touch ~/temporaire/hello.txt
echo "Coucou !" > ~/temporaire/hello.txt
```
Pour lancer ce script :
`./demo-script.sh`
Si erreur de permission :
`chmod u+x demo-script.sh`
Vérifiez le contenu créé :
`cat ~/temporaire/hello.txt`

La plupart des scripts sont conçus pour bash ou le Bourne shell originel. Ils permettent d'utiliser boucles, conditions, opérateurs booléens, etc.
Les scripts bash doivent débuter par la ligne `#!/bin/bash` (shebang).

---

# Gestionnaire de paquets
Un gestionnaire de paquets automatise l'installation, la désinstallation et la mise à jour d'un programme/application sur un système informatique. Il gère aussi les dépendances.
Exemples : dpkg, RPM, Pacman, ports, homebrew, Microsoft Store, Flatpak, snap.
On peut aussi installer des logiciels "à la main" (AppImage, Java, compilation depuis le code source).

---

# Chargeur d'amorçage
Le chargeur d'amorçage (bootloader) est le premier logiciel lancé au démarrage d'une machine. Il permet de démarrer un ou plusieurs systèmes d'exploitation.
## BIOS vs. UEFI
BIOS lit le MBR, UEFI lit la GPT. UEFI est le standard actuel.
## Chargeurs d'amorçage populaires
- GRUB
- rEFInd
- systemd-boot

---

# init et gestion des services
`init` est le premier programme à démarrer après le chargeur d'amorçage (PID 1). Aujourd'hui, la plupart des distributions GNU/Linux utilisent `systemd`.
## Gestion des services avec systemd
Quelques commandes :
- `systemctl --type=service` : lister les services
- `systemctl start nom_service` : démarrer
- `systemctl stop nom_service` : stopper
- `systemctl status nom_service` : infos
- `systemctl enable nom_service` : activer au boot

---

# Éditeur de texte
Éditeurs populaires :
- nano
- vi / vim / neovim
- emacs
La plupart des éditeurs graphiques sont aussi disponibles sur Linux.

---

# Serveur graphique
## X Window System (X11)
Protocole client/serveur pour interfaces graphiques. Implémentation principale : X.Org.
## Wayland
Alternative moderne à X11, adoption encore timide.

---

# Pilotes de périphériques
Programme permettant d'accéder aux ressources matérielles. Les pilotes sont chargés dynamiquement sous forme de modules du noyau.

---

# Gestionnaire d'affichage
Display manager (login manager) : logiciel pour se connecter avec nom d'utilisateur et mot de passe. Exemples : GDM, LightDM, SDDM.

---

# Environnement de bureau
Desktop Environment (DE) : ensemble de programmes pour utiliser un ordinateur via une interface graphique. Exemples :
- Gnome
- KDE Plasma
- XFCE
- LXDE
- LXQt
- Mate
- Cinnamon
- Budgie

---

# Gestionnaire de fenêtre
Window Manager (WM) : gère le placement et le comportement des fenêtres. Exemples : Compiz, i3, dwm, Awesome, Fluxbox, Window Maker.

---

# Bibliothèque d'interface graphique
GTK ou Qt

---

# Explorateur de fichiers
GUI : dolphin, konqueror, krusader, nautilus, thunar, nemo
CLI : ranger, midnight commander

---

# Outil de configuration réseau
Exemples : netplan (Ubuntu), doc arch

---

# Serveur & sous-système audio
Exemple : doc arch

---
