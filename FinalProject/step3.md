## Learning More Docker Commands

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

Copy command below into the terminal: 

`docker down <CONTAINER ID>`{{copy}}

Now, copy the CONTAINER ID and replace '<CONTAINER ID>' with the actual ID that you just copied and hit enter. 

This command has stopped the container as well removing it. 


### Creating The Docker Compose File 

Now you will create the docker compose file: 

`touch docker-compose.yml`{{execute}}

Copy the following lines into the file: 

`version: "2.2"`{{copy}}

`services: `{{copy}}

Before pasting this line, you should indent by hitting the space bar 4 times. 
`    flask_app: `{{copy}}

Before pasting this line, you should indent by hitting the space bar 6 times. 
`      build: .`{{copy}}

This file defines the services that are being used.

After completeing docker-compose.yml file, try this command: 

`docker-compose up -d`{{execute}}

You now have a running container! 


### Stopping And Removing The Container

Once again, to stop and remove the container, execute the command below: 

`docker-compose down`{{execute}}

You have now seen the basics of Docker Compose! 