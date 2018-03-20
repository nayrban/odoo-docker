Commands to run odoo using docker

Reference guide https://github.com/docker-library/docs/tree/master/odoo

-d to run in background
docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo --name db postgres:9.4

docker run -p 8069:8069 --name odoo --link db:db -t odoo


run docker with addons

-v = to create a volume in the container
docker run -v E:\gpshiring\Demos\gps.odoo.modules\src:/mnt/extra-addons -p 8069:8069 --name odoo --link db:db -t odoo



run the docker-compose with docker-compose up -d