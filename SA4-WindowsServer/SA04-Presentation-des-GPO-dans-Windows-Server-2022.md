Présentation des GPO dans
Windows Server 2022

Qu'est-ce qu'une Stratégie de Groupe ?
Une Stratégie de Groupe (Group Policy Object ou GPO) est un outil puissant de gestion et de configuration centralisée
dans les environnements Windows Server. Elle permet aux administrateurs système de définir et d'appliquer des
paramètres de configuration standards à travers l'ensemble d'un réseau d'entreprise.
Les GPO offrent un contrôle avancé sur les différents aspects d'un ordinateur ou d'un compte d'utilisateur, comme les
paramètres de sécurité, les options d'administration, les préférences utilisateur et les déploiements d'applications.
Elles contribuent ainsi à assurer une cohérence et une maintenabilité accrues du parc informatique.
Grâce à leur structure hiérarchique, les GPO permettent également de s'adapter finement aux besoins spécifiques de
chaque unité organisationnelle, tout en maintenant une politique globale cohérente au niveau de l'entreprise.

Avantages des GPO

—

—

—

Gestion centralisée

Cohérence et
Les stratégies de groupe permettent
d'applications et les mises à jour de
3


<h1 align=center>Présentation des GPO dans Windows Server 2022</h1>

Gestion centralisée et standardisation de la configuration des postes et utilisateurs dans un réseau Windows.

---

# Qu'est-ce qu'une Stratégie de Groupe ?

Une Stratégie de Groupe (Group Policy Object ou GPO) est un outil de gestion et de configuration centralisée dans les environnements Windows Server. Elle permet de définir et d'appliquer des paramètres standards à l'ensemble d'un réseau d'entreprise.

Les GPO contrôlent :
- paramètres de sécurité
- options d'administration
- préférences utilisateur
- déploiements d'applications

**Point clé** : Les GPO assurent cohérence et maintenabilité du parc informatique, tout en s'adaptant aux besoins spécifiques de chaque unité organisationnelle.

---

# Avantages des GPO

- Gestion centralisée des paramètres
- Cohérence et standardisation sur tous les postes
- Sécurité renforcée (restrictions d'accès, contrôles d'applications, mises à jour)

---

# Hiérarchie et priorité des GPO

Les GPO sont organisées de façon hiérarchique, permettant une grande flexibilité et personnalisation. La priorité dépend de l'ordre d'application : les GPO les plus basses dans la hiérarchie peuvent écraser les paramètres des GPO supérieures.

paramètres de sécurité du système d'exploitation,

fonctionnalités d'administration du système, telles

comme les stratégies de mot de passe, les droits
d'accès, la protection contre les programmes

que la gestion des mises à jour, la configuration
des imprimantes et des partages réseau, ainsi que

malveillants et les règles de chiffrement des

les paramètres du Bureau et du Panneau de

données.

configuration.

Paramètres d'utilisateur

4

Paramètres d'ordinateur

Les GPO permettent de définir les préférences et

Les GPO peuvent également être utilisées pour

les paramètres pour les utilisateurs, notamment

configurer les paramètres au niveau des machines,

leurs paramètres de bureau, de navigateur, de
messagerie électronique et d'applications métier.

comme les paramètres de démarrage, les scripts
de connexion et de déconnexion, ainsi que les
paramètres matériels.

Paramètres de sécurité avec les GPO

—

—

—

Contrôle d'accès

Politique de mots de
passe

Gestion des audits

Les GPO permettent de définir
finement les autorisations d'accès
aux ressources, en fonction des

Les GPO offrent un moyen centralisé
de définir la politique de gestion des

groupes d'utilisateurs ou
d'ordinateurs. Cela garantit la

mots de passe, comme la complexité,

sécurité et l'intégrité du système en

des comptes après un certain
nombre de tentatives. Cela renforce

restreignant les privilèges aux seuls
utilisateurs autorisés.

la durée de validité ou le verrouillage

considérablement la sécurité des

Les GPO permettent d'activer et de
configurer les journaux
d'événements de sécurité, afin de
tracer les actions des utilisateurs et
de détecter rapidement toute activité
suspecte. Cela facilite la surveillance
et le contrôle de la sécurité du
système.

accès.
Par exemple nous retrouvons également la possibilité de configurer des GPO pour la gestion des mises à jour
automatiques, ce qui permet d'assurer que les systèmes restent à jour avec les derniers correctifs de sécurité.
De plus, les GPO offrent également des fonctionnalités avancées telles que la restriction de l'utilisation de
périphériques externes ou la configuration des paramètres de pare-feu, contribuant ainsi à renforcer encore davantage
la sécurité globale du système.

