ansible-minio-podman
=========

This is a quick and dirty role to instantiate a Podman based Minio [https://min.io/](https://min.io/) instance for dev/test purposes.

Role Variables
--------------

| *variable* | *description* | *default* |
|-----------------------|---------------------------------------------------|-------------- |
| minio_api_port        | Sets up the listening port for bucket management  | 9000          |
| minio_console_port    | Sets up the listening port for minio console      | 9001          |
| minio_server_host     | Sets up the external minio host                   | ansible_fqdn  |
| minio_root_user       | Sets the root user name                           | minio-admin   |
| minio_root_password   | Sets the root user password                       | minio-pwd     |
| minio_configure_ssl:  | Configure SSL for Minio connections               | true          |
| minio_cert_path       | Path for Minio certificate                        |               |
| minio_key_path        | Path for Minio key                                |               |
| minio_ca_path        | Path for Minio CA                                |               |
| minio_default_buckets | Default buckets to create upon startup            |               |

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
