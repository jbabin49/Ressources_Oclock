Introduction au serveur DHCP
d'adresses IP

<h1 align=center>Introduction au serveur DHCP sur Windows Server 2022</h1>

Service réseau pour l'attribution automatique d'adresses IP et la gestion centralisée des paramètres réseau.

---

# Présentation générale

Le serveur DHCP (Dynamic Host Configuration Protocol) attribue automatiquement des adresses IP aux appareils d'un réseau. Il simplifie la configuration et la gestion des appareils, évitant la configuration manuelle de chaque adresse IP.

Le serveur DHCP gère aussi :
- le masque de sous-réseau
- la passerelle par défaut
- les serveurs DNS

---

# Avantages d'utiliser le serveur DHCP

- Automatisation de l'attribution des adresses IP
- Gestion centralisée des adresses IP et des paramètres réseau
- Économies de temps et de ressources pour l'administration
- Amélioration de la sécurité (limitation des adresses IP, filtrage des paquets)

---

# Étapes de configuration du serveur DHCP

Installation du rôle serveur DHCP, configuration des plages d'adresses, options réseau et sécurité.

Installez le rôle serveur DHCP à partir du
gestionnaire de serveur.

2

Configuration de la portée DHCP
Créez une portée DHCP et définissez la plage

Configuration des options DHCP
Configurez les options DHCP telles que les
serveurs DNS et les serveurs WINS.

3
4

d'adresses IP.

Activer le serveur DHCP
Activez le serveur DHCP pour qu'il commence
à attribuer des adresses IP.

La configuration du serveur DHCP est une procédure relativement simple qui peut être effectuée en quelques étapes.
Commencez par installer le rôle serveur DHCP sur votre serveur Windows Server 2022. Ensuite, créez une portée DHCP
et définissez la plage d'adresses IP que vous souhaitez attribuer aux clients. Vous pouvez également configurer des
options DHCP, telles que les serveurs DNS et les serveurs WINS, pour fournir des informations supplémentaires aux
clients. Une fois que vous avez configuré le serveur DHCP, vous pouvez l'activer pour qu'il commence à attribuer des
adresses IP aux clients.

Définition des plages d'adresses IP
La configuration des plages d'adresses IP est cruciale pour le bon fonctionnement du serveur DHCP. Elle permet
d'attribuer des adresses IP aux clients du réseau de manière ordonnée et sécurisée.

—

—

Définition de la plage

Sous-réseaux

Déterminer les adresses IP disponibles pour les clients.

Diviser le réseau en plusieurs sous-réseaux pour une
meilleure gestion.

—

—

Masque de sous-réseau

Porte d'entrée

Définir la taille du sous-réseau et l'adresse réseau.

Spécifier la passerelle par défaut pour les clients.

Le serveur DHCP doit être configuré avec une plage d'adresses IP statiques. Il est important de choisir une plage
d'adresses qui ne chevauche pas d'autres réseaux.

Configuration des options DHCP
Configuration de base

Configuration de la réservation

Définissez les paramètres essentiels tels que le délai

Créez des réservations pour affecter des adresses IP

de location, le nom de domaine, l'adresse IP du

statiques à des appareils spécifiques, assurant une

serveur et les serveurs DNS.

configuration stable et fiable.

1

2

Options DHCP avancées
Configurez des options spécifiques pour répondre
aux besoins de votre réseau, par exemple la
configuration de l'adresse IP du routeur par défaut ou
l'affectation automatique des paramètres WINS.

3

Gestion des baux DHCP
Durée du bail

1

Le serveur DHCP attribue une durée de bail aux clients, définissant la période pendant laquelle ils
peuvent utiliser l'adresse IP. La durée peut être configurée en fonction des besoins.

Renouvellement du bail

2

Avant l'expiration du bail, les clients peuvent le renouveler pour continuer à utiliser la même adresse IP.
Le serveur DHCP gère automatiquement les demandes de renouvellement.

Libération du bail

3

Lorsque les clients sont éteints ou quittent le réseau, le serveur DHCP libère l'adresse IP, la rendant
disponible pour d'autres appareils.

Réservation d'adresse

4

Pour des appareils spécifiques, comme les serveurs, il est possible de réserver une adresse IP fixe,
assurant une connectivité constante.

Surveillance et dépannage du serveur
DHCP
Surveillance des performances

1

Vérifiez la fiabilité du serveur DHCP en surveillant les événements système, les journaux d'erreurs et
l'utilisation des ressources.

Diagnostic des problèmes

2

Utilisez les outils de diagnostic intégrés à Windows Server 2022 pour identifier et résoudre les
problèmes liés aux allocations d'adresses IP, aux conflits d'adresses et à la configuration du serveur
DHCP.

Analyse des baux DHCP

3

Examinez les baux DHCP actifs et expirés pour détecter les problèmes de renouvellement ou de
libération d'adresses IP, et pour identifier les clients qui pourraient être en conflit avec la configuration
du serveur DHCP.

Configuration des alertes

4

Configurez des alertes pour recevoir des notifications en cas d'erreurs ou de problèmes critiques liés au
serveur DHCP, permettant une intervention rapide et une résolution des problèmes.

Intégration du serveur DHCP avec
d'autres services
Le serveur DHCP peut être intégré à d'autres services pour améliorer la gestion du réseau. Il s'agit notamment de
l'intégration avec Active Directory, DNS et le contrôle d'accès réseau.

—

—

—

Active Directory

DNS

Contrôle d'accès

Automatisation de la configuration
DHCP pour les ordinateurs joints au

Intégration des enregistrements DNS
pour les adresses IP attribuées.

Application de politiques de sécurité
basées sur l'adresse IP.

domaine.
L'intégration avec Active Directory permet d'automatiser la configuration DHCP pour les ordinateurs joints au domaine,
simplifiant ainsi la gestion des adresses IP. L'intégration avec DNS permet de lier les adresses IP aux noms de domaine,
facilitant la résolution des noms d'hôtes. Enfin, l'intégration avec le contrôle d'accès réseau permet d'appliquer des
politiques de sécurité basées sur l'adresse IP, renforçant la sécurité du réseau.

