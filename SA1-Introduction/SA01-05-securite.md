<h1 align=center>Sécurité</h1>

Introduction aux fondamentaux de la sécurité informatique, bonnes pratiques, acteurs et concepts clés.

---

# Introduction / Bonnes pratiques

La sécurité informatique concerne tout le monde, pas seulement les experts. Toutes les entreprises n'ont pas les moyens d'embaucher un expert, et en freelance, il faut s'en occuper soi-même.

- **La sécurité est l'affaire de tous**
- **Toutes les entreprises ne peuvent pas embaucher un expert**
- En freelance, il faut gérer soi-même ou sous-traiter

## Pourquoi se soucier de la sécurité ?

- La sécurité concerne tout le monde
- Les entreprises n'ont pas toujours les moyens d'embaucher un expert
- En freelance, on doit s'en occuper soi-même

## Objectifs pédagogiques

- Connaître les bonnes pratiques de sécurité
- Sensibiliser les utilisateurs
- Respecter la charte/règles de sécurité
- Prendre en compte la sécurité lors des interventions
- Connaître les acteurs de la sécurité informatique

---

# Intérêt de la sécurité informatique

Dans une société hyper-connectée, de nombreux aspects de la vie dépendent du bon fonctionnement des infrastructures informatiques.

- Déclarer ses revenus, payer ses impôts
- Prendre rendez-vous chez le médecin
- Faire ses courses en ligne
- Stocker des photos de famille
- Communiquer avec ses proches

**Important :** La sécurité de ces systèmes est primordiale pour éviter la divulgation ou la perte de données.

**Attention :** Les conséquences d'une attaque peuvent être plus graves qu'une simple fuite de données.

## Exemple marquant

- Stuxnet : attaque informatique célèbre

---

# Critères de la sécurité informatique

La sécurité d'un système s'évalue selon plusieurs critères.

## Intégrité

Garantir qu'une donnée n'a pas été modifiée à l'insu du système.

## Confidentialité

Seules les personnes autorisées doivent accéder à une donnée spécifique.

## Authentification / Authenticité

Le système doit identifier avec certitude un utilisateur.

