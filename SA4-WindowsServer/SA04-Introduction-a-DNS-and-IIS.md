Introduction à DNS & IIS
DNS (Domain Name System) est un système qui permet de traduire les noms de domaine en adresses IP. Il joue un rôle
essentiel dans la résolution des noms de domaine sur Internet. IIS (Internet Information Services), quant à lui, est un
serveur web développé par Microsoft qui permet de publier des sites web et des applications sur Internet. Dans cet
article, nous explorerons le fonctionnement de DNS et IIS, ainsi que leur importance dans le domaine de l'hébergement
web.
IIS est un serveur web développé par Microsoft. IIS est intégré aux systèmes d'exploitation Windows Server et permet
aux utilisateurs d'héberger des sites web, des applications et des services web. IIS est une plateforme web puissante et
complète pour les développeurs et les administrateurs web. IIS est utilisé par des millions d'entreprises et
d'organisations à travers le monde.

Introduction au serveur DNS
Windows Server
Le serveur DNS Windows Server est une solution de serveur DNS puissante et fiable, conçue pour les réseaux de toutes
tailles. Il offre une large gamme de fonctionnalités, y compris la résolution de noms, la zone de stockage et la gestion de
l'autorité.
En plus de ces fonctionnalités principales, le serveur DNS Windows Server prend en charge la sécurisation des requêtes
DNS grâce à l'utilisation de protocoles tels que DNS over TLS et DNSSEC. Il permet également la mise en place de règles
de redirection et de filtrage pour contrôler l'accès à certains domaines. Avec une interface conviviale et une
administration centralisée, le serveur DNS Windows Server facilite la gestion et le déploiement des services DNS dans
un environnement Windows.

Rôle et fonctionnalités du serveur DNS
Résolution des noms de
domaine

1

Le serveur DNS traduit les noms de domaine
lisibles par l'homme, comme google.com, en
adresses IP numériques, permettant aux
ordinateurs de se connecter aux sites web et

2

Le serveur DNS stocke des informations sur les
zones de recherche, qui définissent les
domaines et les adresses IP associés.

aux services.

Sécurité et authentification

Gestion des zones de recherche

3

Le serveur DNS peut être configuré pour
garantir la sécurité des requêtes et des
réponses DNS, empêchant les attaques et les
falsifications de données.

4

Gestion des enregistrements
DNS
Le serveur DNS gère la création, la
modification et la suppression des
enregistrements DNS, qui stockent des
informations sur les noms de domaine, les
adresses IP et autres informations.

Installation et configuration du serveur
DNS
Installation de Windows Server
La première étape consiste à installer

1

Windows Server sur un serveur physique ou
virtuel.

Configuration des paramètres
DNS

2
3

Activation du rôle DNS
Le rôle DNS doit être activé dans le
gestionnaire de serveur.

Les paramètres DNS, tels que le nom de
domaine et les serveurs racine, doivent être
configurés.

4

Création de zones de recherche
Des zones de recherche directe et inverse
doivent être créées pour le domaine.

Une fois le serveur DNS installé et configuré, il est prêt à être utilisé pour la résolution de noms et la gestion des
enregistrements DNS.

Gestion des zones de recherche directe

—

—

Création de Zones

Configuration des Enregistrements

Créez des zones pour les domaines que vous souhaitez
gérer, en spécifiant les serveurs DNS maîtres et

Ajoutez les enregistrements DNS nécessaires, tels que les
enregistrements A, CNAME, MX, et SRV.

secondaires.

—

—

Délégation de Sous-domaines

Gestion des Autorisations

Déléguez les sous-domaines à des serveurs DNS

Configurez les autorisations pour contrôler l'accès et la

spécifiques pour une gestion efficace.

Gestion des zones de recherche inverse
1
2

Attribution de la zone à un serveur DNS

Configuration des
les serveurs DNS spécifiés afin de

<h1 align=center>Introduction à DNS & IIS</h1>

Présentation du système de noms de domaine (DNS) et du serveur web IIS sur Windows Server.

---

# Introduction générale

DNS (Domain Name System) traduit les noms de domaine en adresses IP, assurant la résolution des noms sur Internet. IIS (Internet Information Services) est un serveur web développé par Microsoft pour publier des sites et applications web.

IIS est intégré à Windows Server et utilisé par de nombreuses entreprises pour héberger des services web.

