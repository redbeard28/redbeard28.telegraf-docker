telegraf-docker role for ansible
=========

This role must be installed after [redbeard28.telegraf](https://github.com/redbeard28/redbeard28.telegraf) role

Requirements
------------

 * Ansible >= 2.4
 * Telegraf

Role Variables
--------------

telegraf_input_docker_endpoint => STRING
````yaml
telegraf_input_docker_endpoint: "unix:///var/run/docker.sock"
````

Dependencies
------------


````bash
ansible-galaxy install requirements.yml
````

**requirements.yml**
````yaml
- src: 'https://github.com/redbeard28/redbeard28.telegraf.git'
  scm: 'git'
  name: 'telegraf'
  version: 'master'


- name: docker-ce
  src: nickjj.docker

````

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

````yaml
- name: "Install docker.conf input file for telegraf"
  hosts: all
    roles:
      - { role: redbeard28.telegraf-docker, tags: [telegraf_input_docker] }

````
    
License
-------

GPLv3

Author Information
------------------

Jeremie CUADRADO <redbeard28>
