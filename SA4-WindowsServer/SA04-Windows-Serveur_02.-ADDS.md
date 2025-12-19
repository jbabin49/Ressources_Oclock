Active Directory
Domain Services
(ADDS)
Décodé pas à pas 🔐🏛️

1

Introduction à LDAP
Lightweight Directory Access Protocol est un protocole standard
pour interroger et modifier des annuaires. Il fournit une manière
structurée d’accéder à des informations d’identités, de ressources et
de politiques.
Les annuaires sont optimisés pour la lecture. Ils stockent des entrées
hiérarchisées, indexées, et faciles à parcourir pour des opérations
fréquentes comme l’authentification.

2

LDAP repose sur un modèle de données simple : des entrées avec des
attributs.
Chaque entrée est identifiée par un Distinguished Name.
Les opérations centrales sont Bind, Search, Add, Modify et Delete.

3

LDAP sur Windows Server
Active Directory implémente LDAP comme interface d’annuaire.
ADDS expose un schéma LDAP et répond aux requêtes via le port
389/636, tout en intégrant Kerberos, NTLM et les GPO (on reparlera
de ces derniers plus tard).
Dans Windows, LDAP n’est pas l’authentification mais la porte
d’entrée vers les objets. L’authentification s’appuie principalement
sur Kerberos.

4

Historique de LDAP
Le protocole LDAP a été développé dans les années 1990 pour
simplifier l'accès aux annuaires électroniques. Depuis ses débuts, il a
considérablement évolué pour devenir un standard incontournable
dans la gestion des identités et des accès dans les organisations.

5

LDAP est largement utilisé dans de nombreux domaines, tels que les
entreprises, les établissements d'enseignement et les services
gouvernementaux. Il offre une méthode efficace de centralisation des
informations utilisateur et de gestion des autorisations, ce qui facilite
la collaboration et l'accès aux ressources.
De plus, LDAP est évolutif et peut s'intégrer à d'autres protocoles
pour offrir une solution complète de gestion des identités et des
accès.

6


10
Schéma LDAP
12
granulaire.

<h1 align=center>Active Directory Domain Services (ADDS)</h1>

Décodage pas à pas du service d'annuaire centralisé de Microsoft.

---

# Introduction à LDAP

LDAP (Lightweight Directory Access Protocol) est un protocole standard pour interroger et modifier des annuaires. Il permet d'accéder de façon structurée à des informations d'identités, de ressources et de politiques.

**Note** : Les annuaires sont optimisés pour la lecture, stockant des entrées hiérarchisées, indexées et faciles à parcourir pour l'authentification.

## Modèle de données LDAP
Chaque entrée LDAP possède des attributs et un Distinguished Name. Les opérations principales sont :
- Bind
- Search
- Add
- Modify
- Delete

---

# LDAP sur Windows Server

Active Directory implémente LDAP comme interface d'annuaire. ADDS expose un schéma LDAP et répond aux requêtes via les ports 389/636, tout en intégrant Kerberos, NTLM et les GPO.

**Important** : LDAP n'est pas l'authentification, mais la porte d'entrée vers les objets. L'authentification repose principalement sur Kerberos.

---

# Historique de LDAP

Développé dans les années 1990 pour simplifier l'accès aux annuaires électroniques, LDAP est devenu un standard incontournable pour la gestion des identités et des accès dans les organisations.

LDAP est utilisé dans de nombreux domaines (entreprises, enseignement, services gouvernementaux) pour centraliser les informations utilisateur et la gestion des autorisations.

**Point clé** : LDAP est évolutif et peut s'intégrer à d'autres protocoles pour une gestion complète des identités et des accès.

---

# Configuration de LDAP

Une configuration LDAP typique implique plusieurs étapes clés (création d'objets, définition d'attributs, application de politiques, etc.).

14

Création d’un domaine
Active Directory 🚀
La création commence par l’ajout du rôle ADDS, la promotion en
contrôleur de domaine, et la définition du nom DNS du domaine.
On choisit le niveau fonctionnel, on installe DNS si nécessaire, et on
prépare les sites et sous-réseaux pour une réplication efficace.
Un role ? C'est quoi ça ?

15

Roles de Windows Server 🏗
Les rôles de Windows Server sont des fonctionnalités spécifiques qui
peuvent être installées pour répondre à des besoins particuliers.
Chaque rôle a des responsabilités et des services associés.
Par exemple, le rôle ADDS permet de gérer les identités et les accès
dans un environnement Windows, tandis que le rôle DNS gère la
résolution des noms de domaine.
Ou encore le role DHCP qui attribue automatiquement des adresses
IP aux appareils sur le réseau.

16

Le Role : ADDS
Une fois le rôle ADDS installé, nous devons promouvoir le serveur en
contrôleur de domaine (DC). Cela implique la création d'un nouveau
domaine ou l'ajout à un domaine existant.
Le premier Domaine Contrôleur (DC) crée la base du domaine, la
partition de configuration et le catalogue global si sélectionné. Les
DC suivants rejoignent et répliquent. On défini également la Forêt.

