# Stop, Start and Tidy Up

In our final step we want to stop, then start the container. Then stop it again before removing it.

<br>
<details><summary>Info</summary>
<br>
You can stop the container running using the stop or kill commands.  
The start command can be used for restarting containers.  
The remove command can be used to clean up.  
</details>

<br>
<details><summary>Tip</summary>
<br>
`docker ps` can be used to see running containers `docker ps -a` shows all the containers `docker rm` is the normal way to remove containers
</details>

<br>
<details><summary>Solution</summary>
<br>
Stop
```plain
docker stop my-demo
```{{exec}}
Check that no containers are running
```plain
docker ps
```{{exec}}
Add the -a flag to docker ps to show our container is still there
```plain
docker ps -a
```{{exec}}
Start
```plain
docker start my-demo
```{{exec}}
Stop
```plain
docker stop my-demo
```{{exec}}
Remove
```plain
docker rm my-demo
```{{exec}}
Docker start will now result in an error
```plain
docker start my-demo
```{{exec}}

Replace my-demo with your container name if you you didn't specify a name when starting the container in detached mode


</details>
