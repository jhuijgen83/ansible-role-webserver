Webserver Role
==============

Deze Ansible role installeert een webserver op Ubuntu 24.04-systemen. De configuratie bestaat uit Apache, PHP en een testpagina (`index.php`) met `phpinfo()`.

Requirements
------------

- Een werkende Ubuntu 24.04 VM
- `apt` als package manager
- Poort 80 beschikbaar (NGINX wordt automatisch verwijderd als het draait)

Role Variables
--------------

Deze variabelen zijn beschikbaar:

| Variabele       | Default waarde | Beschrijving                              |
|-----------------|----------------|-------------------------------------------|
| `apache_port`   | `80`           | Poort waarop Apache moet luisteren        |

Je kunt deze overschrijven via `group_vars`, `host_vars` of rechtstreeks in je playbook.

Dependencies
------------

Geen.

Example Playbook
----------------

Gebruik deze rol vanuit Ansible Galaxy:

`example.yaml`
- name: Installeer webserver via Galaxy
  hosts: webservers
  become: yes
  roles:
    - jhuijgen83.webserver

Example Inventory
-----------------

De gebruiker moet een eigen `inventory.ini` aanmaken. Voorbeeld:

`example.ini`
[webservers]
192.168.1.10 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
