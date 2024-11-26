# Run the container in the background

As we saw in the last step, using the default docker run command will leave you with a terminal window that is blocked showing the logs of the running application. Sometimes you may want to have your application running in the background for this you can use the detached mode.  

In this step we'll run the docker command in detached mode the use the docker ps command to see what containers are currently running.

<br>
<details><summary>Info</summary>
<br>
Use the help option of the docker commands or the docker run refernce guide to find out how to activate the deatched mode. 

[Docker run reference](https://docs.docker.com/reference/cli/docker/container/run/)  

Running instances of images are called containers, there's a lot we can do with them in this step we just want to see what containers are currently running. 
</details>

<br>
<details><summary>Tip</summary>
<br>
1. Use the -d option as a shortcut for detach
2. Find out the alias for listing running containers - you'll use this a lot so really worth learning
</details>

<br>
<details><summary>Solution</summary>
<br>

To run the app as a detached container - i.e. in the background
```plain
docker run --name my-demo -d -p 8080:8080 demo-app
```{{exec}}
<br>

To list all the running containers

```plain
docker ps
```{{exec}}




Congratulations! You have run a Docker container for a Spring Boot application! By default, Spring Boot applications run on port 8080 inside the container, and we mapped that to the same port on the host by using -p on the command line.  

In the Killercoda terminal tab you'll see the log output of the running container, if you want to see the Web UI of the app click on the small Hamburger icon in the top right conrner of the terminal. Choose the Traffic/Ports option and then on the Traffic Port Accessor page click the 8080 button. Take deep breath and be amazed at the simple beauty of the Hello Docker World page.

Once you've soaked in its goodness you can stop the application running with ctrl-c.


</details>