Paramètres d'administration avec les GPO

—

—

—

Configuration des
paramètres
d'administration

Personnalisation avancée

Déploiement et
application des GPO

Stratégies de Groupe, les

Une fois les Stratégies de Groupe

Les Stratégies de Groupe permettent

configurées, les administrateurs

de configurer de nombreux

administrateurs Windows peuvent
paramétrer finement les

paramètres d'administration sur les

comportements du système

ordinateurs et les utilisateurs du
réseau. Il est possible de gérer les

d'exploitation et des applications. Ils
peuvent ainsi adapter

droits d'accès, les options de

l'environnement de travail de

démarrage, les paramètres de
sécurité et bien d'autres éléments

manière optimale aux besoins
spécifiques de leur organisation.

Grâce à l'outil de gestion des

peuvent les appliquer à des groupes
d'utilisateurs ou d'ordinateurs
spécifiques. Cela permet d'assurer
une cohérence et une
standardisation des paramètres dans
tout le réseau, simplifiant ainsi la
gestion et le support informatique.

essentiels au bon fonctionnement du
système d'exploitation.
Les paramètres d'administration quant a eux permette de personnaliser davantage les fonctionnalités et les restrictions
au niveau des utilisateurs et des ordinateurs.
Par exemple, il est possible de limiter l'accès à certaines applications, de désactiver certaines fonctionnalités du
système d'exploitation ou d'imposer des configurations de sécurité spécifiques.

Paramètres d'utilisateur avec les GPO

—

—

—

Paramétrer l'expérience
utilisateur

Contrôle des paramètres
du bureau

Gestion des dossiers et
fichiers

Les Stratégies de Groupe (GPO)

Avec les GPO, vous pouvez définir les

Les GPO vous permettent de

offrent un moyen puissant de
configurer l'environnement de travail

options par défaut du bureau, telles
que le fond d'écran, la résolution, les

configurerles paramètres par défaut
pour les dossiers, les documents et

des utilisateurs. Vous pouvez

icônes, etc. Cela permet d'assurer

les fichiers des utilisateurs. Vous

personnaliser l'interface, les
préférences, les paramètres

une expérience cohérente et
professionnelle pour tous les

pouvez par exemple imposer
certaines restrictions d'accès ou de

d'applications et bien plus encore

utilisateurs.

stockage.

pour correspondre à leurs besoins
spécifiques.
Dans les paramètres d'utilisateur nous pouvons modifier par exemple le chemin de stockage des fichiers ou le dossier
de téléchargement par défaut, ou encore définir des quotas de stockage pour les utilisateurs ou les groupes
d'utilisateurs spécifiques. Cela peut s'avérer très utile pour contrôler l'espace disque utilisé et éviter les problèmes de
saturation.

Paramètres d'ordinateur avec les GPO

—

—

—

Configuration des
paramètres au niveau des
ordinateurs

Mise à jour automatique
des ordinateurs

Gestion du démarrage des
ordinateurs

Les GPO offrent un moyen efficace de

Les Stratégies de Groupe permettent

Les Stratégies de Groupe permettent

contrôler et de déployer les mises à
jour de Windows et des applications

également de configurer les
paramètres de démarrage des

sur l'ensemble du parc. Il est ainsi

ordinateurs, comme l'affichage du

possible de s'assurer que tous les
postes sont à jour et sécurisés, tout

logo de l'entreprise, le lancement
automatique d'applications, ou

en limitant les interventions

encore la connexion automatique

manuelles.

des utilisateurs. Cela permet
d'homogénéiser l'expérience

de configurer une multitude de
paramètres au niveau des
ordinateurs, tels que les paramètres
de sécurité, de gestion de
l'alimentation, de démarrage, ou
encore les mises à jour
automatiques. Cette gestion
centralisée assure une cohérence et
une standardisation du parc

utilisateur.

informatique.
Dans les paramètres d'ordinateur nous allons pouvons configurer plusieurs options relatives à la gestion de
l'alimentation. Par exemple, nous pouvons définir des politiques de mise en veille ou d'extinction automatique après
une période d'inactivité, ce qui contribue à économiser de l'énergie. De plus, les GPO permettent de contrôler les
options d'alimentation avancées, telles que la gestion des processeurs ou des hibernations, pour optimiser les
performances des ordinateurs. Enfin, il est possible de planifier des tâches de réveil ou d'extinction pour une gestion
encore plus personnalisée de l'alimentation des machines.

Déploiement d'applications avec les GPO
1

Configurer les paramètres
d'installation

2

Déployer des mises à jour
automatiques

Grâce aux GPO, vous pouvez déployer des logiciels

