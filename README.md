Role Name
=========

Ce role permet de déployer AIDE (Adavanced Intrusion Detection Environment) sur Centos pour surveiller l'intégrité des files system

Requirements
------------

Testé Centos 7

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Les variables sont:
- costum_config: pour accepter ou non le modèle de fichier de configuration (à adapter au besoin)
- db_dir: spécifie le répertoire de la base de données d'AIDE (pour le modèle de fichier de configuration)
- log_dir: spécifie le répertoire des logs d'AIDE (pour le modèle de fichier de configuration)
- config_file: specifie le chemin du fichier de configuration (pour le modèle de fichier de configuration)
- check: indique si oui/non on installe le script de vérification et crée une tâche de cron pour son lancement automatique

Remarque: 
- si le modèle du fichier de configuration n'est pas choisi, AIDE est installé avec les paramètres par défaut (comme dans le cas d'une installation manuelle)


Dependencies
------------

Il n'y a pas de dépendances. Mais le rôle peut être intégré facilement dans d'autres projets. Pour ce faire :
- créer un fichier **requirements.yml** avec le contenu ci-dessous :
```
---
- name : aide
  src : https://github.com/tassyk/ansible-aide.git
  scm: git
  version : origin/master
```
- Installer le rôle avec ansible Galaxy :
```
ansible-galaxy install -r requirements.yml -p /chemin/repertoire/roles
```
Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      remote_user: user
      become: True
      become_method: sudo
      roles:
      - ansible-aide

**Exemple d'exécution du playbook :**
```
ansible-playbook aide.yml -i hosts [-u user] [options]
```


License
-------

BSD

Author Information
------------------
tassyk
