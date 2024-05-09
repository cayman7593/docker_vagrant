 VM Docker avec Vagrant

Ce projet provisionne une machine virtuelle (VM) Ubuntu avec Docker installé, utilisant Vagrant. Il est idéal pour les développeurs qui souhaitent avoir un environnement Docker prêt à l'emploi pour leurs développements ou tests.

## Prérequis

Assurez-vous d'avoir les logiciels suivants installés sur votre machine avant de commencer :

- [Vagrant](https://www.vagrantup.com/downloads.html) (testé sur version 2.2.x)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (testé sur version 6.x)

## Installation

1. Clonez ce dépôt GitHub sur votre machine locale en utilisant :
   ```bash
   git clone https://github.com/votre-username/votre-repo.git

2.  Naviguez dans le dossier du projet cloné :
cd votre-repo
3. Lancez la machine virtuelle avec Vagrant :
vagrant up
Une fois la commande exécutée, Vagrant va télécharger l'image de base (ubuntu/mantic64), configurer la VM avec 2048 MB de RAM, et installer Docker.

Utilisation
Après le provisionnement, vous pouvez accéder à votre VM en utilisant :
vagrant ssh
Docker est déjà installé et prêt à être utilisé. Essayez de lancer votre premier conteneur Docker :
docker run hello-world 
   