---

# Serveur DNS Windows Server

Le serveur DNS Windows Server est une solution fiable et puissante pour tous types de réseaux. Il offre :
- résolution de noms
- gestion des zones de stockage
- gestion de l'autorité

**Sécurité** : Prise en charge de DNS over TLS, DNSSEC, règles de redirection et filtrage.

Interface conviviale et administration centralisée pour faciliter la gestion et le déploiement des services DNS.

---

# Rôle et fonctionnalités du serveur DNS

- Résolution des noms de domaine (traduction noms ↔ adresses IP)
- Stockage des informations sur les zones de recherche
- Sécurisation des requêtes et réponses DNS
- Gestion des enregistrements DNS (création, modification, suppression)
Utilisez des outils de diagnostic
pour tester la résolution de noms

chaque domaine ou sous-

résoudre les noms.

et s'assurer que les serveurs DNS

domaine.

fonctionnent correctement.

Création et gestion des enregistrements
DNS

—

—

—

Enregistrement A

Enregistrement CNAME

Enregistrement MX

Associe un nom d'hôte à une adresse

Crée un alias pour un autre

Spécifie le serveur de messagerie

IP

enregistrement

pour un domaine

—

—

Enregistrement SRV

Enregistrement TXT

Définit les services fournis par un

Stocke des informations textuelles

serveur

sur un domaine

Les enregistrements DNS sont des données qui définissent les relations entre les noms de domaine et les adresses IP.
La gestion des enregistrements DNS est essentielle pour garantir la résolution correcte des noms de domaine et le bon
fonctionnement des services réseau.
La création et la gestion des enregistrements DNS permettent de configurer et de contrôler les différents aspects de la
résolution des noms de domaine. Les enregistrements A associant des noms d'hôtes à des adresses IP, les
enregistrements CNAME créant des alias et les enregistrements MX spécifiant les serveurs de messagerie apportent une
flexibilité et une personnalisation à la gestion des noms de domaine. Les enregistrements SRV et TXT offrent également
des fonctionnalités supplémentaires pour spécifier les services fournis par un serveur et stocker des informations
textuelles sur un domaine.

Configuration des paramètres avancés du
serveur DNS
1

Paramètres de sécurité
Configurez la sécurité du serveur DNS. Cela inclut l'activation de l'authentification et de l'autorisation,
la limitation de l'accès au serveur DNS et la mise en place de protocoles de sécurité tels que DNSSEC.

2

Paramètres de performance
Optimisez les performances du serveur DNS. Cela peut inclure la configuration de la mise en cache, la
réduction de la latence et l'amélioration de la gestion des requêtes.

3

Paramètres de journalisation
Configurez la journalisation des événements du serveur DNS, y compris les requêtes, les erreurs et les
modifications apportées à la configuration. Utilisez ces informations pour la surveillance et le
dépannage.

Sécurisation du serveur DNS
1

Contrôle d'accès
Limitez l'accès au serveur DNS aux administrateurs autorisés. Configurez des stratégies de sécurité
pour empêcher les accès non autorisés.

2

Authentification et autorisation
Activez l'authentification et l'autorisation pour les requêtes DNS. Utilisez des protocoles tels que
DNSSEC pour assurer l'intégrité des données.

3

Protection contre les attaques
Mettez en place des pare-feu pour bloquer les attaques malveillantes. Configurez des règles pour filtrer
les requêtes DNS suspectes.

4

Sauvegarde et récupération
Sauvegardez régulièrement les données DNS pour restaurer en cas d'incident. Utilisez des outils de
sauvegarde et de restauration pour assurer la récupération des données.

Sauvegarde et restauration du serveur
DNS

—

—

Sauvegarde régulière

Sauvegardes différentielles

Planifier des sauvegardes incrémentielles et complètes.

Stocker les modifications depuis la dernière sauvegarde
complète.

—

—

Stockage hors site

Restauration du serveur

Conserver les copies de sauvegarde dans un
emplacement distinct.

Restaurer les données à partir d'une sauvegarde en cas de
panne.

