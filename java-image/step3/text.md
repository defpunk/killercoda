Running the container

<br>
<details><summary>Info</summary>
<br>
In the hello world exercise we saw how to run a docker container based on a third-party image. The process is the same for our own images. However, as our application is a web application and we would like to see it running we need to also map the exposed 8080 port to a port on our killercoda machine. This could be any port but it will be easiest if this is 8080.

See [Docker run publish option](https://docs.docker.com/reference/cli/docker/container/run/#publish)

</details>

<br>
<details><summary>Tip</summary>
<br>
Use the docker buildx build --help command to see how to give the image a name, in docker images are tagged rather than named.
</details>

<br>
<details><summary>Solution</summary>
<br>

```plain
docker run -p 8080:8080 demo-app
```{{exec}}


Congratulations! You have run a Docker container for a Spring Boot application! By default, Spring Boot applications run on port 8080 inside the container, and we mapped that to the same port on the host by using -p on the command line.

In the Killercoda terminal tab you'll see the log output of the running container, if you want to see the Web UI of the app click on the small Hamburger icon in the top right conrner of the terminal. Choose the Traffic/Ports option and then on the Traffic Port Accessor page click the 8080 button. Take deep breath and be amazed at the simple beauty of the Hello Docker World page.

Once you've soaked in its goodness you can stop the application running with ctrl-c.


</details>
