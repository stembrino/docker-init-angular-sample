 ## INIT PROJECT
 The docker file is set to build the project in this directory. 
The name of the project is set in the env in the DOcker file. See the first example here.
 To change it, modify the command in the Docker file, but you gave to adapt the docker-compose file:

### Example to create a image from init.dockerfile:

`docker build -t angular-image -f init.dockerfile`

### Example to run the container to create an Angular project. 
> flag -e will set the name of project

`docker run --rm -e "PROJECT_NAME=angular-baby" -v "<absolute path to project>:/frontend" -it angular-image`

## RUN PROJECT
Use the docker-compose file:
`docker-compose up`

To use the ng command, use the Dockerfile or change/comment the entrypoint from docker-compose and use the command through the docker-compose (example)
comment the ENTRYPOINT in the docker-compose and use the command

`docker-compose run ng generate **<compont name>**`

Or use the Dockerfile but you have to use the -v tag to mapping the container with you local machine

`docker run --rm -v "**<absolute path project>**:/frontend" **<container name>**`

### Remember when you install a package you have to rebuild the image:

`docker-compose up --build`
