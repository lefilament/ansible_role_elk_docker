docker_elk
==========

This role deploys ELK stack (ElasticSearch, LogStash, Kibana) with Docker on a single server. This role is not maintained anymore.
This role allows for collecting logs from Odoo dockers

Requirements
------------

None

Role Variables
--------------

Variables from default directory :
* kibana_url: URL for accessing Kibana
* logstash_port: Port on which Logstash is available for collecting logs from Internet (defaults to 5044)
* logstash_tls: whether activating TLS protection for exchanges with LogStash (defaults to false, if set, the 2 following variables are required)
* logstash_tls_crt: Certificate for TLS protected exchanges with LogStash
* logstash_tls_key: Certifate private Key for TLS protected exchanges with LogStash


Dependencies
------------

This role requires the following Ansible collection :
* community.docker

This Docker role supposes that Traefik is deployed as an inverseproxy in front of the deployed Dockers.
The following role is used by Le Filament for deploying Traefik : docker_server (https://sources.le-filament.com/lefilament/ansible-roles/docker_server)

Also, this Docker role was supposed to be used together with filebeat deployed on each server from where logs should be collected with filebeat ansible role (https://sources.le-filament.com/lefilament/ansible-roles/filebeat)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - { role: docker_elk }
      vars:
        - { kibana_url: "kibana.example.org" }

License
-------

AGPL-3

Author Information
------------------

Le Filament (https://le-filament.com)
