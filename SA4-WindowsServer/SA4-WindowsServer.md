Structure de l’Active Directory

    Oclock (Forêt)
        Promotions
           [] Patrice MALDI (Utilisateur)
           [] GS_Promotions (Groupe)
           [] Andromède
               [] Baptiste DELPHIN (Utilisateur)
               [] GS_PromoAndromede (groupe)
           [] Aldebaran
               [] Christophe SEIGNANT  (Utilisateur)
               [] GS_PromoAldebaran (groupe)
           [] Zinc
               [] Roman BELDENT (Utilisateur)
               [] GS_PromoZinc (groupe)
           [] Basilic
               [] Alice MARTIN (Utilisateur)
               [] GS_PromoBasilic (groupe)

Potentiels GPO et Partages à créer
GPO pour tous les étudiants :

   [] Activer le Verrou Numérique : Crée une GPO pour activer le Verrou Numérique au démarrage.
   [] Configurer une politique de mot de passe sécurisé : Obliger les étudiants à utiliser des mots de passe forts et à les changer régulièrement, par exemple tout les 30 jours. (PS: Allez vous renseigner sur les bonnes pratiques de la CNIL si vous avez 2 minutes)

GPO spécifique par promotion :

   [] Forcer un fond d’écran : Crée une GPO pour définir un fond d’écran spécifique pour chaque promotion (Aldebaran, Andromède, Zinc, Basilic).

Autre paramètre :

   [] Désactiver la connexion des étudiants Zinc et Basilic à partir de 17h jusqu’à 8h00 pour tout les jours de la semaine : Mettre en place un paramètre pour restreindre les connexions des utilisateurs de ces promotions pendant les heures spécifiées.

Partages de dossiers :

    Création de dossiers partagés pour chaque promotion :
       [] Crée un dossier partagé pour chaque promotion (Aldebaran, Andromède, Zinc, Basilic).
       [] Configure les permissions de partage et NTFS pour que seuls les membres du groupe approprié aient accès.
            Je suis spécial ! 👀
       [] Attribuer un mappage pour chaque dossier
       Restreindre les fichiers
           [] Interdit aux fichiers .divx uniquement (Nous ne voulons pas de « photo de famille » 🥸)
       [] Quotas de 30Go par promotions
       Exemple de structure de dossiers partagés :
            Serveur//Shares//PromoAldebaran
            Serveur//Shares//PromoAndromede
            Serveur//Shares//PromoZinc
            Serveur//Shares//PromoBasilic

Bonus ! : Installation de Firefox en GPO !

   [] Installer Firefox via les GPO pour tout les utilisateurs des promotions.
        (si vous l’avez deja installé a la main faites le avec Chrome, sinon un autre navigateur 😉 )
        Vous avez besoin d’un fichier MSI.

Bonus Extremes ! : Mettre des profils itinérants & Installation de VSCode.

   [] Créer un nouveau Partage, pour les profils itinérants (Pas d’inquiétude en correction nous allons en parlera correctement 😉 ).
       [] Et créer les pour chaque utilisateur de l’AD

   [] Obligation d’installer VSCode : Crée une GPO pour déployer Visual Studio Code sur les machines des étudiants Zinc & Basilic uniquement.
   Attention, c’est compliqué ! Bravo à vous si vous relevez le défi ! Et y’a plusieurs façon de le faire !

