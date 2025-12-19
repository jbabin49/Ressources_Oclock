Introduction : Active Directory
DS et son importance
Active Directory DS est un service d'annuaire centralisé qui fournit une gestion des utilisateurs, des ordinateurs, des
groupes et des ressources dans un réseau informatique.
Active Directory est essentiel pour la sécurité, la gestion et l'administration des réseaux d'entreprise modernes.

Introduction à LDAP
LDAP, ou Lightweight Directory Access Protocol, est un protocole standardisé pour accéder et modifier des données
dans un annuaire. Il est largement utilisé dans les environnements informatiques pour gérer les utilisateurs, les
ordinateurs et autres ressources. LDAP est un protocole simple, flexible et performant, ce qui le rend adapté à une large
gamme d'applications.

LDAP sur Windows Server
Windows Server offre une implémentation complète du protocole LDAP. Il est intégré à Active Directory, le service
d'annuaire de Microsoft, qui fournit une solution puissante et flexible pour gérer les utilisateurs, les ordinateurs et les
ressources.
L'utilisation de LDAP sur Windows Server permet de centraliser la gestion des utilisateurs et des ressources, en offrant
des fonctionnalités telles que l'authentification, l'autorisation et la recherche d'informations dans l'annuaire. Les
administrateurs peuvent ainsi simplifier la gestion des identités et des accès, tout en assurant la sécurité et la fiabilité
des données. Grâce à l'intégration d'Active Directory, LDAP sur Windows Server permet également une synchronisation
transparente avec d'autres services et systèmes d'exploitation.

Historique de LDAP
Le protocole LDAP a été développé dans les années 1990 pour simplifier l'accès aux annuaires électroniques. Depuis ses
débuts, il a considérablement évolué pour devenir un standard incontournable dans la gestion des identités et des
accès dans les organisations.
LDAP est largement utilisé dans de nombreux domaines, tels que les entreprises, les établissements d'enseignement et
les services gouvernementaux. Il offre une méthode efficace de centralisation des informations utilisateur et de gestion
des autorisations, ce qui facilite la collaboration et l'accès aux ressources. De plus, LDAP est évolutif et peut s'intégrer à
d'autres protocoles pour offrir une solution complète de gestion des identités et des accès.

Configuration de LDAP
1

Création des objets
Active Directory permet de créer des objets LDAP, comme les utilisateurs, les groupes et les
ordinateurs. La création d'objets LDAP suit une hiérarchie, où les objets sont organisés dans des unités
d'organisation (OU) et des domaines.

2

Définition des attributs
Chaque objet LDAP possède des attributs, qui sont des caractéristiques qui le définissent. Les attributs
peuvent être des informations telles que le nom d'utilisateur, le mot de passe, l'adresse e-mail ou les
groupes auxquels l'utilisateur appartient.

3

Configuration des politiques
Active Directory offre des politiques LDAP qui définissent les règles et les restrictions relatives aux
objets. Ces politiques peuvent être appliquées à des groupes spécifiques d'utilisateurs ou
d'ordinateurs.

Schéma LDAP
Le schéma LDAP définit la structure et l'organisation des données dans un annuaire Active Directory. Il est représenté
par un ensemble de classes d'objets, d'attributs et de règles de validation. Chaque objet LDAP, tel qu'un utilisateur ou
un groupe, est une instance d'une classe d'objet particulière.

