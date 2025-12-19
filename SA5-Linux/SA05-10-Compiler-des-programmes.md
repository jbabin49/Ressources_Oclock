<h1 align=center>Compiler des programmes</h1>

Installer depuis le code source quand un paquet n'existe pas (ou trop ancien).

---

# Pourquoi compiler ?
- obtenir une version plus récente qu'en dépôt
- activer/désactiver des options spécifiques (modules, drivers)
- tester/patcher un logiciel avant packaging

**Attention : préférer les paquets officiels quand ils existent (mise à jour et dépendances gérées).**

---

# Prérequis
- outils de base : compilateur, linker, make, headers
  - Debian/Ubuntu : `sudo apt install build-essential`
  - RHEL/Fedora : `sudo dnf groupinstall "Development Tools"`
  - Arch : `sudo pacman -S base-devel`
- dépendances spécifiques : `-dev` / `-devel` des bibliothèques utilisées
- espace disque et CPU (compilation peut être longue)

---

# Workflow classique (tar.gz)
```bash
tar xf logiciel-1.2.3.tar.gz
cd logiciel-1.2.3
./configure --prefix=/usr/local    # détecte l'environnement, options
make                               # compile
sudo make install                  # installe (binaire + man + conf)
```
Commandes utiles :
- `./configure --help` : voir les options disponibles
- `make -j$(nproc)` : paralléliser
- `make check` ou `make test` : tests fournis
- `sudo make uninstall` (si prévu) pour retirer

---

# Exemple rapide : recompiler un outil existant (htop)
Prérequis : ncurses headers (`libncursesw5-dev` ou `ncurses-devel`).
```bash
wget https://github.com/htop-dev/htop/archive/refs/tags/3.3.0.tar.gz
tar xf 3.3.0.tar.gz
cd htop-3.3.0
./autogen.sh        # déjà fait dans certaines archives, sinon nécessaire
./configure --prefix=/usr/local
make -j$(nproc)
sudo make install
htop --version
```

---

# Makefile : juste pour lire un build
- beaucoup de projets fournissent un `Makefile`
- commandes utiles : `make`, `make install`, `make clean`
- variables courantes : `PREFIX=/usr/local`, `DESTDIR=/tmp/pkg` (pour emballer)
- pas besoin d’écrire du code, mais savoir lire les cibles principales aide à dépanner

---

# Bonnes pratiques
- installer dans `/usr/local` ou via `checkinstall` plutôt que `/usr` pour ne pas gêler les paquets
- documenter les options utilisées (`./configure --prefix=... --enable-...`)
- nettoyer le répertoire de build (`make clean`) avant de regénérer
- garder les sources et la commande d'installation pour reproduire ou désinstaller
- sur une VM : créer un snapshot avant une grosse compilation

---
