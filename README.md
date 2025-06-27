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
   git clone https://github.com/HDMTres/ansible-role-wordpressleboss/tree/main/ansible-role-wordpressleboss
   cd ton-projet

2. Exécuter le playbook :
   ansible-playbook -i /root/config/evaluation/ansible-role-wordpressleboss/tests/inventory /root/config/evaluation/ansible-role-wordpressleboss/tests/test.yml

Accès aux clients WordPress :
-----------------------------
Après le déploiement, accéder à l’interface WordPress via votre navigateur :

- Client1 : http://localhost:8082
- Client2 : http://localhost:8083
- Client3 : en cours
- Client4 : en cours

Fonctionnement :
----------------
- Le rôle installe Apache, PHP et MySQL
- WordPress est téléchargé et placé dans /var/www/html/
- Le service Apache est redémarré automatiquement
- La page d’installation WordPress est alors accessible sur le port redirigé


Auteur :
--------
- Nom : TOURE Hadama
- Formation : M1 MSI A TDP 2025 - Sup de Vinci
- Contact : hadama.toure@supdevinci-edu.fr

Licence :
---------
Projet libre sous licence MIT
