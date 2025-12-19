<h1 align=center>Bits, octets, numération</h1>

Introduction aux bases de la numération binaire, unités de mesure et multiples en informatique.

---

# Bit

Le bit est l'abréviation de "binary digit" (chiffre binaire).

- Un bit ne peut prendre que deux valeurs : 0 ou 1
- Les systèmes numériques traitent des informations codées en bits
- **Symbole/unité :** `b` ou `bit`

---

# Octet

1 octet = 8 bits

- **Attention :** octet se dit Byte en anglais
- Ne pas confondre bit et Byte !
- **Symbole/unité :** `o` en français, `B` en anglais (attention à la majuscule)

---

# Multiples

Historiquement, les préfixes kilo, méga, giga, etc. représentaient une puissance de 2 en informatique.

- Exemple : 1 kilobit = 1 024 bits (2^10)
- Dans le système métrique : 1 kilomètre = 1 000 mètres (10^3)

**Problème :** Certains fabricants utilisaient la logique du système métrique (10^3, 10^6, 10^9), d'autres la logique informatique (2^10, 2^20, 2^30).

- Parfois, 1 kilobit valait 1 000 bits, parfois 1 024 bits

Pour éviter ce problème, une nouvelle norme a été créée en 1998 pour distinguer les multiples binaires.

- Préfixes binaires : kibi, mébi, gibi, etc. (2^10, 2^20, 2^30)

---

# Tableaux des multiples

## Multiples des bits (SI)

| Unité    | Notation      | Valeur                  |
|----------|---------------|-------------------------|
| bit      | bit ou b      | 1 bit                   |
| kilobit  | kbit ou kb    | 10^3 bits = 1 000 bits  |
| mégabit  | Mbit ou Mb    | 10^6 bits = 1 000 000   |
| gigabit  | Gbit ou Gb    | 10^9 bits = 1 000 000 000 |
| térabit  | Tbit ou Tb    | 10^12 bits = 1 000 000 000 000 |
| pétabit  | Pbit          | 10^15 bits = 1 000 000 000 000 000 |

## Multiples binaires (IEC)

| Unité     | Notation      | Valeur                  |
|-----------|---------------|-------------------------|
| kibibit   | Kibit         | 2^10 bits = 1 024 bits  |
| mebibit   | Mibit         | 2^20 bits = 1 048 576   |
| gibibit   | Gibit         | 2^30 bits = 1 073 741 824 |
| tebibit   | Tibit         | 2^40 bits = 1 099 511 627 776 |

---

# Conclusion

Bien comprendre la différence entre les unités et leurs multiples est essentiel pour éviter les confusions en informatique, notamment lors de l'achat ou de l'utilisation de matériel et de logiciels.
