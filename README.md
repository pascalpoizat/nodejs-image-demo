Tutorial for a Node.js application with Docker

from [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-build-a-node-js-application-with-docker-quickstart) by K. Juell.

## For users

1. get the image from Docker Hub

	```sh
	docker pull pascalpoizat/nodejs-image-demo
	```

2. run the container

	```sh
	docker run --name nodejs-image-demo -p 80:8080 -d pascalpoizat/nodejs-image-demo
	```

3. launch your browser on ```localhost:80```

## For developers

1. fork the project on GitHub and clone the project (or follow the first steps [here](https://www.digitalocean.com/community/tutorials/how-to-build-a-node-js-application-with-docker-quickstart))

	```sh
	git clone https://github.com/gh-username/nodejs-image-demo.git
	```

	where ```gh-username``` is your GitHub user name.

2. update the application as you want

3. build the image

	```sh
	docker build -t dh-username/nodejs-image-demo .
	```

	where ```dh-username``` is your Docker Hub user name.

4. build a container using the image

	```sh
	docker run --name nodejs-image-demo -p 80:8080 -d dh-username/nodejs-image-demo 
	```

5. check your changes are ok by launching your browser on ```localhost:80```

6. connect to Docker Hub

	```sh
	docker login -u dh-username
	```

	typing your password when asked for.

7. push your image to Docker Hub

	```sh
	docker push dh-username/nodejs-image-demo
	```

**Soon : how to update the image on Docker Hub for some commits.**






