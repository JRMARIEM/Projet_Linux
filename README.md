# Projet_Linux
Instruction pour la session de coaching
Mini-projet : Installer sur une VM (fournie), un serveur Web en Python Flask fonctionnant sur le port 30101. Ce serveur écrit les actions des utilisateurs dans un disque attaché à la VM. écrire les instructions pour le pare-feu
# Exercice 1 - Scrum
1- Aller sur project

2- Ensuite sur New Project

3- Sélectionner un modèle puis cliquer sur créer

4- Créer la liste des tâches à effectuer

5- Faire un screenshot

# Exercice 2 - Linux

1-Mettre à jour les packages de votre VM ubuntu:

`sudo apt update`

`sudo apt upgrade`


2-Vérifier la version de python3 déjà installée:

`python --version`

3-créer un alias nommé python valide pour le user ubuntu de votre VM:

-Ouvrir le fichier .bashrc du user ubuntu:

`sudo nano ~/ .bashrc`

-Ajouter la ligne suivante au fichier

` alias python='python3'`

-Rechargez les modifications faites dans le fichier ~/.bashrc en tapant la commande suivante :

`source ~/ .bashrc`

La commande "python" peut être utilisée pour exécuter le programme "python3" sur la VM.

`python -V`

4- Installer flask:

On doit installé le pip :

 ` sudo apt install pip`
 
Vérifier si pip est bien installé et la version :

  `pip --version` 
  
Installer flask :

  ` pip install flask`
  
Vérifier si flask est bien installé :

   `flask --version`
   
# Exercice 3 - Storage

1- Rechercher le disque supplémentaire de 1Gb connecté à la VM:

Utiliser la commande suivante pour lister les disques et les partitions connectés au système :

`sudo fdisk -l`

Pour trouver directement le disque supplémentaire de 1Gb connecté à la VM utiliser la commande suivante:

   `sudo fdisk -l | grep "1 GiB"`

Formater le disque au format ext4

Vérifier que le disque ne figure pas dans la liste des systèmes de fichiers montés, avec leur point de montage correspondant:

   `df -h`

 formater le disque au format ext4:

  `sudo mkfs -t ext4 /dev/vdc`

 Monter (mount) ce disque sur le point montage /home/ubuntu/projet_Linux/log :

Créez le répertoire de point de montage avec la commande suivante :

  `sudo mkdir log`
  
Montez le disque sur le point de montage en utilisant la commande suivante :

  `sudo mount /dev/vdc /home/ubuntu/tp-coaching-webforce3/log`
  
