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

|Nom|Équipements|Adresse réseau|Adresses dispos|
|---|-----------|--------------|---------------|
|Paris-Lille|2|92.12.44.0/24|254|
|Paris-VPN|2|92.56.78.0/24|254|

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

<img width="1681" height="667" alt="cablage" src="https://github.com/user-attachments/assets/513a85ac-e19d-42ae-86d1-93a346a41f20" />

### Étape 3 - Configuration des switchs

<img width="524" height="322" alt="switch_config" src="https://github.com/user-attachments/assets/70a7b6f9-9274-4a21-b01a-a31be912b252" />

<img width="395" height="229" alt="ping_switch" src="https://github.com/user-attachments/assets/f4421f1c-b619-456d-8f19-a118653b7ddd" />

- Définition du nom d'hôte : `hostname L-LAN`
- Définition du mot de passe du mode privilégié : `enable secret rocknroll`
- Définition de l'adresse sur la vlan1 : `ip address 10.1.1.2 255.255.255.0`
- On allume la vlan : `no shutdown`
- Et on oublie pas de sauvegarder les changements : `copy run sta`

### Étape 4 - Configuration initiale des routeurs

<img width="594" height="717" alt="routeur_config" src="https://github.com/user-attachments/assets/f24d7cbc-2813-43d2-95b4-cd9e328807ab" />

- Définition du nom d'hôte : `hostname routeurParis`
- Définition du mot de passe du mode privilégié : `enable secret rocknroll`
- Définition de l'adresse sur le port : `ip address 92.12.34.1 255.255.255.0`
- On allume le port : `no shutdown`
- Et on oublie pas de sauvegarder les changements : `copy run sta`

### Étape 5 - Routes statiques

<img width="459" height="122" alt="routage_statique" src="https://github.com/user-attachments/assets/5ad536d6-8e36-414f-8c98-6571d5ba0b29" />

- On configure la route statique vers le sous-réseau de l'autre site en passant par son routeur : `ip route 198.168.1.0 255.255.255.0 92.12.34.1`

### Étape 6 - DHCP + Méga bonus

Configuration des pools DHCP sur le serveur

<img width="1006" height="780" alt="DHCP_config" src="https://github.com/user-attachments/assets/32c0213e-5305-4567-8342-4d7ae17dd4ab" />

Configuration du relay DHCP sur les routeurs

<img width="439" height="330" alt="DHCP_relay" src="https://github.com/user-attachments/assets/4e765da0-a37e-4a50-ac50-629a74ee0fcd" />

- On donne l'ip du serveur DHCP à chaque port du routeur (sauf celui du serveur) : `ip helper-address 192.168.3.3`

<img width="997" height="377" alt="config_DHCP_device" src="https://github.com/user-attachments/assets/1d9e2f67-49a9-4b9c-be80-13b17fddb2b9" />

<img width="997" height="319" alt="ipconfig" src="https://github.com/user-attachments/assets/37a23a1d-5616-4f96-8044-fe363444866b" />

- On configure les ip des appareils en DHCP
- On vérifie avec un `ipconfig`

Ça fonctionne 😁