La sauvegarde et la restauration du serveur DNS sont essentielles pour garantir la disponibilité du service et la
protection des données.
Il est important de réaliser des sauvegardes régulières des données DNS et de les stocker hors site pour éviter les pertes
de données en cas de panne du serveur ou de catastrophe naturelle.
Lors de la restauration, il est nécessaire de restaurer les données dans le même ordre que les sauvegardes ont été
effectuées pour garantir l'intégrité des données.

Surveillance et dépannage du serveur
DNS

—

—

—

Surveillance des
performances

Diagnostic des erreurs

Résolution des problèmes

Analyser les journaux d'événements
pour identifier les causes des erreurs.

Appliquer les correctifs nécessaires
et configurer le serveur DNS pour

Utiliser des outils de surveillance
pour identifier les problèmes de
performances.

optimiser les performances.

La surveillance du serveur DNS est cruciale pour garantir sa fiabilité et ses performances. Elle permet d'identifier les
problèmes potentiels et de les résoudre rapidement. Les outils de surveillance permettent de surveiller les
performances du serveur DNS, y compris le temps de réponse, le nombre de requêtes et la taille des zones. En plus de la
surveillance, il est également important de dépanner les erreurs et les problèmes qui peuvent survenir. L'analyse des
journaux d'événements est essentielle pour identifier les causes des erreurs et les résoudre. La résolution des
problèmes peut impliquer l'application de correctifs, la configuration du serveur DNS et l'optimisation des paramètres.

Intégration du serveur DNS avec Active
Directory
L'intégration du serveur DNS avec Active Directory offre des avantages significatifs en termes de gestion centralisée et
de simplification des opérations. Active Directory fournit un cadre unifié pour la gestion des utilisateurs, des ordinateurs
et d'autres ressources réseau, tandis que DNS assure la résolution de noms. En intégrant ces deux services, vous pouvez
automatiser la création et la mise à jour des enregistrements DNS pour les ordinateurs et les utilisateurs gérés par
Active Directory.

—

—

—

Synchronisation

Intégration

Gestion

Synchroniser les informations Active

Configurer Active Directory pour

Gérer les enregistrements DNS via

Directory avec le serveur DNS

utiliser le serveur DNS intégré

Active Directory

Lorsque les deux services sont intégrés, vous pouvez profiter d'une gestion centralisée des enregistrements DNS. Vous
pouvez également utiliser des outils Active Directory pour créer et gérer des zones DNS, des enregistrements SRV et
d'autres types d'enregistrements DNS, ce qui simplifie les processus de configuration et de maintenance.

Gestion des clients DNS
1

Configuration manuelle
Les clients peuvent être configurés manuellement en spécifiant les serveurs DNS préférés et
secondaires dans les paramètres réseau.

2

DHCP
Les serveurs DHCP peuvent attribuer automatiquement les adresses IP et les serveurs DNS aux clients
pendant la connexion au réseau.

3

Groupes de stratégie
Les stratégies de groupe peuvent être utilisées pour définir des paramètres DNS spécifiques pour les
clients dans un domaine Active Directory.

Pourquoi utiliser IIS ?
IIS, ou Internet Information Services, est un serveur web puissant et flexible. Microsoft l'a développé pour héberger des
sites web, des applications et des services. Il offre une multitude d'avantages pour les développeurs et les
administrateurs web.
IIS est un choix populaire grâce à sa fiabilité et son intégration avec le système d'exploitation Windows.
Il est facile à configurer et à gérer. Son interface conviviale permet aux utilisateurs de tous niveaux de compétences de
l'utiliser efficacement.

Étapes d'installation d'IIS sur Windows
Server 2022
Activez les fonctionnalités de
serveur
Cliquez sur "Activer ou désactiver des
fonctionnalités Windows."

Confirmez l'installation

1
2
3

Sélectionnez IIS
La liste des fonctionnalités serveur comprend
IIS et ses composants.

Cliquez sur "OK" pour lancer l'installation
d'IIS.

L'installation d'IIS est un processus simple et intuitif. Il suffit de suivre les étapes mentionnées ci-dessus et de s'assurer
que toutes les dépendances sont installées. Une fois l'installation terminée, IIS est prêt à être configuré et utilisé pour
héberger des sites web.

Configuration de base d'IIS
Une fois IIS installé, il est essentiel de le configurer correctement pour répondre aux besoins spécifiques de votre
serveur web.

Paramètres de sécurité

1

2

Contrôle d'accès, authentification et autorisation

