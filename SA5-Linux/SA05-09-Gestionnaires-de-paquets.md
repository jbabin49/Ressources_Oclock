<h1 align=center>Gestionnaires de paquets</h1>

Installer, mettre à jour et supprimer des logiciels proprement sur une distribution GNU/Linux.

---

# Rôle d'un gestionnaire de paquets
- archive contenant binaires, dépendances, scripts de post-install, métadonnées
- téléchargé depuis des dépôts signés (sources officielles ou internes)
- installé avec vérification d'intégrité et résolution des dépendances
- permet les mises à jour cohérentes du système (sécurité, correctifs)

---

# apt / dpkg (Debian & dérivés)
- `dpkg` : outil bas niveau pour manipuler des `.deb` locaux
- `apt` / `apt-get` : résout dépendances, parle aux dépôts listés dans `/etc/apt/sources.list` et `/etc/apt/sources.list.d/*.list`
- cache téléchargements dans `/var/cache/apt/archives`

Commandes clés :
```bash
sudo apt update                # rafraîchir la liste des paquets
sudo apt upgrade               # mettre à jour les paquets installés
sudo apt install htop          # installer (résolution auto des dépendances)
sudo apt remove htop           # désinstaller
sudo apt search docker         # rechercher
sudo apt show openssh-server   # infos détaillées
sudo dpkg -i fichier.deb       # installer un .deb local
sudo dpkg -l | head            # lister les paquets installés
```

---

# pacman (Arch & dérivés)
- binaire unique qui gère synchro, install, cache dans `/var/cache/pacman/pkg`
- configuration : `/etc/pacman.conf` et listes de miroirs dans `/etc/pacman.d/mirrorlist`
- pas d'AUR par défaut : nécessiterait un helper (ex. `yay`) non officiel

Commandes clés :
```bash
sudo pacman -Syu          # synchronise la base + met à jour tout le système
sudo pacman -S htop       # installe un paquet
sudo pacman -Ss nginx     # recherche dans les dépôts
sudo pacman -Qi htop      # infos sur un paquet installé
sudo pacman -Ql htop      # fichiers installés par le paquet
sudo pacman -Rns htop     # supprime + dépendances orphelines + fichiers conf
```

---

# rpm + dnf (Red Hat & dérivés)
- `rpm` : outil bas niveau pour les `.rpm` (pas de résolution de dépendances)
- `dnf` (ou `yum` sur anciennes versions) : gère dépôts, transactions, dépendances
- configuration des dépôts : fichiers `.repo` dans `/etc/yum.repos.d/`

Commandes clés :
```bash
sudo dnf check-update       # liste les mises à jour
sudo dnf upgrade            # met à jour
sudo dnf install htop       # installe depuis les dépôts
sudo dnf remove htop        # désinstalle
sudo dnf search nginx       # recherche
sudo dnf info openssh       # infos
sudo rpm -ivh fichier.rpm   # installer un .rpm local
rpm -qa | head              # lister les paquets installés
rpm -ql bash                # fichiers installés par un paquet
```

---

# Comparatif rapide
| Distribution         | Outil haut niveau | Outil bas niveau | Fichiers de dépôts                |
|---------------------|-------------------|------------------|-----------------------------------|
| Debian / Ubuntu     | apt               | dpkg             | /etc/apt/sources.list(.d)         |
| Arch / Manjaro      | pacman            | pacman           | /etc/pacman.conf, pacman.d        |
| RHEL / CentOS / Fedora | dnf (yum)      | rpm              | /etc/yum.repos.d/*.repo           |

Conseil : utilisez toujours l'outil haut niveau pour bénéficier de la résolution des dépendances et des transactions sûres.

---

# Démos à faire en TP
1. Lister les dépôts configurés (`cat /etc/apt/sources.list`, `pacman -Syy`, `dnf repolist`)
2. Installer puis retirer un paquet simple (`htop`, `curl`, `tree`)
3. Examiner les fichiers installés par un paquet (`dpkg -L`, `pacman -Ql`, `rpm -ql`)
4. Observer le cache et nettoyer (`sudo apt clean`, `sudo pacman -Sc`, `sudo dnf clean all`)
5. Mettre à jour une machine de test et surveiller les journaux (`/var/log/apt/history.log`, `journalctl -u pacman-init`, `/var/log/dnf.log`)

---
