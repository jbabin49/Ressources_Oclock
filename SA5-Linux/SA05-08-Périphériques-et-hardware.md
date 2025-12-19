<h1 align=center>Périphériques et hardware</h1>

Comprendre et surveiller le matériel sous Linux.

---

# Surveiller les performances
- `top`, `htop` : charge CPU, RAM, processus en temps réel
- `vmstat 1`, `iostat -x 1` (pkg sysstat) : vue CPU/mémoire/E/S
- `free -h` : mémoire utilisée, cache, swap
- `df -h`, `lsblk` : occupation et topologie des disques
- `sar -u 1 5` : historique/échantillonnage (nécessite sysstat)

Démos en VM : lancer `stress-ng` ou compiler un projet et observer CPU/RAM/E/S.

---

# Gestion des processus
- `ps aux | grep nginx` : lister
- `pgrep nginx` / `pkill nginx` : trouver/terminer par nom
- `kill -TERM <pid>` / `kill -KILL <pid>` : signaux
- `nice -n 5 cmd` / `renice +5 <pid>` : priorité CPU
- `systemctl status <service>` : services gérés par systemd

---

# lspci, lsusb, dmesg
- `lspci -v` : périphériques PCI (carte réseau, GPU…)
- `lsusb -v` : périphériques USB (clés, webcams…)
- `dmesg | tail -n 50` : messages du noyau (détections, erreurs)
- `dmesg -w` : suivre en direct un branchement USB/PCI

Démos : suivre `dmesg -w` pendant un redémarrage de service ou l'ajout d'une interface réseau virtuelle (NAT/bridged), vérifier `lspci`/`lsusb` listent les contrôleurs virtio.

---

# Modules du noyau : lsmod, insmod, modprobe
- `lsmod` : modules chargés + utilisation mémoire
- `modinfo <module>` : infos (version, licence, options)
- `sudo modprobe <module>` : charge avec dépendances
- `sudo modprobe -r <module>` : décharge
- `sudo insmod fichier.ko` : insère un module local (sans dépendances)

Démos : (dé)charger un module présent (`virtio_net`, `loop`), observer `dmesg` lors du `modprobe`.

---

# Le dossier /dev
- interface des périphériques sous forme de fichiers spéciaux
- `ls -l /dev/sd* /dev/nvme*` : disques détectés
- `ls -l /dev/tty*` : terminaux/ports série
- `udev` gère la création dynamique (règles dans `/etc/udev/rules.d/`)
- accès contrôlé par permissions/groupes (`disk`, `tty`, `video` …)

Démos : créer un disque loop pour simuler un périphérique :
```bash
sudo dd if=/dev/zero of=/tmp/disk.img bs=1M count=10
sudo losetup -fP /tmp/disk.img   # crée /dev/loopX
ls -l /dev/loop*
sudo losetup -d /dev/loopX
```

---