Les attributs définissent les propriétés d'un objet, par exemple, le nom d'utilisateur, le mot de passe, l'adresse e-mail ou
le groupe d'appartenance. Le schéma LDAP est essentiel pour garantir la cohérence et l'intégrité des données dans
l'annuaire.
CN: Le CN représente le "common name" (nom commun) d'un objet LDAP. Il correspond généralement au nom complet
d'un utilisateur ou au nom unique d'un objet dans l'annuaire. Le CN peut être utilisé pour identifier de manière unique
un objet au sein de l'annuaire.
SN: Le SN représente le "surname" (nom de famille) d'un objet LDAP. Il indique le nom de famille d'un utilisateur ou
peut être utilisé pour identifier un objet au sein de l'annuaire en combinaison avec d'autres attributs. Par exemple, dans
le cas d'un utilisateur, le CN pourrait être le nom complet et le SN serait le nom de famille spécifique. Ces attributs
permettent de définir de manière précise les caractéristiques d'un objet dans l'annuaire LDAP.
GN: Le GN représente le "given name" (prénom) d'un objet LDAP. Il indique le prénom d'un utilisateur ou peut être
utilisé en combinaison avec d'autres attributs pour identifier de manière unique un objet au sein de l'annuaire. Par
exemple, dans le cas d'un utilisateur, le CN pourrait être le nom complet, le SN serait le nom de famille et le GN serait le
prénom spécifique. Ainsi, ces attributs permettent de spécifier de manière précise l'identité d'un objet dans l'annuaire
LDAP.

Contrôle d'accès LDAP
Authentification
LDAP utilise des mécanismes

1

d'authentification pour vérifier l'identité des
utilisateurs.

2

Autorisation
Des permissions d'accès sont définies pour
chaque objet LDAP, permettant de contrôler

Contrôle d'accès basé sur les
rôles
LDAP supporte le contrôle d'accès basé sur les
rôles, ce qui permet de définir des permissions
en fonction des rôles des utilisateurs.

3

les actions que les utilisateurs peuvent
effectuer.

Applications LDAP

—

—

Gestion des utilisateurs et des groupes

Authentification et autorisation

LDAP est utilisé pour gérer les utilisateurs et les groupes

LDAP est utilisé pour authentifier les utilisateurs et

dans les réseaux d'entreprise. Il permet de contrôler

autoriser l'accès aux ressources en fonction des

l'accès aux ressources et de gérer les privilèges.

autorisations définies pour chaque utilisateur.

—

—

Annuaire d'entreprise

Intégration d'applications

LDAP sert de base à un annuaire d'entreprise qui stocke
des informations sur les utilisateurs, les ordinateurs, les

LDAP est utilisé pour intégrer des applications avec Active
Directory, permettant aux applications d'accéder aux

imprimantes et autres ressources.

données de l'annuaire.

Création d'un domaine Active Directory
Un domaine Active Directory est un groupe d'ordinateurs et d'utilisateurs gérés par un serveur Active Directory. Il est
essentiel pour une gestion centralisée et sécurisée des ressources et des identités.

Nom de domaine
Choisir un nom de domaine unique et facile à

1

mémoriser.

2
Création du domaine

3

Fonctionnement du domaine
Configurer le fonctionnement du domaine, tel
que la forêt, le domaine et les sites.

Utiliser l'assistant "Nouvel domaine" pour
créer le domaine Active Directory.

La création d'un domaine Active Directory implique la définition d'un nom de domaine, la configuration des paramètres
de fonctionnement et l'utilisation de l'assistant "Nouvel domaine".

C'est quoi une Forêt ?
Une forêt dans Active Directory est une collection de domaines qui partagent un ensemble commun de règles et de
politiques de sécurité. Elle établit une relation d'approbation entre plusieurs domaines, permettant ainsi une gestion et
une administration centralisées des ressources et des utilisateurs à travers ces domaines.

Les domaines au sein d'une forêt peuvent être organisés hiérarchiquement, avec un domaine racine et des domaines
enfants. La structure en forêt permet également la réplication des données entre les domaines, assurant ainsi la
cohérence des informations et la disponibilité des services. L'utilisation d'une forêt dans Active Directory offre une
flexibilité et une évolutivité pour répondre aux besoins d'une organisation, en permettant une gestion centralisée et
une gestion des politiques de sécurité à grande échelle.