Gestion des sites web
Configuration de sites web, de dossiers virtuels et de domaines

Configuration des applications

3

Paramètres d'applications, pools d'applications et
configurations de sécurité

Paramètres du serveur

4

Configuration du serveur, de la journalisation et des
performances

La configuration de base implique la mise en place de paramètres de sécurité, la gestion des sites web, la configuration
des applications et la définition des paramètres du serveur.

Gestion des sites web dans IIS
1

Création de sites web
IIS permet de créer et de gérer des sites web, chacun avec ses propres paramètres de configuration.

2

Configuration des sites web
Configurez les paramètres du site, tels que le nom d'hôte, le chemin physique, l'application par défaut
et les autorisations d'accès.

3

Gestion des applications
IIS offre des outils pour gérer les applications web, y compris la configuration des pools d'applications,
des paramètres de sécurité et des applications pré-installées.

4

Gestion des fichiers
Gérer les fichiers du site, y compris les fichiers HTML, CSS, JavaScript, les images et les fichiers de
configuration.

5

Paramètres de sécurité
Configurer les autorisations d'accès pour les utilisateurs et les groupes afin de garantir la sécurité du
site web.

Création d'un nouveau site web
Accès au Gestionnaire des sites
web
Depuis le tableau de bord IIS, ouvrez le
Gestionnaire des sites web pour accéder aux
options de création de nouveaux sites.

Paramétrage des liaisons

1
2

Configuration du site web
Définissez le nom du site, le chemin physique
vers le contenu du site, le nom de domaine et

3

le port d'écoute.

Créez des liaisons pour les protocoles HTTP et
HTTPS, en spécifiant le port et le nom d'hôte
pour chaque liaison.

4

Activation des fonctionnalités
Activez les modules et les fonctionnalités
nécessaires pour le site web, tels que les

Vérification de la configuration
Validez la configuration du site web en
naviguant vers le site à l'aide du navigateur
web.

5

applications ASP.NET, les services web ou les
sites statiques.

Paramètres de sécurité dans IIS
IIS offre un éventail de fonctionnalités de sécurité pour protéger vos applications web et vos serveurs.

1

4

Authentification

2

Autorisation

3

Filtrage

Contrôler l'accès aux

Déterminer les actions

Bloquer les requêtes

ressources web.

autorisées.

malveillantes.

Chiffrement
Protéger les données sensibles.

Ces mécanismes permettent de sécuriser les applications web en limitant l'accès aux ressources, en filtrant les requêtes
suspectes et en protégeant les données sensibles.

Optimisation des performances d'IIS
1

Configuration du cache
Activer le cache HTTP pour les fichiers statiques comme les images et les fichiers CSS. Utiliser des
techniques de mise en cache côté serveur, comme le cache de sortie.

2

Compression
Activer la compression GZIP pour réduire la taille des fichiers HTML, CSS et JavaScript. Ceci accélère le
temps de chargement des pages web.

3

Gestion des threads
Ajuster le nombre de threads de travail et de threads d'E/S pour optimiser les performances de IIS en
fonction de la charge du serveur.

Surveillance et journalisation dans IIS
IIS offre des outils puissants pour surveiller et analyser les performances des applications web et du serveur lui-même.
Des logs détaillés sont générés, permettant d'identifier les problèmes et d'améliorer les performances.

Collecte des données

1

Des journaux d'événements système, des logs IIS et des traces d'exécution des applications
sont collectés.

Analyse des logs

2

Des outils intégrés et des solutions tierces permettent d'analyser les logs
et d'identifier les tendances.

Alerte et notification

3

Des alertes sont déclenchées en cas d'événements
critiques ou de performance anormale.

La configuration de la journalisation est essentielle pour garantir une surveillance efficace du serveur et des
applications web. Le choix des logs à collecter, la fréquence de collecte et les méthodes d'analyse dépendent des
besoins spécifiques de l'environnement.

Gestion des mises à jour et des patchs
d'IIS
La mise à jour régulière d'IIS est essentielle pour assurer la sécurité et la stabilité du serveur web.
Les mises à jour incluent des correctifs de sécurité et des améliorations de performances.

—

—

—

Planification

Téléchargement

Installation

Établir un calendrier de mise à jour.

Obtenir les mises à jour via Windows
Update.

Appliquer les mises à jour et
redémarrer le serveur.

