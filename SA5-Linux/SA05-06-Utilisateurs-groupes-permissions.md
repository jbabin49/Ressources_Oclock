<h1 align=center>Utilisateurs, groupes et permissions</h1>

Manipuler les comptes et sécuriser l'accès au système GNU/Linux.

---

# Gestion des utilisateurs et groupes
Dans ces slides, on va voir :
- la gestion des utilisateurs (`useradd`, `usermod`, `userdel`)
- la gestion des groupes (`groupadd`, `usermod -aG`, `gpasswd --delete`)
- les fichiers `/etc/passwd`, `/etc/shadow`, `/etc/group`
- les permissions Unix, `chown` et `chmod`

---

# Comptes utilisateurs
Un utilisateur identifie une personne ou un service sur la machine. Il possède :
- un identifiant numérique (UID)
- un groupe primaire (GID)
- un dossier personnel et un shell par défaut
- des permissions distinctes de celles des autres utilisateurs

---

# /etc/passwd
Le fichier `/etc/passwd` recense les comptes. Chaque ligne ressemble à :
`baptiste:x:1000:1000:Baptiste:/home/baptiste:/bin/bash`
- `baptiste` : nom de compte
- `x` : mot de passe chiffré stocké dans `/etc/shadow`
- `1000` : UID
- `1000` : GID primaire
- `Baptiste` : commentaire (gecos)
- `/home/baptiste` : dossier personnel
- `/bin/bash` : shell par défaut

---

# /etc/shadow
Le fichier `/etc/shadow` contient les mots de passe chiffrés et les règles d'expiration.
`baptiste:$y$j9T$...:19493:0:99999:7:::`
- seul `root` (ou un superuser via `sudo`) peut le lire
- on y trouve les hachages, dates de changement, délais d'expiration

---

# Créer, modifier, supprimer un utilisateur
Ajouter un utilisateur : `useradd`
```bash
sudo useradd -m -s /bin/bash -c "Jean Dupont" jean
sudo useradd -m -u 1050 -g 100 jean-tech
```
- `-m` : crée le dossier personnel
- `-s` : shell par défaut
- `-c` : commentaire (gecos)
- `-u` / `-g` : UID / GID imposés

Pensez à définir un mot de passe ensuite : `sudo passwd jean`.

Modifier un utilisateur : `usermod`
```bash
sudo usermod -s /bin/zsh jean
sudo usermod -d /home/jdupont -m jean
sudo usermod -l jdupont jean
sudo usermod -L jean
sudo usermod -U jean
```
- `-d` + `-m` : change le home et déplace le contenu
- `-l` : renomme le login
- `-L` / `-U` : verrouille/déverrouille le mot de passe dans `/etc/shadow`

Supprimer un utilisateur : `userdel`
```bash
sudo userdel jean
sudo userdel -r jean
```
- `-r` : supprime le home et la boîte mail locale (`/var/mail/user`)
- vérifiez avant de supprimer : aucun processus en cours, pas de fichiers critiques

---

# Groupes
Un groupe rassemble plusieurs utilisateurs et simplifie l'attribution des droits.
- chaque utilisateur a un groupe primaire (GID)
- il peut appartenir à des groupes secondaires
- `root` possède des droits qui dépassent la logique de groupe

---

# /etc/group
Le fichier `/etc/group` liste les groupes :
`sudo:x:27:baptiste,jean`
- `sudo` : nom du groupe
- `x` : mot de passe du groupe
- `27` : GID
- `baptiste,jean` : membres secondaires du groupe

Créer / supprimer un groupe :
```bash
sudo groupadd reseau
sudo groupadd -g 1052 devops
sudo groupdel reseau
```

Ajouter / retirer un utilisateur d'un groupe :
```bash
sudo usermod -aG sudo,reseau jean
sudo gpasswd --delete jean reseau
sudo usermod -g devops jean
```

---

# Permissions Unix
Chaque fichier ou dossier possède 3 blocs de droits :
- u (user) : propriétaire
- g (group) : groupe propriétaire
- o (others) : tous les autres

Lire les droits :
```bash
ls -l
```
Affiche les permissions :
- premier caractère : type (`-` fichier, `d` dossier, `l` lien…)
- bloc `rwx` pour l'utilisateur, le groupe, puis les autres

Signification des bits :
- `r` (read) : lire un fichier / lister un dossier
- `w` (write) : modifier un fichier / créer-supprimer dans un dossier
- `x` (execute) : exécuter un binaire / traverser un dossier

Sur un dossier, `x` est indispensable pour parcourir son contenu, même si `r` est présent.

---

# Changer propriétaire : chown
```bash
sudo chown jean:devops rapport.txt
sudo chown :reseau projets
sudo chown -R www-data:www-data /var/www/html
```
- `user:group` permet de modifier les deux en une fois
- `-R` descend dans l'arborescence

---

# Changer les droits : chmod
Deux syntaxes possibles : symbolique ou octale.

Syntaxe symbolique :
```bash
chmod u+x script.sh
chmod o-w rapport.txt
chmod o=g partage/
```
- `u` propriétaire, `g` groupe, `o` autres, `a` tous
- `+` ajoute, `-` retire, `=` impose exactement

Syntaxe octale :
```bash
chmod 644 rapport.txt
chmod 775 script.sh
chmod 700 secrets/
```
Sur un dossier partagé, pensez au `x` pour permettre la traversée.

---
