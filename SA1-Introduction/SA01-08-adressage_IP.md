<h1 align=center>Adressage IP</h1>

Introduction à l'adressage IP et aux masques de sous-réseaux dans les réseaux informatiques.

---

# Qu'est-ce qu'une adresse ?

Pour communiquer sur un réseau, chaque machine a besoin d'une adresse, appelée adresse IP.

- Comparable à une adresse postale pour le courrier
- Utilisée sur tous les réseaux TCP/IP

---

# Versions du protocole IP

- **IPv4** : plus ancien, environ 4,3 milliards d'adresses possibles
- **IPv6** : plus moderne, nombre d'adresses quasi illimité

*Ce cours se concentre sur IPv4.*

---

# Adresse IPv4

Une adresse IPv4 est composée de 4 nombres entre 0 et 255, séparés par des points.

Exemples :
- 192.168.1.1
- 10.0.42.37
- 92.135.27.9
- 8.8.8.8

## Attribution

- Sur un réseau domestique, l'adresse est attribuée par la box via le protocole DHCP.

---

# Structure d'une adresse IPv4

- 4 octets (1 octet = 8 bits)
- Soit 32 bits au total

**Exemple binaire :**
- 192.168.1.1 = 11000000.10101000.00000001.00000001

**Remarque :** Chaque bloc ne peut dépasser 255 (11111111 en binaire).

---

# Machine et réseau

Dans une adresse IPv4, une partie identifie la machine, l'autre le réseau.

- C'est le masque de sous-réseau qui détermine cette séparation.

---

# Masque de sous-réseau

- Ressemble à une adresse IP : 4 nombres séparés par des points
- Exemples :
  - 255.255.255.0
  - 255.255.0.0
  - 255.255.192.0
  - 255.255.255.128

**Utilité :**
- Permet de distinguer la partie réseau de la partie machine dans une adresse IP

---

# Conclusion

Comprendre l'adressage IP et les masques de sous-réseau est fondamental pour configurer et dépanner les réseaux informatiques.
