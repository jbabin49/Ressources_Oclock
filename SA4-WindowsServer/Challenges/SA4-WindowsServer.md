Structure de l’Active Directory

* Oclock (Forêt)
   * Promotions
      * [x] Patrice MALDI (Utilisateur)
      * [x] GS_Promotions (Groupe)
      * [x] Andromède
          * [x] Baptiste DELPHIN (Utilisateur)
          * [x] GS_PromoAndromede (groupe)
      * [x] Aldebaran
          * [x] Christophe SEIGNANT  (Utilisateur)
          * [x] GS_PromoAldebaran (groupe)
      * [x] Zinc
          * [x] Roman BELDENT (Utilisateur)
          * [x] GS_PromoZinc (groupe)
      * [x] Basilic
          * [x] Alice MARTIN (Utilisateur)
          * [x] GS_PromoBasilic (groupe)


Potentiels GPO et Partages à créer
* GPO pour tous les étudiants :
  * [x] Activer le Verrou Numérique : Crée une GPO pour activer le Verrou Numérique au démarrage.
  * [x] Configurer une politique de mot de passe sécurisé : Obliger les étudiants à utiliser des mots de passe forts et à les changer régulièrement, par exemple tout les 30 jours. (PS: Allez vous renseigner sur les bonnes pratiques de la CNIL si vous avez 2 minutes)


GPO spécifique par promotion :

  * [x] Forcer un fond d’écran : Crée une GPO pour définir un fond d’écran spécifique pour chaque promotion (Aldebaran, Andromède, Zinc, Basilic).


Autre paramètre :

  * [x] Désactiver la connexion des étudiants Zinc et Basilic à partir de 17h jusqu’à 8h00 pour tout les jours de la semaine : Mettre en place un paramètre pour restreindre les connexions des utilisateurs de ces promotions pendant les heures spécifiées.


Partages de dossiers :

* Création de dossiers partagés pour chaque promotion :
  * [x] Crée un dossier partagé pour chaque promotion (Aldebaran, Andromède, Zinc, Basilic).
  * [x] Configure les permissions de partage et NTFS pour que seuls les membres du groupe approprié aient accès.
       * Je suis spécial ! 👀
  * [x] Attribuer un mappage pour chaque dossier
  * Restreindre les fichiers
      * [x] Interdit aux fichiers .divx uniquement (Nous ne voulons pas de « photo de famille » 🥸)
   * [x] Quotas de 30Go par promotions
   * Exemple de structure de dossiers partagés :
       * Serveur//Shares//PromoAldebaran
       * Serveur//Shares//PromoAndromede
       * Serveur//Shares//PromoZinc
       * Serveur//Shares//PromoBasilic


Bonus ! : Installation de Firefox en GPO !

  * [ ] Installer Firefox via les GPO pour tout les utilisateurs des promotions.
        (si vous l’avez deja installé a la main faites le avec Chrome, sinon un autre navigateur 😉 )
        Vous avez besoin d’un fichier MSI.


Bonus Extremes ! : Mettre des profils itinérants & Installation de VSCode.

  * [ ] Créer un nouveau Partage, pour les profils itinérants (Pas d’inquiétude en correction nous allons en parlera correctement 😉 ).
      * [ ] Et créer les pour chaque utilisateur de l’AD

  * [ ] Obligation d’installer VSCode : Crée une GPO pour déployer Visual Studio Code sur les machines des étudiants Zinc & Basilic uniquement.
