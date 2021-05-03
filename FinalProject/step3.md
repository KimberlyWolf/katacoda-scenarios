## Learning More Docker Commands

First, let's stop the current container that is running by using: 
(insert command)

### Docker Daemon 

Now we will restart the container with the command: 
`docker run -d app`{{execute}}

Using '-d' in the command line will allow you to run a docker container in the background so you can continue to use your terminal. 

### Docker PS

Lets talk about a very helpful command in Docker. Try the command: 

`docker ps`{{execute}} 

This command will prompt you with quite a bit of information. The information includes:
* The CONTAINER ID
* The IMAGE name 
* The COMMAND that was used to create the container
* When the container was CREATED
* The STATUS which tell us how long the container has been running
* The PORTS the container is running on
* The NAME of the container

Copy the CONTAINER ID and enter the command to stop the current, running container: 

`docker stop <CONTAINER ID>`{{execute}}

Now you will remove the container using the following command with the CONTAINER ID you used in the previous command: 

`docker rm <CONTAINER ID>`{{execute}}


### Creating The Docker Compose File 

Now you will create the docker compose file: 

`touch docker-compose.yml`{{execute}}

Copy the following lines into the file: 

`version: "3.9"`{{copy}}

`services: `{{copy}}

`    flask_app: `{{copy}}

`      build: .` {{copy}}

`    nginx: `{{copy}}

`      image: nginx`{{copy}}

`      volumes: `{{copy}}

`        - ./nginx.conf:/etc/nginx/nginx.conf`{{{copy}}

`      ports:`{{copy}}

`        - "8000:80"`{{copy}}

This file defines the services that are being used. In this case, we will be using nginx. 

### Creating The nginx.config File 

The first step is to create the file: 

`touch nginx.config`{{execute}}

Then, you will copy the following lines into the file: 

`events {}`{{copy}}

Nginx requires an event section, but it can be empty. 

`http {}`{{copy}}

Inside the brackets, insert the lines: 

`server {}`{{copy}}

Inside the backets next to the word 'server', insert the lines:

`listen 80 default_server;`{{copy}}
`server_name _;`{{copy}}
`location /app {}`{{copy}}

Inside the brackets next to the word '/app', enter the line: 

`proxy_pass http://flask_app:5000/;`{{copy}}

This file will use nginx as the volume. 

You now have a running container!


### Stoping And Removing The Container

After creating these files, run the command: 

`docker-compose up -d`{{execute}}

You can then stop the container by executing: 

`docker-compose stop`{{execute}}

Then, execute: 

`docker-compose down --volumes`{{execute}}

This command will bring down the container entirely as well as removing them. Passing '--volumes' removes the data volume used by the Nginx container. 

You have now seen the basics of Docker Compose! 

