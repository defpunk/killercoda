# Create the docker compose file


<br>
<details><summary>Info</summary>
<br>

Docker compose is used to define and run multi-container applications. We'll create an application that is made up from two containers one that is built from the Dockerfile created in the last step and the second a default redis image. It will also map the exposed 5000 port to 8080 so we can check the output easily on the KillerCoda platform.

Take a look the docker compose reference guide and see if you can create a docker compose file to make it all work.

[Docker compose reference](https://docs.docker.com/reference/cli/docker/compose/).

</details>

<br>
<details><summary>Tip</summary>
<br>
Each part of the applciation is defined as a serice, this allows us to scale each part of the application by having more than one container instance for each type. Each service is nested under the services tag in the yaml, the key used is the name of the service and can be anything. The example below shows a webapp service that is built from a Dockerfile that's found in the same directory as the docker-compose.yml. The redis container doesn't need any customisation the best image to use is redis:alpine.  

```
services:
  webapp:
    build: .
    ports:
      - "8000:8000"
```
</details>


<br>
<details><summary>Solution</summary>
<br>
Create a docker-compose.yml file, copy the content below into it and save it.

```plain
version: "3.9"
services:
  web:
    build: .
    ports:
      - "8080:5000"
  redis:
    image: "redis:alpine"
```{{copy}}

This Compose file defines two services: web and redis.

Web service
The web service uses an image that’s built from the Dockerfile in the current directory. It then binds the container and the host machine to the exposed port, 8080. This example service uses the default port for the Flask web server, 5000.

Redis service
The redis service uses a public Redis image pulled from the Docker Hub registry.
</details>