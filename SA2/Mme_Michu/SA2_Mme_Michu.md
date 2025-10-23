# Atelier SA2 - Mme Michu

## 1. Réparer le démarrage de Windows

### 1. Boot sur un ISO de Windows 10  

J'ai monté un ISO de Windows 10 dans la VM pour pouvoir booter sur le programme d'installation et utiliser l'utilitaire de dépannage.  
<img src="https://github.com/jbabin49/Ateliers_Oclock/blob/main/SA2/Mme_Michu/Screenshots/Insertion_iso_W10.png" width="auto" height="200">  

### 2. Tentative avec l'outil de redémarrage du système infructueuse


https://github.com/user-attachments/assets/be044c0c-0c20-4ca9-9c64-766a6f62fc03


### 3. Tentative avec le terminal


https://github.com/user-attachments/assets/0e6cc514-8a7b-4a27-96e3-1583952efcde


<img src="https://github.com/jbabin49/Ateliers_Oclock/blob/main/SA2/Mme_Michu/Screenshots/bureau.png" width="auto" height="500">  

  
### Ça a marché 🥳

## 2. Restaurer les performances normales de la machine

### 1. Pour commencer un petit tour dans le gestionnaire des tâches
Après avoir trié par consommation des ressources, on se rends compte que les services consommant le plus sont des processus Windows :
- Antimalware Service Executable (Windows Defender)
- Hôte de service local (8 en tout)  
<img src="https://github.com/jbabin49/Ateliers_Oclock/blob/main/SA2/Mme_Michu/Screenshots/gestionnaire_taches.png" width="auto" height="500">  

### 2. Trouver pourquoi et comment résoudre le problème

Un petit tour sur notre ami internet et un tuto de Malekal nous explique pourquoi  ces processus consomment autant et comment résoudre le problème  
https://www.malekal.com/antimalware-execution-service-et-forte-utilisation-cpu-disque-ou-ram-sur-windows-10/  


Je commence par faire une mise à jour de la protection  
<img src="https://github.com/jbabin49/Ateliers_Oclock/blob/main/SA2/Mme_Michu/Screenshots/gestionnaire_taches.png" width="auto" height="500"> 

## 3. Vérifier l'état des disques durs



## 4. Retrouver les fichiers disparus dans le dossier "Images"
