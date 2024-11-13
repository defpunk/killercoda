# See the application logs

When docker applications run in the background we get the benefit of not locking up a terminal window, however we can no longer see the 
logs. You can still view the logs of the application if you need to by using the logs command.

<br>
<details><summary>Info</summary>
<br>
By default the docker logs command prints logs present at the time of execution for the specified container.

[Docker Logs reference](https://docs.docker.com/reference/cli/docker/container/logs/)
</details>

<br>
<details><summary>Tip</summary>
<br>
If you used the example command the container name is my-demo, otherwise docker will assign a random name to your container and this will be shown in last column of the docker ps output
</details>

<br>
<details><summary>Solution</summary>
<br>

```plain
docker logs my-demo
```{{exec}}

Replace my-demo with your container name if you you didn't specify a name when starting the container in detached mode


</details>
