# Challenge Packet Tracer SA3 - Réseaux

## Contexte

Une nouvelle entreprise vous recrute pour professionnaliser son réseau. Actuellement, les salariés sont connectés en WiFi sur des box FAI avec du matériel hétérogène.

Le parc informatique va être complètement renouvelé.

L'entreprise est en pleine expansion, et recrute fréquemment de nouveaux salariés. Actuellement, il y a 59 collaborateurs, vous y compris, mais l'entreprise pourrait dépasser 200 salariés ou plus dans les mois/années à venir ! 📈

Voici les différents services de l'entreprise ainsi que le nombre de salariés par service :

 - commerciaux : 16
 - communication : 5
 - comptabilité : 5
 - direction : 4
 - ressources humaines : 2
 - juridique : 2
 - recherche et développement : 23
 - informatique : 2

L'entreprise a des bureaux à Paris et à Lille, mais ils envisagent à terme d'ouvrir un site par département Français.

À Paris, on retrouve la direction, la comptabilité, le service juridique, la communication et les ressources humaines. Il y a également 10 commerciaux, 12 ingénieurs R&D et un informaticien.

Le site de Lille compte 11 ingénieurs R&D, 6 commerciaux et un informaticien.

Sur le site de Paris, une salle serveur va être créée et équipée 4 serveurs. Le coeur du réseau y sera installé. Les salariés du service R&D sont dans un batiment différent, équipé d'une petite baie informatique, de quoi y installer un peu de matériel réseau ! La baie du batiment R&D sera relié à la salle serveur avec une fibre optique.

Les salariés peuvent travailler de façon nomade : depuis leur domicile en télétravail ou en déplacement chez des clients pour les commerciaux, par exemple. Ils se connectent via un VPN sur le routeur du site de Paris au réseau de l'entreprise (plus d'infos ci-dessous).

### Étape 1 - Plan d'adressage

Voici les sous-réseaux minimum à créer :

 * Paris :
   * LAN (tous les PC fixes et portables)
   * DMZ (zone démilitarisée, pour les serveurs, voir ci-dessous)
   * WiFi public (pour les visiteurs, filaire obligatoire pour les salariés)

 * Lille :
   * LAN (tous les PC fixes et portables)
   * WiFi public (pour les visiteurs, filaire obligatoire pour les salariés)

 * VPN (un sous-réseau dans lequel se trouvent les machines des collaborateurs à distance)

#### Plan

Je prends large sur les LAN pour prévenir l'expansion de l'entreprise.

* Paris

<center>
  
|Nom|Équipements|Adresse réseau|Adresses dispos|Passerelle|
|---|-----------|--------------|---------------|----------|
|P-LAN|29|192.168.1.0/24|254|192.168.1.1|
|P-WifiPublic|?|192.168.2.0/24|254|192.168.2.1|
|P-DMZ|4|192.168.3.0/28|14|192.168.3.1|

</center>

* Lille

<center>
  
|Nom|Équipements|Adresse réseau|Adresses dispos|Passerelle|
|---|-----------|--------------|---------------|----------|
|L-LAN|18|10.1.1.0/24|254|10.1.1.1|
|L-WifiPublic|?|10.1.2.0/24|254|10.1.2.1|

</center>

* VPN

<center>
  
|Nom|Équipements|Adresse réseau|Adresses dispos|Passerelle|
|---|-----------|--------------|---------------|----------|
|VPN|59|172.16.1.0/24|254|172.16.1.1|

</center>

* Liens entre routeurs

<center>

|Nom|Équipements|Adresse réseau|Adresses dispos|Passerelle|
|---|-----------|--------------|---------------|----------|
|Paris-Lille|2|192.168.4.0/29|6|192.168.4.1|
|Paris-VPN|2|192.168.5.0/29|6|192.168.5.1|

</center>

### Étape 2 - Câblage + Bonus

Voici la liste du matériel réseau à votre disposition :

* Routeurs :
  * 2x Cisco 2901 (un pour Paris, un pour Lille)
  * 1x Cisco 1941 (pour le VPN)

* Modules et cartes d'extension pour routeurs :
  * 5x cartes HWIC-1GE-SFP, avec 5x modules SFP GLC-LH-SMD
  * 2x cartes HWIC-2T

* Switchs :
  * 4x Cisco 3650-24PS (2 pour le LAN de Paris, un pour la DMZ, un pour le LAN de Lille)
  * 1x Cisco 2960-24TT (Pour le VPN)

* Modules et cartes d'extension pour switchs :
  * 4x alimentations AC-POWER-SUPPLY (une par switch 3650-24PS)
  * 4x modules SFP GLC-LH-SMD

* Autres équipements :
  * 4x Serveurs
  * 3x Copieurs (2 pour Paris dont un pour le batiment R&D, un pour Lille)
  * 2x Points d'accès WiFi AP-PT (1 pour le wifi de Paris et 1 pour le WiFi de Lille)

<img width="1690" height="675" alt="cablage" src="https://github.com/user-attachments/assets/3ce15aad-14ea-4f46-b9e5-563e9b88eed6" />

### Étape 3 - Configuration des switchs

<img width="524" height="322" alt="switch_config" src="https://github.com/user-attachments/assets/70a7b6f9-9274-4a21-b01a-a31be912b252" />

<img width="395" height="229" alt="ping_switch" src="https://github.com/user-attachments/assets/f4421f1c-b619-456d-8f19-a118653b7ddd" />

