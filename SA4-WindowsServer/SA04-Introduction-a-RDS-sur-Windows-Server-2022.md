Accès Web aux bureaux à
Licence des bureaux à
Passerelle des bureaux à
bureau à distance (RD Session Host). Le client RDC est inclus avec le système d'exploitation Windows et est également
bureau distant. Il affiche la bande passante avec une icône sur la barre de connexion, similaire à un indicateur de force

<h1 align=center>Introduction à RDS sur Windows Server 2022</h1>

Technologie d'accès distant aux applications et bureaux Windows, avec gestion centralisée et sécurité renforcée.

---

# Présentation générale

RDS (Services de Bureau à Distance) permet aux utilisateurs d'accéder à des applications et bureaux Windows depuis n'importe quel appareil. Windows Server 2022 apporte de nouvelles fonctionnalités, une sécurité accrue et une gestion simplifiée.

---

# Fonctionnement de RDS

Les RDS sont un rôle serveur Windows offrant bien plus que de simples bureaux à distance. Ils comprennent :
- Hôte de session RD (RD Session Host)
- Hôte de virtualisation de bureau à distance (RD Virtualization Host)
- Broker de connexion RD (RD Connection Broker)
- Accès Web aux bureaux à distance (RD Web Access)
- Licence des bureaux à distance (RD Licensing)
- Passerelle des bureaux à distance (RD Gateway)

**Important** : Plusieurs utilisateurs peuvent accéder à un bureau virtuel ou à leur propre machine virtuelle (VDI), en pool ou dédié.

Le client RDC (Remote Desktop Client) est inclus avec Windows et disponible pour d'autres plateformes (Android, iOS, macOS). Il détecte la qualité de connexion et affiche la bande passante disponible.
du signal.

Avantages de RDS pour les entreprises
Réduction des coûts

Amélioration de la sécurité

RDS permet aux entreprises de réduire leurs coûts

RDS centralise la gestion des accès aux

d'infrastructure en consolidant les serveurs et les
logiciels. Il offre également une flexibilité accrue,

applications, permettant aux administrateurs
d'appliquer des politiques de sécurité strictes et de

permettant aux employés d'accéder aux

suivre les activités des utilisateurs. Il permet

applications et données à partir de n'importe quel

également de réduire les risques liés à la perte de

appareil, réduisant ainsi le besoin d'acheter des
ordinateurs portables coûteux.

données et aux accès non autorisés.

Augmentation de la productivité

Meilleure collaboration

En permettant aux utilisateurs d'accéder aux

RDS facilite la collaboration en permettant aux

applications et aux données à partir de n'importe
quel appareil, RDS améliore la productivité des

équipes de partager des applications et des
données de manière centralisée. Les utilisateurs

employés. Il permet également de simplifier les

peuvent accéder aux mêmes fichiers et travailler

mises à jour et les maintenances, minimisant les
interruptions de service.

simultanément, améliorant ainsi la communication
et la productivité.

Déploiement RDS
Vous devez ensuite décider entre des déploiements de bureau basés sur une session ou sur une machine virtuelle (VM).
(Si nécessaire, un déploiement RDS peut inclure à la fois des déploiements de bureau basés sur une session et sur une
VM.)
Les RDS offrent deux types de déploiements :
Déploiement de bureau basé sur une session. Ce type de déploiement permet aux utilisateurs de se connecter à un
hôte de session de bureau à distance (RD Session Host), et d'utiliser soit une expérience de bureau complète, soit
d'exécuter des applications à distance et de les présenter comme si elles étaient installées localement.
Déploiement de bureau basé sur une VM. Ce type de déploiement fournit aux utilisateurs un accès à un système
d'exploitation client complet (OS) - tel que Windows 10 - qui fonctionne sur une VM.
Déterminez les exigences matérielles du serveur et les ressources réseau Déterminez comment les clients accèdent aux
RDS

Création de collections de serveurs et de bureaux
Créez des collections de serveurs pour regrouper les serveurs RDS et des collections de bureaux pour définir les images
de bureau qui seront utilisées par les utilisateurs. Configurez les paramètres de sécurité, tels que l'authentification et
l'autorisation, pour contrôler l'accès aux bureaux à distance.

HÔTE DE SESSION RD
L'hôte de session RD est un service de rôle qui héberge des programmes basés sur Windows ou des bureaux Windows
complets pour les clients RDS. Ce service de rôle est obligatoire pour chaque déploiement RDS qui fournit aux
utilisateurs des bureaux basés sur des sessions avec des bureaux Windows complets ou avec le programme RemoteApp.
Un serveur d'hôte de session RD accepte les connexions des utilisateurs et exécute des programmes. Pour utiliser un
serveur d'hôte de session RD, vous devez tenir compte du nombre d'applications installées et de leurs types, de
l'utilisation des ressources, du nombre de clients connectés et du type d'interaction utilisateur.
La planification de l'hôte de session RD se concentre sur le nombre d'utilisateurs simultanés et la charge de travail qu'ils
génèrent.

