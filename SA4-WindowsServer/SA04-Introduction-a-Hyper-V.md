Introduction à Hyper-V
Hyper-V est un hyperviseur de Microsoft. Il permet de créer des machines virtuelles pour exécuter différents systèmes
d'exploitation sur un seul ordinateur physique. Hyper-V est disponible sur les versions serveur et client de Windows.

Qu'est-ce qu'Hyper-V ?
Hyper-V est une solution de virtualisation développée par Microsoft. Elle permet de créer des machines virtuelles (VM)
qui fonctionnent sur un système d'exploitation hôte.
Hyper-V est une technologie mature et performante qui offre un large éventail de fonctionnalités. Elle est intégrée aux
systèmes d'exploitation Windows Server et Windows 10/11.
L'une des fonctionnalités clés d'Hyper-V est la capacité de gérer plusieurs machines virtuelles sur un seul serveur
physique, ce qui permet une utilisation efficace des ressources matérielles. De plus, Hyper-V offre une isolation
complète entre chaque machine virtuelle, garantissant ainsi la sécurité et la stabilité de chaque environnement
d'exécution. Cette technologie de virtualisation est utilisée par de nombreuses organisations pour consolider leurs
infrastructures et réduire les coûts de maintenance.

Avantages d'Hyper-V
Virtualisation de serveur

Hyper-V permet de virtualiser des serveurs, offrant

intégration étroite avec d'autres produits Microsoft tels que System Center, ce qui facilite la gestion et la surveillance
Types de machines virtuelles


<h1 align=center>Introduction à Hyper-V</h1>

Hyperviseur Microsoft pour la virtualisation de serveurs et la gestion centralisée de machines virtuelles.

---

# Présentation générale

Hyper-V est un hyperviseur développé par Microsoft, disponible sur Windows Server et Windows 10/11. Il permet de créer et gérer des machines virtuelles (VM) sur un seul ordinateur physique.

**Point clé** : Hyper-V offre une isolation complète entre chaque VM, garantissant sécurité et stabilité.

---

# Avantages d'Hyper-V

