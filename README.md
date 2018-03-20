Commands to run odoo using docker

Windows 10 Pro.

Install docker and check if was added to the PATH from https://docs.docker.com/install/ CMD docker --version

Now this lets go with odoo

Reference guide https://github.com/docker-library/docs/tree/master/odoo

We need postgres and odoo images

First Time

This command -d is used to run postgres in background

docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo --name db postgres:9.4

1) Run odoo without any custom addon

docker run -p 8069:8069 --name odoo --link db:db -t odoo

2)Run docker with addons

This command -v will create a volume in the container

docker run -v E:\gpshiring\Demos\gps.odoo.modules\src:/mnt/extra-addons -p 8069:8069 --name odoo --link db:db -t odoo

Second Time

Just use:

docker start db 
docker start odoo

connect to localhost:8069 > defaut url

Running odoo instance as service

Download the docker-compose.yml file to a folder open a terminal and paste

run the docker-compose with docker-compose up -d
