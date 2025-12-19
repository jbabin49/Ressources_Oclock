<h1 align=center>Journaux du système</h1>

Comprendre rapidement où se trouvent les logs et comment les lire sous GNU/Linux.

---

# Où arrivent les journaux ?
- distributions systemd : `systemd-journald` centralise, écrit en binaire
- compatibilité syslog : `rsyslog` ou `syslog-ng` peut rediriger vers `/var/log/*.log`
- services : `systemd` capture stdout/stderr et les envoie au journal
- répertoires classiques : `/var/log/syslog`, `/var/log/auth.log`, `/var/log/messages`, `/var/log/dmesg`

---

# Lire les logs (fichiers texte)
- `sudo tail -f /var/log/syslog` ou `/var/log/messages`
- `sudo tail -f /var/log/auth.log` : authentification
- `dmesg | less` : messages noyau, matériels détectés au boot
- `less /var/log/apt/history.log`, `/var/log/secure` (RHEL)

---

# Lire les logs (journalctl)
Commande unique pour consulter le journal systemd :
```bash
journalctl -xe            # dernières entrées avec détails
journalctl -f             # suivre en temps réel
journalctl -u ssh         # unité systemd (service)
journalctl -k             # messages noyau
journalctl --since "10 min ago"
journalctl _PID=1234      # filtrer par PID
```
Options utiles : `-b` (boot courant), `-p err` (niveau), `--output cat` (format simple)

---

# Rotation et taille
- fichiers texte : gérés par `logrotate` (conf `/etc/logrotate.conf`, `logrotate.d/*`)
  - compression, rétention, fréquence
- `journald` :
  - persistance : `/var/log/journal` (sinon en mémoire sous `/run/log/journal`)
  - limites : `SystemMaxUse=`, `RuntimeMaxUse=` dans `/etc/systemd/journald.conf`
  - `journalctl --disk-usage` pour voir la taille, `--vacuum-size=500M` pour purger

---

# Bonnes pratiques dépannage
- identifier le service (`systemctl status <service>`, puis `journalctl -u <service>`)
- capturer le moment de l’incident (`--since "5 minutes ago"`)
- filtrer par gravité (`-p warning` ou `-p err`)
- surveiller en live pendant une action (`journalctl -fu <service>`)
- vérifier l’espace disque (`df -h /var/log`) avant de soupçonner un service

---
