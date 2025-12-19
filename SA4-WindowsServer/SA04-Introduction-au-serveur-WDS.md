Introduction au serveur WDS
Un serveur WDS, ou Windows Deployment Services, est un outil intégré à Windows Server qui permet de déployer des
images de système d'exploitation sur des ordinateurs clients. Il est principalement utilisé pour les déploiements à
grande échelle, comme dans les entreprises ou les écoles, pour installer ou mettre à jour des systèmes d'exploitation
sur plusieurs ordinateurs simultanément.
Le serveur WDS fonctionne en créant une image de système d'exploitation (un fichier .WIM) qui contient tous les fichiers
nécessaires pour installer Windows. Cette image peut être déployée sur des clients via le réseau. Le serveur WDS peut
également gérer les pilotes et les mises à jour pour les clients, garantissant ainsi que tous les ordinateurs sont mis à jour
avec les derniers pilotes et correctifs.

Avantages du serveur WDS

—

—

Gain de temps

Sécurité accrue

Le serveur WDS permet de déployer rapidement et

En utilisant un serveur WDS, vous pouvez contrôler les

efficacement des systèmes d'exploitation et des

images de déploiement et vous assurer que tous les

applications sur plusieurs ordinateurs. Il permet de
réduire le temps nécessaire à la configuration manuelle

ordinateurs reçoivent les mêmes paramètres de sécurité.
Cela permet de limiter les risques de configuration

de chaque appareil, ce qui optimise la productivité.

incorrecte ou d'exposition à des vulnérabilités.

—

—

Réduction des coûts

Gestion centralisée

Le serveur WDS permet de centraliser le déploiement et la

Le serveur WDS simplifie la gestion du réseau en

gestion des images, réduisant ainsi le besoin de
personnel informatique spécialisé pour chaque tâche.

permettant de contrôler et de mettre à jour les systèmes
d'exploitation et les applications de tous les ordinateurs

Cela permet de réaliser des économies importantes à

depuis un point central. Cela permet de gagner du temps

long terme.

et de garantir une cohérence dans l'ensemble du réseau.

Création d'une image de déploiement
Choisir un système d'exploitation

1

Sélectionnez la version de Windows que vous souhaitez déployer. Assurez-vous que cette version est
compatible avec les ordinateurs clients. Vous pouvez choisir Windows 10, 11 ou une version serveur.

Personnaliser l'image

2

Ajoutez des applications, des pilotes et des paramètres spécifiques à votre environnement. Vous pouvez
personnaliser l'image en fonction des besoins de votre entreprise ou de votre organisation.

Capturer l'image

3

Utilisez l'outil de capture d'image de WDS pour créer une image du système d'exploitation. La capture
de l'image crée un fichier WIM qui contient tous les fichiers et les paramètres du système d'exploitation.

Enregistrer l'image

4

Enregistrez l'image capturée sur le serveur WDS. Vous pouvez enregistrer l'image dans un dossier dédié
ou sur un lecteur partagé. Assurez-vous que l'image est stockée dans un emplacement sécurisé.

Déploiement d'une image sur les clients
Choisir l'image

1

Sélectionnez l'image de déploiement créée
précédemment. Assurez-vous qu'elle est
compatible avec les clients cibles.

2

Configurer WDS
Configurez le serveur WDS pour pointer vers

Démarrer le déploiement

3

Lancez le processus de déploiement sur les
clients. Le serveur WDS démarrera
automatiquement le processus de boot et
d'installation.

Une fois le déploiement lancé, WDS gère
l'ensemble du processus de boot et
d'installation. Il charge les pilotes nécessaires,
installe le système d'exploitation et configure
les paramètres réseau. Le serveur WDS
garantit un processus de déploiement
automatique et efficace sur tous les clients.

4

l'image de déploiement sélectionnée.
Définissez les options de déploiement, comme
le mode de démarrage.

Surveiller le déploiement
Surveillez l'état du déploiement en temps réel.

5

Vérifiez les logs pour identifier et résoudre les
erreurs éventuelles.