Les GPO vous permettent également de gérer les

de manière centralisée en définissant les

mises à jour des applications. Vous pouvez

paramètres d'installation et de configuration de

configurer des fenêtres de maintenance pour

l'application. Cela permet d'assurer une
installation cohérente sur tous les postes.

installer automatiquement les dernières versions,
garantissant ainsi que tous vos utilisateurs
disposent de la même version à jour.

3

Restreindre l'accès aux applications

4

Simplifier le déploiement

Avec les GPO, vous pouvez aussi contrôler l'accès à
certaines applications en fonction des profils des

Le déploiement d'applications via les GPO est bien
plus simple et efficace que des installations

utilisateurs ou des groupes. Cela vous aide à

manuelles sur chaque poste. Vous gagnez ainsi en

sécuriser votre environnement et à éviter les
utilisations non autorisées.

temps et en productivité pour gérer l'ensemble de
votre parc informatique.

Une des gros intérêt également des GPO c'est la possibilité de déployer des applications automatiquement sur tous les
postes de travail ou seulement sur certains groupes d'utilisateurs. Cela facilite grandement la gestion et la distribution
des applications, en évitant les tâches répétitives et fastidieuses. De plus, avec les GPO, vous avez la possibilité de
planifier le déploiement des applications à des moments précis, afin de minimiser les perturbations pour les
utilisateurs et d'optimiser les ressources du réseau.

Gestion des scripts avec les GPO

—

—

—

Exécuter des scripts lors
du démarrage

Déléguer l'exécution de
scripts

Surveiller l'exécution des
scripts

Les GPO permettent de déployer des

Les administrateurs peuvent définir

Les journaux d'événements

scripts qui s'exécutent

des autorisations spécifiques pour

permettent de suivre l'exécution des

automatiquement lors du démarrage
d'un ordinateur ou de la connexion

permettre à certains utilisateurs ou
groupes d'exécuter des scripts

scripts déployés via les GPO. Cela
facilite le dépannage en cas de

d'un utilisateur. Ces scripts peuvent

particuliers. Cela offre une flexibilité

problème et permet de s'assurer que

être utilisés pour installer des
applications, configurer des

dans la gestion des tâches
administratives tout en maintenant

les scripts se déroulent comme
prévu.

paramètres système ou effectuer

un contrôle approprié.

d'autres actions de manière
centralisée.
Nous pouvons également rajouter des scripts avec les GPO, nous pouvons avec ces scripts faire des actions
personnalisées lors de la connexion ou de la déconnexion d'un utilisateur. Par exemple, un script pourrait être utilisé
pour effectuer une sauvegarde automatique des fichiers de l'utilisateur lorsqu'il se déconnecte de son compte et
également pour nettoyer certains fichiers temporaires. Les scripts permettent d'automatiser des tâches spécifiques et
d'améliorer l'efficacité des opérations administratives. Cependant, il est important de surveiller l'exécution des scripts
pour détecter tout problème potentiel et s'assurer qu'ils fonctionnent correctement.

Gestion des paramètres d'impression avec
les GPO
Contrôle de l'accès aux imprimantes

Définition des paramètres par défaut

Les GPO permettent de configurer les autorisations

À l'aide des GPO, les administrateurs peuvent définir les

d'accès aux imprimantes, en accordant ou en

paramètres d'impression par défaut, tels que le format

restreignant l'accès à certains utilisateurs ou groupes.
Cela aide à sécuriser l'environnement et à éviter les

de papier, l'orientation, la qualité d'impression, etc. Cela
permet d'assurer une uniformité dans l'environnement

impressions non autorisées.

et de réduire les coûts d'impression.

Gestion des paramètres de dossiers avec
les GPO

—

—

—

Paramètres de dossiers

Redirection de dossiers

Paramètres d'accès

Les GPO permettent de configurer de

La redirection de dossiers utilisateur

Les administrateurs peuvent

nombreux paramètres liés aux
dossiers, tels que les emplacements

est une fonctionnalité clé des GPO
qui permet de stocker les dossiers

également utiliser les GPO pour
définir les paramètres d'accès et de

des dossiers personnels, les scripts

personnels des utilisateurs sur un

sécurité sur les dossiers réseau, afin

de connexion/déconnexion, les
paramètres de partage et de sécurité

serveur central plutôt que sur leurs
postes de travail. Cela facilite la

de contrôler qui peut accéder aux
fichiers et dossiers et quelles sont les

sur les dossiers réseau, ainsi que la

sauvegarde, le déploiement et l'accès

autorisations accordées.

redirection des dossiers utilisateur.

à distance aux données.

