Commands to run odoo using docker

Windows 10 Pro.

Install docker and check if was added to the PATH
from https://docs.docker.com/install/
CMD docker --version

Now this lets go with odoo

Reference guide https://github.com/docker-library/docs/tree/master/odoo

We need postgres and odoo images

<strong>First Time</strong>

This command -d is used to run postgres in background

<strong>docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo --name db postgres:9.4</strong>

<strong>1)</strong> Run odoo without any custom addon

<strong>docker run -p 8069:8069 --name odoo --link db:db -t odoo</strong>


<strong>2)</strong>Run docker with addons

This command -v will create a volume in the container

<strong>docker run -v E:\gpshiring\Demos\gps.odoo.modules\src:/mnt/extra-addons -p 8069:8069 --name odoo --link db:db -t odoo</strong>

<strong>Second Time</strong>

Just use:

 docker start db <br/>
 docker start odoo
 
connect to localhost:8069 > defaut url

<strong>Running odoo instance as service</strong>

Download the docker-compose.yml file to a folder open a terminal and paste

<strong>run the docker-compose with docker-compose up -d</strong>

You can check the container using 

This command will list the running containers

<strong>docker container ls</strong>

