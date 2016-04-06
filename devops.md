# <a href="https://www.vagrantup.com" target="_blank">Vagrant</a>

![vagrant](assets/vagrant_logo.png)

Vagrant permet d'accélerer la mise en place d'environnements de dev.

Il permet de configurer et d'utiliser des machines virtuelles en quelques lignes de commandes.

## Installation

+ [Installer VirtualBox](https://help.ubuntu.com/community/VirtualBox/Installation)
```bash
sudo apt-get update
sudo apt-get install virtualbox virtualbox-qt virtualbox-dkms
```

+ [Télécharger Vagrant](https://www.vagrantup.com/downloads.html)


[:tv: Créer une VM avec Vagrant](https://www.youtube.com/watch?v=YpkPAb7q10k)
[:tv: utiliser PuPHPet](https://www.youtube.com/watch?v=Yb20B0kPrro)

## Boxes
Il existe :
+ des [configurations types / boxes toutes prêtes](https://atlas.hashicorp.com/boxes/search), partagées par d'autres développeurs
+ un générateur de configuration en ligne : [Puphpet](https://puphpet.com/#frontpage)


+ https://box.scotch.io


+ **[Vagrant push](https://www.hashicorp.com/blog/vagrant-push-to-deploy.html)**


#### Box Puphpet
+ configurer sa vm
+ télécharger
+ dézipper , renommez vm-php7
+ déplacez le dossier vers ~/vagrant/boxes/
```bash
cd ~/vagrant/boxes/vm-php7
vagrant up
```
+ ouvrir <a href="http://192.168.56.101" target="_blank">192.168.56.101</a>

# Puppet

# Chef
http://blog.octo.com/devops-corner-episode-1-chef-pour-les-nuls/
[MANAGING LAMP ENVIRONMENTS WITH CHEF, VAGRANT, AND EC2 (1 OF 3)](http://www.jasongrimes.org/2012/06/managing-lamp-environments-with-chef-vagrant-and-ec2-1-of-3/)
# Ansible

# Docker

[Docker Vs Vagrant](https://www.upguard.com/articles/docker-vs-vagrant)
[Docker ou VM](http://stackoverflow.com/questions/16047306/how-is-docker-different-from-a-normal-virtual-machine?rq=1)

**Install ubuntu**
+ which curl

## utilisation ##

docker pull image/nom

ou a d'un dossier avec DockerFile
+ `docker build -t nomImg`
+ docker run

docker start / stop / pause / restart img_name
docker exec -it pensive_liskov bash

+ régler pb daemon macos
```bash
docker-machine start default

# regenerate TLS connection certs
docker-machine regenerate-certs default

# finally, set env
eval "$(docker-machine env default)"
```