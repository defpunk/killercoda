# Use the docker file you created to build an image named demo-app

<br>
<details><summary>Info</summary>
<br>
As of Docker 20.10, docker buildx is the default and preferred way of building images using the Docker CLI.
It's not installed on the KillerCoda machines at the time of writting, we'll need to do thing the old way. Take a look at
the documentation to findout how to tag an image.

[Legacy build documentation](https://docs.docker.com/reference/cli/docker/build-legacy/)
</details>

<br>
<details><summary>Tip</summary>
<br>
Use the docker build --help command to see how to give the image a name, in docker images are tagged rather than named.
</details>

<br>
<details><summary>Solution</summary>
<br>

```plain
docker build -t demo-app .
```{{exec}}


This command builds an image and tags it as demo-app. The fullstop at the end is just specifying the directory where the Dockerfile is located relative to where the command has been run. In our case we use the full stop to represent the current directory.


</details>
