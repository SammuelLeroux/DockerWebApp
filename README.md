# Guide d'Installation Docker pour Debian 11

Ce guide fournit des instructions étape par étape pour installer Docker et Docker Compose sur Debian 11. De plus, il couvre le déploiement d'un projet à l'aide de Docker Compose avec des tâches spécifiques liées à Portainer, MariaDB, et un backend Flask.

## Table des Matières
    1. [Installation de Docker](#installation-de-docker)
    2. [Installation de Docker Compose](#installation-de-docker-compose)
    3. [Déploiement du Projet](#déploiement-du-projet)

# Installation de Docker

Pour installer Docker sur Debian 11, suivez ces étapes :

## Mettre à jour l'index des paquets
```bash
sudo apt update
```

## Installer les dépendances
```bash
sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
```

## Ajouter la clé GPG de Docker
```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

## Ajouter le dépôt APT de Docker
```bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

# Installer Docker Engine
```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io
```

## Ajouter votre utilisateur au groupe docker
```bash
sudo usermod -aG docker $USER
```

## Redémarrer votre système pour appliquer les changements
```bash
sudo reboot
```

# Installation de Docker Compose

Pour installer Docker Compose, exécutez les commandes suivantes :

## Télécharger le binaire Docker Compose
```bash
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

## Appliquer les permissions d'exécution
```bash
sudo chmod +x /usr/local/bin/docker-compose
```

## Déploiement du Projet

Assurez-vous d'avoir Docker et Docker Compose installés avant de continuer.

## Clonez le dépôt GitHub :

```bash
git clone https://github.com/SammuelLeroux/DockerWebApp.git
cd DockerWebApp
```
