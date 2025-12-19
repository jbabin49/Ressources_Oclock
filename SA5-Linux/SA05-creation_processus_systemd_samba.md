# Migration Samba vers systemd

## 1. Créer le service systemd

```bash
sudo nano /etc/systemd/system/samba.service
```

Contenu du fichier :

```ini
[Unit]
# commentaire du service
Description=Samba AD Daemon
Documentation=man:samba(8)
# démarrer le service apres les cibles network, systeme de fichier, resolution de domaine
After=network.target remote-fs.target nss-lookup.target

[Service]
# important different type de service, lire le man
Type=forking
# la commande qui demarre le service
ExecStart=/usr/local/samba/sbin/samba -D
# la commande qui reload le service
ExecReload=/bin/kill -HUP $MAINPID
# la commande qui trouve le PID root pour stopper le service
PIDFile=/usr/local/samba/var/run/samba.pid
# nombre de fichiers que le service peut manipuler
LimitNOFILE=16384

[Install]
# la cible multi utilisateur démarre le service samba
WantedBy=multi-user.target
```

Recharger systemd :

```bash
sudo systemctl daemon-reload
sudo systemctl enable samba
```

## 2. Tuer l'ancien processus et démarrer avec systemd

```bash
# Trouver le PID
ps aux | grep "/usr/local/samba/sbin/samba"

# Tuer le processus (remplacer XXXX par le PID)
sudo kill XXXX

# Ou en une ligne
sudo kill $(pgrep -f "/usr/local/samba/sbin/samba")

# Démarrer avec systemd
sudo systemctl start samba

# Vérifier
sudo systemctl status samba
```

## Commandes utiles

```bash
sudo systemctl start samba      # Démarrer
sudo systemctl stop samba       # Arrêter
sudo systemctl restart samba    # Redémarrer
sudo systemctl status samba     # Statut
sudo systemctl cat samba # afficher le service
sudo systemlctl edit --full samba # editer le fichier systemd pour en faire une copie qui sera conservé
```