Forêt, Tree, et Domain
En plus des domaines et des relations d'approbation, Active Directory utilise également les concepts de forêt et
d'arborescence pour organiser les domaines.
Un Tree est un ensemble de domaines liés hiérarchiquement, avec un domaine racine qui se trouve au sommet de
l'arborescence. Les domaines enfants sont connectés au domaine racine par des relations d'approbation, ce qui permet
une gestion centralisée des utilisateurs, des groupes et des ressources au sein de l'arborescence entière.
Une forêt, quant à elle, est un ensemble de trees qui partagent une structure de noms communs et une base de
données de répertoire partagée, offrant ainsi une gestion de l'authentification, de la sécurité et de l'accès unifiée pour
tous les domaines de la forêt.
Le domaine lui est une unité organisationnelle au sein de l'arborescence, composée d'un ou plusieurs serveurs et des
objets de sécurité tels que les utilisateurs, les groupes et les ordinateurs. Chaque domaine possède son propre
administrateur et ses propres politiques de sécurité, mais les domaines d'une même arborescence peuvent partager
des ressources et des stratégies de groupe grâce aux relations d'approbation.

Représentation
Forêt (Forest) :
Arbre 1 : oclock.local
Domaine enfant : etudiant.oclock.local
Domaine enfant : formateur.oclock.local
Arbre 2 : linkedin.local
Domaine enfant : lien.linkedin.local

C'est quoi Netbios !
NetBIOS (Network Basic Input/Output System) est un protocole de communication utilisé par les ordinateurs pour
partager des ressources et s'identifier sur un réseau local. Il permet notamment la résolution de noms d'ordinateurs en
adresses IP, facilitant ainsi la communication entre les machines. NetBIOS est couramment utilisé dans les réseaux
Windows, bien qu'il soit moins répandu avec l'introduction de protocoles plus modernes tels que TCP/IP.

Sys-quoi ? Ah ! SYSVOL !
Le Sysvol, ou System Volume, est un dossier partagé utilisé par Active Directory pour stocker les scripts de connexion,
les stratégies de groupe et autres fichiers nécessaires à la réplication entre les contrôleurs de domaine. Il contient les
informations de configuration et de stratégie qui sont appliquées aux ordinateurs et aux utilisateurs du domaine. La
réplication du Sysvol garantit la cohérence des données entre les contrôleurs de domaine, assurant ainsi la disponibilité
permet de garantir que tous les contrôleurs de domaine disposent des mêmes informations et que la disponibilité des
groupes
La gestion des utilisateurs et des groupes est essentielle pour la sécurité et l'organisation de l'Active Directory.

1

spécifiques.
2

Attribution d'appartenance

Attribuer les utilisateurs aux groupes appropriés pour gérer leurs
Définir les privilèges de chaque groupe pour contrôler
Création de stratégies
Configuration des paramètres

<h1 align=center>Introduction : Active Directory DS et son importance</h1>

Service d'annuaire centralisé pour la gestion des identités et des ressources réseau.

---

# Introduction à LDAP

LDAP (Lightweight Directory Access Protocol) est un protocole standardisé pour accéder et modifier des données dans un annuaire. Il est largement utilisé pour gérer les utilisateurs, ordinateurs et ressources dans les environnements informatiques.

## LDAP sur Windows Server
Windows Server intègre une implémentation complète de LDAP via Active Directory, permettant la centralisation de la gestion des identités et des ressources. Les fonctionnalités incluent :
- authentification
- autorisation
- recherche d'informations dans l'annuaire
**Important** : L'intégration d'Active Directory permet la synchronisation avec d'autres services et systèmes d'exploitation.

---

# Historique de LDAP

Le protocole LDAP a été développé dans les années 1990 pour simplifier l'accès aux annuaires électroniques. Il est devenu un standard incontournable pour la gestion des identités et des accès dans les organisations (entreprises, établissements d'enseignement, services gouvernementaux).

**Point clé** : LDAP centralise les informations utilisateur et la gestion des autorisations, facilitant la collaboration et l'accès aux ressources.

---

# Configuration de LDAP

## Création des objets
Active Directory permet de créer des objets LDAP (utilisateurs, groupes, ordinateurs) organisés hiérarchiquement dans des unités d'organisation (OU) et des domaines.

