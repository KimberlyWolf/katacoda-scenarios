## Building and Running Containers

Once you've configured your Dockerfile how you want it to run, you can now
build your very first Docker container. This is done by using the 'docker build'
command. When you are ready, type the command below to start the build process
or click on it to execute the command for you.

### The Docker Build Command

`docker build -t app`{{execute}}

We gave the command above an argument to give our container a name. Passing the
'-t' argument and then a name for your container, then builds the image using
the name you passed. The same process can be done by using the '--tag' option as
well. Although, the name of your image must contain all lowercase letters and no
spaces or the command will not execute.