17

C’est quoi une Forêt ? 🌲
La forêt est la limite de confiance et de schéma. Elle regroupe un ou
plusieurs domaines partageant un catalogue global, une
configuration commune, et un schéma unique.
Les forêts permettent l’isolation logique : administration, politiques
et identités restent contrôlées dans des frontières claires.

18

Forêt, Tree et Domain 🌳

🏷️

Un tree regroupe des domaines dans un espace de noms. Un domaine
est une unité d’administration, de sécurité et de réplication.
Les trusts automatiques existent entre domaines d’une même forêt.
Les trusts externes permettent l’interopérabilité entre forêts.

19

FORÊT : oclock (Schéma + Catalogue global)
│
├── ARBRE 1 : oclock.lan
│
│

├── Domaine racine : oclock.lan
│
├── Site : Paris (OC-PAR)

│
│
│

│
└── Site : Lyon (OC-LYN)
│
└── Domaine enfant : prod.oclock.lan

│
│

├── Site : Paris (OC-PAR)
└── Site : Lyon (OC-LYN)

│
└── ARBRE 2 : pandit.lan
├── Domaine racine : pandit.lan
│
│

├── Site : Bordeaux (PD-BDX)
└── Site : Toulouse (PD-TLS)

│

Attend, j'ai un arbre qui a le même nom que la Forêt... C'est pas un
peu confus ?
20

Oui, ça peut l’être ! Dans cet exemple, “oclock” est le nom de la forêt,
tandis que “oclock.lan” est le nom DNS du domaine racine dans cette
forêt. L’arbre est simplement la structure logique qui regroupe les
domaines partageant ce même espace de noms.
Donc, même si les noms se ressemblent, ils ne désignent pas la même
chose :
la forêt = l’ensemble,
le domaine racine = le point de départ de l’arbre,
et l’arbre = tout ce qui partage le même espace DNS.

21

Souvent, on choisit des noms proches pour simplifier la gestion, mais
attention : côté réseau et compatibilité, Active Directory ne s’appuie
pas uniquement sur le DNS…

22

C’est quoi NetBIOS ! 📛
Avant que le DNS ne soit généralisé, Windows utilisait NetBIOS pour
identifier les ordinateurs et les domaines sur le réseau local.
Chaque domaine Active Directory garde donc aussi un nom NetBIOS
court, souvent dérivé de son nom DNS, mais limité à 15 caractères (et
sans “.”).

23

Nom DNS du domaine

Nom NetBIOS associé

oclock.lan

OCLOCK

prod.oclock.lan

PROD

lab.oclock.lan

LAB

pandit.lan

PANDIT

24

Le nom NetBIOS est crucial pour la compatibilité avec les anciens
systèmes et applications qui ne supportent pas le DNS. Comme par
exemple, les partages réseau via SMB utilisent souvent le nom
NetBIOS pour localiser les ressources.
Mais ça on reviendra plus tard dessus…

25

Maintenant qu’on comprend mieux comment un domaine est
identifié à la fois par son nom DNS et par son nom NetBIOS on peut
se demander :

“Mais où sont stockés concrètement les
éléments qui font fonctionner ce domaine ?”

26

Bonne question !

Ben dans le Sysvol pardi !

27

Sys-quoi ?
Le SYSVOL (pour System Volume) est un dossier partagé
automatiquement présent sur chaque contrôleur de domaine (DC). Il
contient tous les fichiers nécessaires à la réplication et à la cohérence
des stratégies dans le domaine.

28

Dedans, on retrouve notamment :
Les scripts d’ouverture de session (logon scripts),
Les GPO (Group Policy Objects) appliquées aux utilisateurs et ordinateurs,
Et les fichiers publics nécessaires à la configuration du domaine.

Il peut être répliqué par DFS-R dans les environnements récents.

29

🧩 Conclusion
Du LDAP au SYSVOL
LDAP → Structure logique de l'annuaire
↓
ADDS → Implémentation Microsoft de LDAP
↓
Forêt → Limite de confiance et de schéma
↓
Arbre → Espace de noms DNS commun
↓
Domaine → Unité d’administration et de sécurité
↓
Site → Topologie physique (réplication et DC)
↓
DNS / NetBIOS → Noms et identification du domaine
↓
SYSVOL → Réplication et cohérence des stratégies

30

En résumé :
LDAP fournit la logique et la structure.
ADDS met tout cela en œuvre dans Windows.
Forêt / Arbre / Domaine / Site structurent l’organisation.
DNS et NetBIOS identifient les domaines et hôtes.
SYSVOL assure la cohérence et la réplication des politiques.

🎯 Active Directory, c’est l’union de ces briques !

31

Allez, on met tout ça en pratique ! 🚀

32

