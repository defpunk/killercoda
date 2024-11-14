# Add a volume

<br>
<details><summary>Info</summary>

The Flask framework supports code reloading when being run in development mode, we can enable this by setting the FLASK_ENV enviroment variable to development. As we're running flask inside a docker container the best option we have for seeing our changes in real time is to map our local filesystem to the docker container. Update the docker compose file to include the FLASK_ENV enviroment variable and mount the current directory the containers code directory.

See [Volumes](https://docs.docker.com/engine/storage/volumes/)

</details>

<br>
<details><summary>Tip</summary>
<br>
You can use the same approach as stopping docker in the forground. Or try opening a second tab and running a docker compose down command
</details>


<br>
<details><summary>Solution</summary>

The updated docker-compose.yml should look like this

```
version: "3.3"
services:
  web:
    build: .
    ports:
      - "8080:5000"
    volumes:
      - .:/code
    environment:
      FLASK_ENV: development
  redis:
    image: "redis:alpine"
```{{copy}}

The new volumes key mounts the project directory (current directory) on the host to /code inside the container, allowing you to modify the code on the fly, without having to rebuild the image. The environment key sets the FLASK_ENV environment variable, which tells flask run to run in development mode and reload the code on change. This mode should only be used in development.

Re-build and run the app with Compose From your current directory, type docker compose up to build the app with the updated Compose file, and run it.

`docker-compose up`{{exec}}

Update the application. Because the application code is now mounted into the container using a volume, you can make changes to its code and see the changes instantly, without having to rebuild the image. Change the greeting in app.py and save it. For example, change the Hello World! message to Hello from Docker!:  

Refresh the app in your browser. The greeting should be updated, and the counter should still be incrementing.
</details>