ACCÈS WEB RD
L'accès Web RD est le service de rôle RDS qui fournit un portail web unique où les bureaux distants disponibles, les
programmes RemoteApp et les bureaux virtuels sont affichés. Vous pouvez accéder à l'accès Web RD depuis n'importe
quel navigateur web. Lorsque vous sélectionnez une ressource RDS, le fichier .rdp se télécharge et RDC l'ouvre
automatiquement.
L'accès Web RD peut également publier une liste des ressources RDS disponibles sous forme de flux web RDWeb qui
peut s'intégrer au menu Démarrer de Windows. Le service de rôle d'accès Web RD est une partie obligatoire de chaque
déploiement RDS, et il installe le rôle de serveur web et les services Internet (IIS) en tant que prérequis.

Gestion des sessions et des connexions

—

—

Gestion des sessions

Contrôle d'accès

RDS permet aux administrateurs de contrôler les sessions

Les administrateurs peuvent configurer des autorisations

des utilisateurs à distance. Ils peuvent voir les

d'accès pour les utilisateurs, les groupes et les

applications en cours d'exécution, les ressources utilisées
et les actions effectuées. Cela est utile pour le dépannage,

applications. Ils peuvent limiter l'accès aux applications
spécifiques, aux heures d'accès et aux ressources

la sécurité et le suivi des performances.

système.

—

—

Fonctionnalités de connexion

Prise en charge des appareils

RDS offre une variété d'options de connexion, telles que

RDS est compatible avec une large gamme d'appareils,

RDP, les connexions Web et les applications publiées. Les
utilisateurs peuvent accéder à leurs bureaux et

notamment les ordinateurs portables, les tablettes et les
smartphones. Les utilisateurs peuvent se connecter à

applications à distance depuis n'importe quel appareil.

leurs bureaux à distance et accéder à leurs applications à
partir de n'importe quel appareil.

Intégration avec d'autres services
Microsoft
RDS s'intègre de manière transparente avec d'autres services Microsoft tels que Azure Active Directory (Azure AD) pour
l'authentification et l'autorisation des utilisateurs, Azure Monitor pour la surveillance et la gestion des performances, et
Microsoft Intune pour la gestion des appareils. Cela permet une gestion centralisée et simplifie les opérations pour les
administrateurs.
L'intégration avec Azure AD permet de gérer les identités et les accès des utilisateurs de manière centralisée, offrant une
expérience utilisateur cohérente. Azure Monitor permet de surveiller les performances et la disponibilité des serveurs
RDS, tandis qu'Intune permet de gérer les configurations et les mises à jour des appareils clients. En tirant parti de ces
synergies, les organisations peuvent améliorer la sécurité, la fiabilité et la gestion globale de leur infrastructure RDS.

Haute disponibilité et reprise après
sinistre

—

—

Résilience des services

Profil itinérant

RDS sur Windows Server 2022 offre des fonctionnalités de

RDS sur Windows Server 2022 prend en charge les profils

haute disponibilité pour garantir la continuité des
services. La mise en cluster des serveurs RDS permet de

itinérants, ce qui permet aux utilisateurs de conserver
leurs paramètres et leurs données personnelles lorsqu'ils

maintenir les services opérationnels en cas de panne d'un

se connectent à différents appareils. De cette façon, les

serveur. Les options de basculement automatique et de
réplication de données garantissent un temps d'arrêt

utilisateurs peuvent accéder à leur environnement de
travail personnalisé et familier, peu importe où ils se

minimal.

trouvent. Cela facilite la mobilité des utilisateurs et
améliore leur productivité.

PROFILS
Vous pouvez configurer un utilisateur avec deux profils. Ils utilisent un profil utilisateur standard lorsqu'ils se
connectent localement avec leur profil utilisateur RDS. Un second profil est utilisé lorsque l'utilisateur se connecte à un
Hôte de Session RD.
Créer les deux profils pour un utilisateur leur permet d'avoir deux états d'utilisateur différents et indépendants. Pour les
utilisateurs itinérants, ces profils doivent être stockés sur un serveur de fichiers tolérant aux pannes. Lorsque
l'utilisateur se déconnecte, toutes les données de profil peuvent être supprimées du serveur Hôte de Session RD.
Cependant, pour fournir une expérience de connexion fluide, les profils d'utilisateur itinérants peuvent être mis en
cache localement sur un serveur Hôte de Session RD.
Disque de profil utilisateur
Les disques de profil utilisateur sont utilisés dans les sessions basées sur une session ou sur une VM, pour isoler les
données utilisateur et les données d'application pour chaque utilisateur dans un fichier .vhdx séparé. Ce fichier doit
être stocké sur un emplacement réseau. Lorsqu'un utilisateur se connecte à un Hôte de Session RD pour la première
fois, son disque de profil utilisateur est créé et monté dans le chemin de profil de l'utilisateur, C:\Users\%username%.
Pendant la session de l'utilisateur, toutes les modifications apportées au profil sont écrites dans le fichier .vhdx de
l'utilisateur, et lorsque l'utilisateur se déconnecte, son disque de profil est démonté.
Redirection de dossier
Vous pouvez utiliser la redirection de dossier pour changer l'emplacement cible de dossiers spécifiques dans le profil
d'un utilisateur, d'un disque dur local à un emplacement réseau.

