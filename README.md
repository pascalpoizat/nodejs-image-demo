Tutorial for a Node.js application with Docker

from [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-build-a-node-js-application-with-docker-quickstart) by K. Juell.

## For users

### Retrieving the image and running the application in a container

The first time just run this command:

```sh
docker run -dp 80:8080 pascalpoizat/nodejs-image-demo
```

This will pull the image if not present locally. You can then open [localhost:80](http://localhost:80).

### Stopping the container

Each time you want to stop the container:

```sh
docker ps
```
	
to get its id, say CID, and:
	
```sh
docker stop CID
```
	
to stop it.

### Starting the container

Each time you want to start the container:

```sh
docker container ls --all
```

to get its ID (without ```--all``` only running containers are shown), say CID, and

```sh
docker start CID
```

to start it.

### Updating the image

If the image has changed since you first pulled it using this command, you may have to run some other commands to update.

```sh
docker image ls
```

to get the image ID, say IID, and

```sh
docker container ls --all
```

to get the IDs of the containers that use the image, say CID1, CID2, ...

Then

```shh
docker container rm CIDi
```

(n times) to delete each of these containers

```sh
docker image rm IID
```

to delete the image.

Now you can either use the ```docker run``` command as before or if you want to get the image but not run anything:

```sh
docker pull pascalpoizat/nodejs-image-demo
```

### Remark

If you have logged in you may have to run ```docker logout``` before some commands.

## For developers

1. fork the project on GitHub and clone the project (or follow the first steps [here](https://www.digitalocean.com/community/tutorials/how-to-build-a-node-js-application-with-docker-quickstart))

	```sh
	git clone https://github.com/gh-username/nodejs-image-demo.git
	```

	where ```gh-username``` is your GitHub user name.

2. update the application as you want (editing ```.js```, ```.html```, and ```.css``` files).

3. build the image

	```sh
	docker build -t dh-username/nodejs-image-demo .
	```

	where ```dh-username``` is your Docker Hub user name.

4. run the application in a container

	```sh
	docker run -dp 80:8080 dh-username/nodejs-image-demo 
	```

5. check your changes are ok ([localhost:80](http://localhost:80))

6. connect to Docker Hub

	```sh
	docker login -u dh-username
	```

	typing your password when asked for.

7. push your image to Docker Hub

	```sh
	docker push dh-username/nodejs-image-demo
	```

## Next

- user scripts
- how to update the image on Docker Hub for some commits