—

—

Vérification

Documentation

Confirmer que les mises à jour sont

Enregistrer les détails des mises à

installées correctement.

jour appliquées.

Il est important de tester les mises à jour dans un environnement de développement avant de les déployer en
production.

Résolution des problèmes courants dans
IIS
1

2

3

Erreurs 404

Erreurs 500

Les erreurs 404 indiquent que la

Les erreurs 500 signalent des

Problèmes de
performance

page demandée n'a pas été
trouvée. Vérifiez la configuration

erreurs de serveur. Examinez les
journaux d'événements, les

du site Web, les autorisations des

fichiers de journalisation IIS et

dossiers et les règles de
réécriture d'URL.

les configurations de
l'application.

Analyser le trafic du site Web, les
ressources du serveur et les
paramètres de configuration IIS
peut aider à améliorer les
performances.

Sauvegarde et restauration de la
configuration IIS
Sauvegarde de la configuration
Utilisez l'outil de ligne de commande

1

AppCmd.exe pour exporter la configuration IIS
vers un fichier XML.

Sauvegarde de la base de
données Metabase

2
3

Sauvegardez la base de données Metabase,
qui stocke les paramètres de configuration IIS.

4

Restauration de la configuration
Importez le fichier XML de configuration
sauvegardé en utilisant AppCmd.exe.

Restauration de la base de
données Metabase
Restaurez la base de données Metabase en

Gestion de la version
Utilisez les outils de contrôle de version pour
gérer les différentes versions de la
configuration IIS.

5

utilisant les outils de sauvegarde et de
restauration de SQL Server.

Intégration d'IIS avec d'autres services
Windows
IIS peut être intégré avec d'autres services Windows pour offrir des fonctionnalités avancées. Cela permet de créer des
solutions complètes et robustes pour les applications web.

Active Directory

1

Authentification et autorisation des
utilisateurs

2

SQL Server
Gestion des données et des bases de données

Windows Server Update
Services (WSUS)

3

Gestion des mises à jour pour IIS

L'intégration avec Active Directory permet de gérer l'accès aux applications web et de contrôler les permissions des
utilisateurs. La connexion à SQL Server permet de stocker et de gérer les données des applications web.

Sécurisation des communications avec
HTTPS
HTTPS est un protocole de communication sécurisé qui protège les données transmises entre un serveur web et un
navigateur.
Le protocole HTTPS utilise le cryptage SSL/TLS pour chiffrer les données.

1
2
3
4

Obtenir un certificat SSL
Installer le certificat
Configurer le site web pour HTTPS
Tester la sécurité

L'utilisation de HTTPS est essentielle pour sécuriser les communications web et protéger les données sensibles.

Gestion des certificats SSL/TLS dans IIS
1

Obtention des certificats
Les certificats SSL/TLS peuvent être obtenus auprès d'autorités de certification (CA) comme Let's
Encrypt ou Comodo.

2

Installation des certificats
Les certificats SSL/TLS doivent être installés dans le magasin de certificats de l'ordinateur et associés
aux sites Web IIS.

3

Gestion des certificats
IIS fournit des outils pour gérer la durée de vie des certificats, renouveler les certificats expirés et
supprimer les certificats obsolètes.

Mise en place de la haute disponibilité
avec IIS
Configuration de cluster
IIS peut être configuré dans un environnement

1

de cluster pour assurer une haute
disponibilité et une tolérance aux pannes.
Cela implique de configurer un cluster de

2

serveurs Windows Server avec des nœuds

Gestion de la charge
Un équilibreur de charge est utilisé pour
distribuer le trafic entré sur plusieurs serveurs

supplémentaires pour héberger les instances

IIS dans le cluster, ce qui garantit que le
service web reste disponible même si un

IIS.

serveur tombe en panne.

Réplication de données

3

Pour une haute disponibilité, il est crucial de
répliquer les données et les configurations IIS
sur tous les nœuds du cluster. Cela assure que
les modifications apportées à un serveur sont
répercutées sur tous les autres.

4

Surveillance et gestion
Il est essentiel de surveiller attentivement les
performances et la disponibilité du cluster IIS.
Les outils de surveillance peuvent détecter les
problèmes potentiels et déclencher des
actions de récupération pour minimiser les
temps d'arrêt.