Gateway RD
Les Services de Bureau à Distance (RDS) peuvent fournir un environnement standardisé pour les utilisateurs qui se
connectent à un réseau interne. Cependant, de nombreux utilisateurs ont besoin d'accéder à leurs environnements
lorsqu'ils ne sont pas connectés à un réseau interne, par exemple, lorsqu'ils travaillent à domicile ou voyagent pour
affaires.
Pas besoin d'installer un VPN : Fournit une connectivité sécurisée depuis un réseau public.
La passerelle RD doit avoir une connectivité à la fois avec un réseau interne et un réseau public pour pouvoir faire office
de proxy et inspecter le trafic RDP.
Un déploiement plus sécurisé consiste à placer la passerelle RD dans un réseau périmétrique. Dans cette conception, la
passerelle RD écoute le trafic HTTPS sur l'interface orientée vers Internet, et le trafic RDP sur le réseau local (LAN).
La Gateway RD est un service de rôle RDS optionnel.

Licences du RDS
Si vous souhaitez utiliser les Services de Bureau à Distance (RDS), vous devez correctement licencier tous les clients qui
se connectent aux RDS. Chaque client doit d'abord avoir une licence pour le système d'exploitation installé localement
(OS). Chaque client doit également être licencié pour utiliser la Licence d'Accès Client des Services de Bureau à Distance
de Windows Server (CAL RDS).
Enfin, vous devez obtenir une CAL RDS, qui permet à un client de se connecter à un déploiement de bureau basé sur une
session de RDS.
Après avoir installé les RDS, vous disposez d'une période de grâce initiale de 120 jours avant de devoir installer la CAL
valide.
La gestion des licences de bureau à distance (Licence RD) gère les CAL RDS requises pour chaque appareil ou utilisateur
pour se connecter à un serveur Hôte de Session RD.
Par utilisateur (Ce mode de licence donne à un utilisateur le droit d'accéder à n'importe quel serveur Hôte de Session
RD dans un déploiement RDS à partir d'un nombre illimité d'ordinateurs clients ou d'appareils).
Par appareil (Ce mode de licence donne à tout utilisateur le droit de se connecter à n'importe quel serveur Hôte de
Session RD dans un déploiement RDS à partir d'un appareil spécifique).

Outils de surveillance et de reporting
Surveillance en temps
réel

Rapports détaillés

Les outils de surveillance en

une vue d'ensemble complète
des performances du serveur

temps réel offrent des
informations précieuses sur la
santé et les performances du
serveur RDS. Ils suivent les
métriques clés telles que
l'utilisation du processeur, la
mémoire, le stockage et les
connexions. Les alertes sont
déclenchées en cas de
problèmes potentiels,
permettant une intervention
rapide et une minimisation des
temps d'arrêt.

Les rapports détaillés fournissent

RDS au fil du temps. Ils analysent
les tendances d'utilisation,
identifient les goulets
d'étranglement et aident à
optimiser la configuration. Ces
rapports peuvent être utilisés

Outils d'analyse
avancés
Des outils d'analyse avancés
permettent une compréhension
approfondie des performances
du serveur RDS. Ils identifient les
tendances d'utilisation, les
modèles de comportement et les
anomalies. Ces informations

pour améliorer les performances,

aident à prendre des décisions
éclairées pour optimiser les

la sécurité et la conformité.

ressources et améliorer
l'expérience utilisateur.

Scénarios d'utilisation de RDS
Travail à distance

1

RDS permet aux employés d'accéder à leurs
applications et bureaux depuis n'importe où,
avec une connexion internet. Cela améliore la
flexibilité du travail et réduit les coûts

2

Les hôpitaux et les cliniques utilisent RDS

d'infrastructure.

Éducation

Soins de santé
pour fournir aux médecins et aux infirmières

3

un accès sécurisé aux dossiers médicaux et
aux applications médicales, optimisant ainsi
la coordination des soins.

Les universités utilisent RDS pour fournir aux
étudiants un accès aux applications et
logiciels académiques, sans avoir à installer
ces applications sur leurs appareils
personnels.

4

Développement logiciel
Les équipes de développement utilisent RDS
pour accéder à des environnements de
développement et de test, simplifiant ainsi la
collaboration et la gestion des versions.