- Virtualisation de serveurs pour une meilleure utilisation des ressources physiques
- Réduction des coûts matériels et de maintenance
- Sécurité accrue (protection contre les attaques "Zero-day")
- Fiabilité améliorée (réduction des temps d'arrêt)

---

# Architecture Hyper-V

Hyper-V utilise une architecture basée sur un hyperviseur de type 1 (s'exécutant directement sur le matériel physique). Les machines virtuelles fonctionnent au-dessus de l'hyperviseur, avec leurs propres systèmes d'exploitation et applications.

Fonctionnalités avancées :
- Virtualisation du processeur, de la mémoire et du stockage
- Migration en direct des VM entre hôtes sans interruption de service
- Intégration avec System Center pour la gestion centralisée

---

# Machines virtuelles Hyper-V

Hyper-V permet de créer des machines virtuelles facilement, en utilisant des assistants et des outils intégrés.
de l'OS invité est essentielle pour assurer un fonctionnement optimal.

4

Gestion des machines virtuelles
Hyper-V fournit des outils de gestion robustes pour contrôler les machines virtuelles, y compris le
démarrage, l'arrêt, la sauvegarde et la restauration. Les utilisateurs peuvent surveiller l'état et les
performances des machines virtuelles.

Gestion des machines virtuelles

—

—

Démarrage et arrêt

Configuration

Contrôler le cycle de vie des machines virtuelles.

Configurer les paramètres et les ressources.

—

—

Surveillance

Sauvegarde et restauration

Surveiller les performances et la santé.

Créer des instantanés et restaurer les données.

Hyper-V offre une interface intuitive pour gérer les machines virtuelles. Vous pouvez facilement les démarrer, les arrêter,
les configurer, les surveiller, les sauvegarder et les restaurer.
De plus, Hyper-V permet également de gérer les paramètres et les ressources associés aux machines virtuelles. Vous
pouvez configurer la mémoire allouée, les disques virtuels, les réseaux virtuels, etc. Pour assurer une performance
optimale, il est essentiel de surveiller régulièrement les performances et la santé des machines virtuelles. En utilisant
les outils de surveillance intégrés d'Hyper-V, vous pouvez identifier les goulots d'étranglement potentiels et prendre des
mesures appropriées pour les résoudre.
Il est également important de mettre en place des stratégies de sauvegarde régulières pour prévenir toute perte de
données. Hyper-V offre la possibilité de créer des instantanés (snapshots) de machines virtuelles, ce qui permet de
capturer un état précis de la machine à un moment donné. En cas de problème, vous pouvez facilement restaurer les
données à partir de ces instantanés pour revenir à un état antérieur et minimiser les pertes.

Réseaux virtuels Hyper-V

—

—

—

Isolation et sécurité

Connectivité flexible

Types de connexions

Les réseaux virtuels Hyper-V

Les réseaux virtuels peuvent être

Hyper-V offre différents types de

permettent d'isoler les machines

connectés à des réseaux physiques,

connexions de réseau virtuel, tels

virtuelles les unes des autres, en
créant des segments de réseau

permettant aux machines virtuelles
d'accéder à des ressources externes

que les réseaux privés virtuels (VPN)
et les connexions à distance, pour

distincts pour améliorer la sécurité et

et d'interagir avec le monde réel.

répondre aux besoins spécifiques.

la confidentialité.
Hyper-V propose différents types de réseaux virtuels pour permettre la communication entre les machines virtuelles :
Tout d'abord, les réseaux internes permettent la communication uniquement entre les machines virtuelles au sein du
même hôte Hyper-V. Cela permet d'isoler le trafic réseau et d'assurer la sécurité des communications entre les VM.
Ensuite, les réseaux privés virtuels permettent aux machines virtuelles de communiquer en toute sécurité avec d'autres
machines virtuelles hébergées sur des hôtes Hyper-V distants. Cela permet d'étendre le réseau virtuel au-delà d'un seul
hôte.
Enfin, les réseaux externes permettent aux machines virtuelles de se connecter aux réseaux physiques, offrant ainsi une
connectivité avec l'extérieur. Cela permet aux VM d'accéder à des ressources réseau externes, comme Internet ou
d'autres systèmes.

Conversion Réseau HyperV par rapport
aux modes Virtualbox
NAT (Network
Address
Translation)

Réseau Bridged

Réseau Interne

Réseau Hôte-Seul

Le mode Bridged de
VirtualBox connecte

VirtualBox permet de
créer des réseaux

Le mode Hôte-Seul de
VirtualBox connecte une

Sous VirtualBox, le mode

directement les

internes isolés entre les

VM uniquement à l'hôte.

NAT permet aux
machines virtuelles de

machines virtuelles au
réseau physique, leur

machines virtuelles.
Hyper-V dispose de

Hyper-V propose une
configuration

partager la connexion

attribuant une adresse IP

réseaux internes

équivalente avec les

réseau de l'hôte. Hyper-V
offre une fonctionnalité

distincte. Hyper-V
propose une

similaires, permettant
une communication

réseaux privés virtuels,
permettant une

similaire avec le réseau

configuration

sécurisée entre les VM

connectivité restreinte

interne, permettant aux
VM d'accéder à Internet

équivalente avec le
réseau externe, offrant

sans accès à l'extérieur.

entre les VM et l'hôte.

via l'adresse IP de l'hôte.

une connectivité directe
au réseau local.

Stockage Hyper-V
Hyper-V offre une variété d'options de stockage pour les machines virtuelles, notamment les disques durs virtuels
(VHDX) et les disques durs virtuels (VHD).
Les disques durs virtuels peuvent être stockés localement sur l'hôte Hyper-V ou sur des partages de fichiers réseau.
Hyper-V prend également en charge le stockage partagé, qui permet à plusieurs hôtes Hyper-V de partager le même
stockage.
Ce stockage partagé peut être réalisé en utilisant des protocoles tels que iSCSI ou Fibre Channel. Il permet une
meilleure utilisation des ressources de stockage et facilite la migration des machines virtuelles d'un hôte Hyper-V à un
autre. De plus, Hyper-V offre également la possibilité d'utiliser des disques durs virtuels en cluster, ce qui améliore la
disponibilité et la résilience du stockage pour les machines virtuelles.

Haute disponibilité et reprise après
sinistre
Haute Disponibilité

Reprise après sinistre

Hyper-V offre des fonctionnalités de haute disponibilité

Les fonctionnalités de reprise après sinistre d'Hyper-V

pour garantir la continuité des services. Les clusters de

permettent de restaurer rapidement les machines

serveurs Hyper-V permettent la redondance et la bascule
automatique en cas de panne d'un nœud.

virtuelles en cas de catastrophe. La sauvegarde et la
restauration des machines virtuelles vers un site
secondaire assurent une reprise rapide des opérations.

Sécurité Hyper-V
Isolation

Authentification et
Autorisation

Protection contre les
Malware

du système hôte pour empêcher

Contrôle d'accès strict aux
ressources Hyper-V pour garantir

Hyper-V offre des fonctionnalités
de sécurité intégrées pour

les attaques.

que seuls les utilisateurs

détecter et bloquer les logiciels

autorisés peuvent y accéder.

malveillants.

Hyper-V isole les machines
virtuelles les unes des autres et

Sauvegarde et Restauration
Des sauvegardes régulières des machines virtuelles permettent de restaurer les données en cas d'attaque.

Outils de gestion Hyper-V

—

—

Gestionnaire de serveur

Gestionnaire de machines virtuelles

Le Gestionnaire de serveur fournit une interface
graphique pour gérer les rôles et fonctionnalités du

Le Gestionnaire de machines virtuelles permet de créer,
de démarrer, d'arrêter et de gérer les machines virtuelles.

serveur.

—

—

Windows PowerShell

Surveillance

Windows PowerShell fournit des cmdlets pour

Les outils de surveillance permettent de surveiller la

automatiser les tâches de gestion Hyper-V.

performance des machines virtuelles et du serveur HyperV.

Déploiement et configuration Hyper-V
1

Choix du matériel
Sélectionner un serveur avec les ressources nécessaires (CPU, RAM, stockage) en fonction des besoins
de virtualisation.

2

Installation du système d'exploitation
Installer Windows Server avec les fonctionnalités Hyper-V activées, y compris le rôle gestionnaire
Hyper-V.

3

Configuration de l'environnement Hyper-V
Configurer les paramètres de virtualisation, les réseaux virtuels, le stockage et les options de sécurité.

4

Création de machines virtuelles
Créer des machines virtuelles à partir de modèles ou d'images ISO en définissant les ressources et les
paramètres de chaque VM.

5

Déploiement d'applications et de systèmes d'exploitation
Installer les systèmes d'exploitation et les applications souhaités sur les machines virtuelles et les
configurer.

Cas d'utilisation et meilleures pratiques
Virtualisation de
serveurs

Déploiement
d'applications

Gestion des
postes de travail

Hyper-V est idéal pour

Hyper-V facilite le

Hyper-V permet de créer

virtualiser des serveurs.
Cela permet de

déploiement
d'applications critiques,

des environnements de
poste de travail virtuels

d'environnements cloud

consolider des serveurs

de développement et de

pour les utilisateurs

physiques sur un seul
serveur physique,

test, et de scénarios de
haute disponibilité.

distants ou pour tester
des logiciels dans un

machines virtuelles
locales à des services

réduisant les coûts
d'infrastructure et
d'énergie.

environnement isolé.

Cloud hybride
Hyper-V prend en charge
la création
hybrides, reliant des

cloud.