- Identifiant unique (email, nom d'utilisateur)
- Facteur d'authentification (mot de passe, empreinte digitale)

## Disponibilité

Un système disponible est fonctionnel, accessible et utilisable.

## Non-répudiation / Traçabilité / Preuve

Empêcher qu'un utilisateur puisse nier une transaction.

- Conservation de preuves
- Traçabilité des transactions

---

# Métiers de la sécurité informatique

Il existe de nombreux métiers dans ce domaine.

## Cryptologue

Mathématicien spécialisé dans la cryptologie, conçoit et analyse les algorithmes et protocoles cryptographiques.

## DSSI / RSSI

Directeur ou Responsable de la Sécurité des Systèmes d'Information.

- Responsable de la sécurité du SI
- Recommandé que ce ne soit pas le DSI

## Auditeur / Pentester

Expert technique réalisant des audits de sécurité (tests d'intrusion).

- Identifier les vulnérabilités avant les hackers

## DPO

Data Protection Officer, chargé du respect du RGPD.

- Mobilisé en cas de fuite de données personnelles

## Expert sécurité

- Administrateur système/réseau spécialisé en sécurité
- Développeur spécialisé en sécurité

## Consultant / Formateur

- Consultants en conseil/accompagnement
- Formateurs en sécurité informatique

---

# Grands principes de la cybersécurité

Quelques principes essentiels à garder en tête.

## Menace principale

**La plus grande menace est l'utilisateur.**

- Mal-intentionné ou distrait, il reste un risque majeur

## Privilège minimum

Chaque groupe, service, utilisateur doit avoir uniquement accès à ce qui est strictement indispensable.

## Défense en profondeur

La sécurité doit être organisée en plusieurs niveaux indépendants.

- Si un niveau est compromis, le suivant doit bloquer l'attaque

## Être paranoïaque

Être suspicieux : si quelque chose semble suspect, c'est probablement le cas.

## Sécurité absolue ?

**La sécurité absolue n'existe pas.**

- Il faut faire des compromis entre sécurité et fonctionnalité
- Préparer des PRA/PCA, faire des sauvegardes

## Composant le plus faible

La sécurité d'un système est égale à celle de son composant le plus faible.

## Secure by design

Penser à la sécurité dès la conception du projet.

- Les choix technologiques précoces impactent la sécurité

## Loi de Murphy

"Tout ce qui est susceptible d'aller mal ira mal."

- Concevoir les applications comme si cette loi était vraie

---

# Acteurs de la sécurité informatique

Présentation des principaux organismes et acteurs.

## ANSSI

Agence Nationale de la Sécurité des Systèmes d’Information.

- Service gouvernemental français
- Publie recommandations, gère le CERT-FR

## CSIRT / CERT

Équipes d’experts chargées de réagir en cas d’incident informatique.

- CERT-FR publie des alertes de sécurité

## CVE / MITRE

MITRE publie le dictionnaire CVE (Common Vulnerabilities and Exposures).

- CVE : vulnérabilité référencée
- Criticité évaluée par le CVSS

## CNIL

Commission Nationale Informatique & Libertés.

- Veille au respect du RGPD et de la loi Informatique et Libertés
- Peut prononcer des sanctions
- Notification obligatoire en cas de fuite de données personnelles

## OWASP

Organisation spécialisée dans la sécurité des applications web.

- Top10 : liste des dix risques majeurs
- ZAP : outil de scan de failles web
- WSTG : guide de tests de sécurité web
- Cheat Sheet Series : mémos sécurité web
- ASVS : standard de vérification sécurité applicative

---

# Les missions en sécurité informatique

La sécurité s’appréhende sous trois aspects complémentaires : prévention, détection, réaction.

## Prévention

- Anticiper/identifier les risques
- Sensibiliser les utilisateurs
- Limiter l'impact des attaques
- Tester les politiques de sécurité/sauvegarde
- Respecter les bonnes pratiques
- Faire de la veille

## Détection

- Surveiller le réseau, le parc
- Réagir en cas d'alerte automatisée

## Réaction

- Suivre le PCA/PRA pour rétablir le système
- Restaurer des sauvegardes
- Prévenir/communiquer (CNIL, assurances, dépôt de plainte)

---

# Mots de passe et authentification

## Bonnes pratiques pour les mots de passe

- Générer aléatoirement
- Longueur suffisante
- Un mot de passe unique par système
- Ne pas contenir d'informations personnelles
- Éviter les substitutions simples ou mots du dictionnaire
- **Ne jamais utiliser les mots de passe les plus courants**

## Gestionnaire de mots de passe

- Stocker les mots de passe de façon chiffrée
- Préférer un gestionnaire à un carnet papier ou navigateur

## Facteurs d'authentification

- Facteur de connaissance : mot de passe, code pin
- Facteur de possession : clé, carte à puce, code SMS, OTP/TOTP
- Facteur biologique : empreinte digitale, reconnaissance rétinienne/vocale
- Parfois facteur réactionnel : geste ou signature

## 2FA / MFA

- 2FA : authentification à deux facteurs
- MFA : authentification à facteurs multiples
- **Activer dès que possible**

---

# Antivirus et malwares

## Fonctionnement des antivirus

- Analyse de la signature (hash) des fichiers
- Analyse comportementale (méthode heuristique)

## Types de malwares

- Ransomware : chiffre les données, exige une rançon
- Spyware : espionne l'activité, vole des données
- Adware : virus publicitaire
- Cheval de troie : code malicieux dans une application légitime
- Ver : virus auto-répliquant
- Rootkit : malware furtif, difficile à détecter
- Keylogger : enregistre les frappes clavier
- Coinminer : mine des cryptomonnaies à l'insu de l'utilisateur
- Botnet : réseau de machines zombies pour attaques DDoS

---

# Cryptographie

## Chiffrement vs hachage

- Chiffrement : rendre une donnée illisible sans clé
- Hachage : empreinte unique, non réversible

## Chiffrement symétrique

- Même clé pour chiffrer et déchiffrer

## Chiffrement asymétrique

- Clé publique pour chiffrer, clé privée pour déchiffrer

## Chiffrement hybride

- Combine chiffrement symétrique et asymétrique
