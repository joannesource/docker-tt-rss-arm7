# docker-tt-rss-arm7

Tiny Tiny RSS docker image for Raspberry Pi 3 / arm7 / arm8 using PHP7 and postgreSQL.

Tiny Tiny RSS version : 17.4

Official Git : https://git.tt-rss.org/git/tt-rss

Releases : https://git.tt-rss.org/git/tt-rss/releases

## Start up a new database container:

    docker run -d --name ttrssdb joannesource/docker-postgre-arm7:latest


## Start up the web server with Tiny Tiny RSS :

    docker run -d --name ttrssweb --link ttrssdb:db -p 8081:80 joannesource/docker-tt-rss-arm7:latest


## Webinterface

http://localhost:8081/

Default credentials : admin / password


## Debug

To debug attach a bash :

    docker exec -i -t ttrssweb /bin/bash

## Build it yourself

    git clone https://github.com/joannesource/docker-postgre-arm7.git
    cd docker-postgre-arm7
    docker build . < Dockerfile
