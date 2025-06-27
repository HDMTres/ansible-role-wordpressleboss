===============================
DEPLOIEMENT WORDPRESS AVEC ANSIBLE de Hadama TOURE
===============================

Description :
-------------
Ce projet automatise le déploiement d’un site WordPress complet sur une ou plusieurs machines Linux (clients) via Ansible. Il installe et configure Apache, PHP, MySQL et WordPress à distance.

Structure du projet :
---------------------
- ansible-role-wordpressleboss/  --> Rôle personnalisé pour WordPress
  - tasks/
  - templates/
  - files/
- tests/
  - inventory                   --> Fichier d'inventaire Ansible
- playbook.yml                  --> Playbook principal
- README.txt                    --> Ce fichier

Technologies utilisées :
------------------------
- Ansible
- Ubuntu Server 24.04
- Apache2
- PHP
- MySQL ou MariaDB
- WordPress
- WSL2 ou VirtualBox avec port forwarding (ex: 8082 → client1:80)

Lancer le projet :
------------------
1. Cloner le projet :
   git clone https://gitlab.com/ton-utilisateur/ton-projet.git
   cd ton-projet

2. Exécuter le playbook :
   ansible-playbook -i /root/config/evaluation/ansible-role-wordpressleboss/tests/inventory /root/config/evaluation/wordpressleboss.yaml

   (Ajouter --ask-become-pass si nécessaire)

Accès aux clients WordPress :
-----------------------------
Après le déploiement, accéder à l’interface WordPress via votre navigateur :

- Client1 : http://localhost:8082
- Client2 : http://localhost:8083
- Client3 : à configurer
- Client4 : à configurer

Fonctionnement :
----------------
- Le rôle installe Apache, PHP et MySQL
- WordPress est téléchargé et placé dans /var/www/html/
- Le service Apache est redémarré automatiquement
- La page d’installation WordPress est alors accessible sur le port redirigé

Dépannage :
-----------
- Apache ne démarre pas ? → systemctl status apache2
- Page blanche ? → vérifier si PHP est activé (apache2ctl -M | grep php)
- Port déjà utilisé ? → ss -tuln | grep :80

Auteur :
--------
- Nom : Ton Nom Prénom
- Formation : M1 MSI TDP 2025 - Sup de Vinci
- Contact : hdmunkey@supdevinci-edu.fr

Licence :
---------
Projet libre sous licence MIT