## Définition des attributs
Chaque objet LDAP possède des attributs (nom d'utilisateur, mot de passe, adresse e-mail, appartenance à des groupes, etc.).

## Configuration des politiques
Active Directory propose des politiques LDAP pour définir les règles et restrictions appliquées à des groupes spécifiques d'utilisateurs ou d'ordinateurs.

---

# Schéma LDAP

Le schéma LDAP définit la structure et l'organisation des données dans un annuaire Active Directory. Il comprend :
- classes d'objets
- attributs
- règles de validation

Chaque objet LDAP (utilisateur, groupe, etc.) est une instance d'une classe d'objet particulière. Les attributs définissent les propriétés de chaque objet (nom, mot de passe, adresse e-mail, groupe d'appartenance).

**Note** : Le schéma LDAP garantit la cohérence et l'intégrité des données dans l'annuaire.

3

Attribuez des stratégies de groupe à des unités organisationnelles spécifiques pour appliquer les
paramètres aux utilisateurs et aux ordinateurs pertinents.

Gestion des stratégies

4

Gérez les stratégies de groupe pour mettre à jour les paramètres, résoudre les problèmes et améliorer la
sécurité.

Gestion des comptes d'utilisateurs
1

Modification des mots de passe
Les utilisateurs peuvent modifier leurs propres mots de passe à l'aide d'outils intégrés à Active
Directory, comme le panneau de configuration de Windows.

2

Réinitialisation des mots de passe
Les administrateurs peuvent réinitialiser les mots de passe des utilisateurs oubliés ou compromis en
utilisant des outils d'administration Active Directory.

3

Blocage des comptes
Les comptes d'utilisateurs peuvent être temporairement bloqués pour des raisons de sécurité, comme
des tentatives de connexion incorrectes répétées.

4

Déblocage des comptes
Les administrateurs peuvent débloquer les comptes bloqués après avoir vérifié les raisons du blocage
et pris les mesures correctives nécessaires.

Intégration de l'Active Directory avec
d'autres services
L'intégration d'Active Directory avec d'autres services permet d'accroître la sécurité et la gestion centralisée des
ressources.

—

—

Serveurs de messagerie

Serveurs de fichiers

Intégration avec des serveurs de messagerie comme

Intégration avec des serveurs de fichiers pour un accès

Exchange Server.

contrôlé aux données.

—

—

Applications

Services cloud

Intégration avec des applications d'entreprise pour une

Intégration avec des services cloud comme Azure AD pour

gestion centralisée des utilisateurs et des groupes.

une gestion hybride des identités.

La synergie avec d'autres services améliore la gestion des ressources et l'accès aux données.

Gestion des serveurs membres
Les serveurs membres sont des ordinateurs qui font partie d'un domaine Active Directory. Ils hébergent des
applications et des données partagées, et sont gérés par le contrôleur de domaine.

—

—

Joindre un serveur

Configuration des stratégies

Joindre un serveur à un domaine Active Directory.

Appliquer les stratégies de groupe aux serveurs membres.

—

—

Gestion des comptes

Surveillance

Gérer les comptes d'utilisateurs et de groupes sur les

Surveiller l'état et la performance des serveurs membres.

serveurs membres.
La gestion des serveurs membres permet de garantir la sécurité, la fiabilité et la conformité des ressources réseau.

Surveillance et maintenance d'Active
Directory

—

—

—

Surveillance

Journaux d'événements

Outils de surveillance

La surveillance d'Active Directory est

Examinez régulièrement les journaux

Utilisez des outils de surveillance

essentielle pour garantir un
fonctionnement optimal et détecter

d'événements pour identifier les
erreurs, les avertissements et les

dédiés à Active Directory pour
surveiller les performances et

les problèmes potentiels.

événements de sécurité.

l'intégrité du service.

—

—

—

Maintenance

Mises à jour

Sauvegardes

La maintenance régulière d'Active

Appliquez régulièrement les mises à

Créez des sauvegardes régulières de

Directory est importante pour

jour de sécurité et les correctifs pour

Active Directory pour restaurer le

maintenir la stabilité et la sécurité du
système.

protéger Active Directory contre les
vulnérabilités.

système en cas de panne ou de
corruption.

—
Optimisation
Optimisez les performances d'Active
Directory en ajustant les paramètres
et en gérant efficacement les
ressources.