Gestion des pilotes et des mises à jour

—

—

—

Gestion des pilotes

Mises à jour automatiques

Intégration avec WSUS

Le serveur WDS permet de gérer les
pilotes de périphériques pour les

Le serveur WDS peut également être
configuré pour télécharger et

Pour une gestion plus avancée des
mises à jour, le serveur WDS peut

ordinateurs clients. Il peut stocker et

distribuer automatiquement les

être intégré à Windows Server

distribuer les pilotes nécessaires
pour une variété de périphériques,

mises à jour Windows aux
ordinateurs clients. Cela permet de

Update Services (WSUS). WSUS
permet de contrôler les mises à jour

tels que les cartes réseau, les

maintenir les systèmes clients à jour

qui sont déployées aux clients et de

imprimantes, les scanners et les

avec les dernières correctifs de

planifier les déploiements.

cartes graphiques.

sécurité et améliorations.

Intégration avec Active Directory

—

—

—

Authentification
centralisée

Gestion des politiques de
groupe

Gestion des images

Le serveur WDS peut être intégré à

Les politiques de groupe peuvent

Active Directory pour fournir une
authentification centralisée aux

être utilisées pour configurer les
paramètres du serveur WDS et des

clients. Cela permet de simplifier la

clients. Cela permet d'appliquer des

gestion des mots de passe et des

configurations uniformes aux clients,

comptes d'utilisateurs. Les
administrateurs peuvent gérer les

telles que les paramètres de sécurité,
les paramètres du réseau et les

comptes d'utilisateurs et les

paramètres logiciels.

Active Directory peut être utilisé pour
connaissances Microsoft et les ressources de la communauté.

des clients.
central.

<h1 align=center>Introduction au serveur WDS</h1>

Outil de déploiement d'images Windows pour installations à grande échelle et gestion centralisée.

---

# Présentation générale

Le serveur WDS (Windows Deployment Services) permet de déployer des images de système d'exploitation sur des ordinateurs clients via le réseau. Il est utilisé pour installer ou mettre à jour des systèmes d'exploitation sur plusieurs ordinateurs simultanément (entreprises, écoles, etc.).

WDS gère également les pilotes et mises à jour pour garantir que tous les ordinateurs sont à jour.

---

# Avantages du serveur WDS

- Gain de temps : déploiement rapide et efficace des systèmes d'exploitation et applications
- Sécurité accrue : contrôle des images de déploiement et uniformisation des paramètres de sécurité
- Réduction des coûts : centralisation du déploiement et gestion des images, moins de personnel spécialisé nécessaire
- Gestion centralisée : contrôle et mise à jour des systèmes d'exploitation et applications depuis un point central

4

2

Déploiement
automatisé
WDS peut automatiser le

3

Évolutivité
WDS peut gérer des milliers de
clients simultanément.

processus de déploiement des
images sur les clients.

Sécurité renforcée
WDS intègre des fonctionnalités de sécurité pour protéger les images et les données.

Les organisations peuvent utiliser WDS pour déployer des images sur des centaines ou des milliers d'ordinateurs en
même temps. La gestion centralisée des images et des mises à jour permet de garantir la cohérence et la sécurité de
l'environnement informatique.

Personnalisation de l'environnement de
déploiement
Configurer les paramètres du système

Personnaliser l'image de déploiement

Vous pouvez personnaliser l'environnement de
déploiement en configurant des paramètres spécifiques

L'image de déploiement peut être personnalisée avec
des logiciels, des pilotes et des configurations

au système d'exploitation. Cela inclut la modification

spécifiques. Vous pouvez inclure des applications et des

des paramètres de sécurité, l'installation des
applications et la configuration des paramètres réseau.

paramètres spécifiques aux utilisateurs, ce qui permet
de créer un environnement de travail personnalisé. Vous

Vous pouvez également utiliser des scripts pour

pouvez également utiliser des outils de gestion de

automatiser ces tâches.

l'image pour créer des images personnalisées.

