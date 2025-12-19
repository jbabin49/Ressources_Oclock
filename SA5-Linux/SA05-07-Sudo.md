<h1 align=center>Sudo</h1>

Monter en privilèges sans rester root sur GNU/Linux.

---

# Pourquoi utiliser sudo ?
- applique le principe du moindre privilège : on reste utilisateur normal, on élève ponctuellement
- journalise les commandes et les erreurs (audit)
- contrôle fin : qui peut faire quoi, sur quelle machine, avec quel mot de passe
- évite les sessions root permanentes et les erreurs irréversibles

---

# Fonctionnement
- `sudo` vérifie l'utilisateur et son mot de passe
- lit `/etc/sudoers` et les fichiers du dossier `/etc/sudoers.d/`
- valide la commande demandée selon les règles
- passe l'environnement et le contexte précisés dans la config

---

# /etc/sudoers
Fichier principal de configuration. Ne l'éditez JAMAIS avec un éditeur classique : utilisez `visudo`.

Structure minimaliste :
```
User_Alias ADMINS = baptiste,jean
Defaults env_reset
Defaults secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
root    ALL=(ALL:ALL) ALL
%sudo   ALL=(ALL:ALL) ALL
ADMINS  ALL=(root) /usr/bin/systemctl restart nginx
```

---

# Clés de lecture
- alias : regrouper utilisateurs/commandes si besoin
- `Defaults` : options globales (environnement, logs…)
- règles : qui / depuis où / en tant que qui / quelles commandes

---

# Règle standard
```
%sudo ALL=(ALL:ALL) ALL
```
- `%sudo` : tous les membres du groupe sudo
- `ALL` : depuis n'importe quelle machine
- `(ALL:ALL)` : exécuter en tant que n'importe quel utilisateur et groupe
- `ALL` : toute commande

---

# Règle ciblée
```
baptiste ALL=(www-data) /usr/bin/systemctl restart nginx
```
- baptiste peut relancer nginx en se faisant passer pour `www-data`
- reste bloqué pour le reste

`NOPASSWD:` peut supprimer la demande de mot de passe, à utiliser avec parcimonie.

---

# visudo
L'outil recommandé pour modifier la configuration.
```bash
sudo visudo
sudo visudo -f /etc/sudoers.d/web
```
- verrouille le fichier pendant l'édition
- vérifie la syntaxe avant d'enregistrer
- empêche de casser l'accès sudo par une erreur

Préférez créer des fichiers dans `/etc/sudoers.d/` plutôt que d'éditer directement `/etc/sudoers`.

---

# Démos sur VM
1. Vérifier ses droits :
```bash
id
groups
sudo -l
```
2. Tester des commandes simples :
```bash
sudo whoami
sudo tail -n 5 /var/log/syslog   # ou /var/log/messages
```
3. Ajouter un utilisateur au groupe sudo :
```bash
sudo usermod -aG sudo jean
```
Déconnexion/reconnexion pour appliquer.

4. Créer une règle ciblée :
```bash
sudo visudo -f /etc/sudoers.d/web
# jean ALL=(www-data) /usr/bin/systemctl restart nginx
```
5. Tester l'accès :
```bash
sudo systemctl restart nginx   # en tant que jean
sudo -l                        # vérifier les droits
```

---

# Journalisation
- Debian/Ubuntu : `tail -f /var/log/auth.log | grep sudo`
- RHEL/CentOS : `journalctl -f -t sudo`
- les logs montrent l'utilisateur, la commande, le résultat (success/denied)

---

# Bonnes pratiques
- éviter `sudo su -` ou `sudo -s` prolongés, préférer des commandes ciblées
- limiter les règles `ALL` et les `NOPASSWD`
- utiliser `sudoedit` pour éditer des fichiers de config
- ranger vos règles dans `/etc/sudoers.d/` avec un nom explicite
- tester avec `sudo -l` et surveiller les logs après modification

---

# Points clés à retenir
- `sudo` permet une élévation contrôlée et tracée des privilèges
- `/etc/sudoers` définit qui peut faire quoi et comment
- `visudo` protège la configuration en vérifiant la syntaxe
- privilégiez des règles minimales, testées, et loggez vos usages

---
