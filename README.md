===============================
DEPLOIEMENT WORDPRESS AVEC ANSIBLE de Hadama TOURE
===============================

Description :
-------------
Ce projet automatise le déploiement d'un site WordPress complet sur une ou plusieurs machines Linux (clients) via Ansible. Il installe et configure Apache, PHP, MySQL et WordPress à distance.

Structure du projet :
---------------------
- ansible-role-wordpressleboss/  --> Rôle personnalisé pour WordPress
  - tasks/                      --> Tâches Ansible
  - templates/                  --> Templates (wp-config.php.j2)
  - defaults/                   --> Variables par défaut
  - handlers/                   --> Gestionnaires de services
  - tests/
    - inventory                 --> Fichier d'inventaire Ansible
    - test.yml                  --> Playbook de test
- README.md                     --> Ce fichier

Technologies utilisées :
------------------------
- Ansible
- Ubuntu Server 24.04 / Rocky Linux
- Apache2 / HTTPD
- PHP
- MySQL / MariaDB
- WordPress
- WSL2 ou VirtualBox avec port forwarding

INSTALLATION ET DÉPLOIEMENT :
=============================

<<<<<<< HEAD
1. Exécuter le playbook :
---------------------------
```bash
ansible-playbook -i /root/config/evaluation/ansible-role-wordpressleboss/tests/inventory /root/config/evaluation/ansible-role-wordpressleboss/tests/test.yml
```

2. Vérifier le déploiement :
----------------------------
Après l'exécution du playbook, vérifiez que les services sont actifs :

```bash
# Vérifier l'état des services sur les clients Ubuntu
ansible ubuntu -i tests/inventory -m shell -a "systemctl status apache2"
ansible ubuntu -i tests/inventory -m shell -a "systemctl status mariadb"

# Vérifier l'état des services sur les clients Rocky
ansible rocky -i tests/inventory -m shell -a "systemctl status httpd"
ansible rocky -i tests/inventory -m shell -a "systemctl status mysqld"
```

CONFIGURATION POST-INSTALLATION :
==================================

3. Accès aux sites WordPress :
-------------------------------
Ouvrez votre navigateur et accédez aux sites WordPress :

- **Client1 (Ubuntu)** : http://localhost:8082 (si port forwarding configuré)
- **Client2 (Ubuntu)** : http://localhost:8083 (si port forwarding configuré)
- **Client3 (Rocky)** : 
- **Client4 (Rocky)** : 


5. Vérifications techniques :
-----------------------------
```bash
# Vérifier que WordPress est bien installé
ansible ubuntu -i tests/inventory -m shell -a "ls -la /var/www/html/"

# Vérifier la base de données
ansible ubuntu -i tests/inventory -m shell -a "mysql -e 'SHOW DATABASES;'"

# Vérifier les permissions
ansible ubuntu -i tests/inventory -m shell -a "ls -la /var/www/html/wp-config.php"

# Tester la connectivité web
ansible ubuntu -i tests/inventory -m shell -a "curl -I http://localhost"
```

DÉPANNAGE ET SUPPORT :
========================

Ah gros...

Auteur :
--------
- **Nom** : TOURE Hadama
- **Formation** : M1 MSI A 2025 - Sup de Vinci
- **Contact** : hadama.toure@supdevinci-edu.fr
- **Date** : Juin 2025

Licence :
---------
Projet libre sous licence MIT

SUPPORT ET RESSOURCES :
=======================

Ressources utiles :
- Documentation Ansible : https://docs.ansible.com/
- Documentation WordPress : https://wordpress.org/support/
- PHP Documentation : https://www.php.net/docs.php
- MySQL Documentation : https://dev.mysql.com/doc/
- Apache Documentation : https://httpd.apache.org/docs/

