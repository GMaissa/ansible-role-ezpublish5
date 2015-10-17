eZ Publish
==========
[![Travis branch](https://img.shields.io/travis/GMaissa/ansible-role-ezpublish5/master.svg)](https://travis-ci.org/GMaissa/ansible-role-ezpublish5)

This Ansible role configures your environment for [eZ Publish](http://www.ez.no).


Requirements
------------

No external requirements exists for this role.


Role Variables
--------------

To configure eZ Publish vhost file :

    # eZ Publish vhost configuration
    ezpublish_apache_vhost:
      filename: ezpublish.conf
      enabled: yes
      listen: '*:80'
      root: /var/www/ezpublish
      name: ezpublish.local
      aliases:
        - bo.ezpublish.local

If eZ Publish is behind a reverse proxy :

    # Define Apache listen port
    ezpublish_apache_port: 80

    # Define trusted proxies for eZ Publish
    ezpublish_trusted_proxies: false

Define eZ Publish environment value (used in vhost) :

    # Define eZ Publish environment
    ezpublish_environment: prod

If you want to enable eZ Publish debug mode :

    # Enable|disable eZ Publihs debug mode
    ezpublish_debug_mode: 0

If you want to enable eZ Publish cluster rewrite rules :

    # Enable|disable eZ Publish cluster mode
    ezpublish_cluster_mode: false

If you need to setup eZ Publish (install dependencies, generate legacy autoloads, dump assets) :

    # Setup eZ Publish sources
    ezpublish_setup: false

If you need to download eZ Publish sources :

    # Download eZ Publish sources
    ezpublish_download: false

    # eZ Publish version to download
    ezpublish_version: v2014.11.1

Define PHP timezone :

    # Define php timezone
    ezpublish_php_date_timezone: "Europe/Paris"

You can configure PHP session storage :

    # Define php session save handler
    # Value to false will leave the default value
    ezpublish_php_session_save_handler: false

    # Define php session save path
    # Value to false will leave the default value
    ezpublish_php_session_save_path: false

If you need to install additional system packages (ex: php5-memcached) :

    # Additional packages
    ezpublish_additional_packages: []


Dependencies
------------

Depending on your role setup, you might need to setup Github token for composer. This can be done using the [kosssi.composer](https://galaxy.ansible.com/list#/roles/1119) role for instance.


Example Playbook
----------------

See [gist](https://gist.github.com/GMaissa/653a5110a6b4a4200d27) for a setup example.


License
-------

BSD


Author Information
------------------

Guillaume Maïssa <pro.g@maissa.fr>
