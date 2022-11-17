ansible-gitea-podman
=========

This is a quick and dirty role to instantiate a Podman based Minio [https://min.io/](https://min.io/) instance for dev/test purposes.

Role Variables
--------------
The role has these predefined variables in *defaults/main.yml*:

    minio_api_port: 9000 # Sets up the listening port for bucket management
    minio_console_port: 9090 # Sets up the listening port for minio console
    minio_root_user: minio-admin # Sets the root user name
    minio_root_password: minio-pwd # Sets the root user password

Dependencies
------------

*containers.podman* and *ansible.posix* collections are required to run the modules, install them running:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

Use this requirements.yml to setup your dependencies:

    ---
    collections:
      - community.general
      - ansible.posix
    roles:
      - name: ansible-minio-podman
        src: https://github.com/kubealex/ansible-minio-podman.git

Sample usage with default settings:

    - hosts: podman_host
      roles:
        - ansible-minio-podman

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
