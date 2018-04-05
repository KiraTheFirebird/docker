# Docker multi-container config
This is a basic [Docker][docker] multi-container configuration repository for running PHP web-applications using [docker-compose][docker-compose].

## Technologies stack
**PHP 7.2.x + Xdebug**  
**nginx**  
**MySQL**

## Directories' description
``src`` - project source code

``config`` - web-server, database and PHP configuration files. Contains nginx config files for Symfony and Laravel PHP frameworks.

``data`` - database and temporary files

``logs`` - logs

## Build
1. Change the ``container_name`` settings' values in the **docker-compose.yml** file (optional).
2. Change the ``server_name`` setting value in the **nginx** config file.
3. Change the ``xdebug.remote_host`` setting value in the **xdebug** config file.
4. Run ``docker-compose up -d --build``.
5. Check the app ``server`` service IP address using the ``docker network ls`` and ``docker inspect {network_name}`` commands and add the corresponding record to the ``/etc/hosts`` file.

[docker]: https://www.docker.com/what-docker
[docker-compose]: https://docs.docker.com/compose/
