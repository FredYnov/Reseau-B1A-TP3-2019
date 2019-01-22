B1 Réseau 2018 - TP3


<meta charset="UTF-8">
<p> Mathis BIANCO B1A </p> 
<p> Sacha Sallès </p> 

**B1-Réseau-2018 TP3**
-----------------

#***Partie 1-4 Vue en cours*** 


# I.Création et utilisation simples d'une VM CentOS
*********************************************************
## 1.Création
  Création de ma VM effectue sur VirtualBox vue en cours.
-----------------
![alt text](CENTOS.png "githup")
![alt text](CENTOS3.png "TYPE NAT")

-----------------
## 2. Installation de l'OS
![alt text](CENTOS2.png "ensemble des caractérisations de ma VM")


## 3. Premier Boot
![alt text](CENTOS4.png "Désactivez SElinux")

## 4. Configuration Réseau d'une machineCentOs

###### a. utiliser une commande pour prouver que vous avez Internet depuis la VM

J'ai fait un traceroute 8.8.8.8, voici le résultat

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%201.png)

###### b. Prouvez que votre PC hôte et la VM peuvent communiquer

Là encore, j'ai fait un traceroute à partir de CentOs vers l'adresse IP de ma machine physique, à savoir 10.33.2.198.

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%202.png)

* Idem à partir de la machine physique vers le 127.0.0.1

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%203.png)

###### c. affichez votre table de routage sur la VM et expliquez chacune des lignes

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%204.png)

<ol>
  <li>La ligne 1 correspond à la Gateway</li>
  <li>La ligne 2 correspond à l'adresse IP de la première carte Réseau NAT (10.0.2.0)</li>
  <li>La ligne 3 correspond à le'adresse IP de notre seconde carte Réseau (192.168.101.0)</li>
</ol>

**5. Faire joujou avec quelques commandes**

* Ping Hôte -> VM

  * Vers IP 192.168.101.10

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%205.png)

* Ping VM -> Hôte

  * Vers IP 192.168.101.1

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%206.png)

* Affichage de la table de routage de l'hôte:

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%2010.png)

* Affichage de la table de routage de la VM:

cf ci-dessus, l'opération a déjà été faite dans 4c.

* Depuis la VM utilisez curl (ou wget) pour télécharger un fichier sur internet

Que ce soit avec sudo yum install wget ou sudo yum install binds-utils, impossible d'installer quoi que ce soit. Erreur : aucune source disponible...

* depuis la VM utilisez dig pour connaître l'IP de :

Idem ci-dessus pour dig

## II. Notion de ports et SSH

* Pour cette partie, j'ai fait un SS -altnp4, voilà le résultat

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%207.png)

* IPv4 en écoute:

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%208.png)

**2. SSH**

  *A. SSH

J'ai effectué le changement de port en passant du port 22 au port 2222.

Ensuite, j'ai refait une commande ss -t -l -4 -n

![alt text](https://github.com/FredYnov/B1-Reseau-tp3/blob/master/Capture%20ecran/Capture%209.png)


### 3. Firewall
******************



# III. Routage Statique

### 1. Préparation des hôtes (vos PCs)

 Vos carte Ethernet doivent être dans le réseau 12 : 192.168.112.0/30

