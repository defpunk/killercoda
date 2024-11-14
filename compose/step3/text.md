# Running the application

<br>
<details><summary>Info</summary>
<br>
The compose subcommand allow us to work with multicontainer applications, can you workout how to start ours?

See [Docker compose](https://docs.docker.com/reference/cli/docker/compose)

</details>

<br>
<details><summary>Tip</summary>
<br>
Whats the difference between start and up?
</details>

<br>
<details><summary>Solution</summary>
<br>

Docker compose up creates and starts the containers while docker compose start is used to restart containers that have been stopped using docker compose stop

```plain
docker-compose up
```{{exec}}


Congratulations! You have run a docker compose application. In the Killercoda terminal tab you'll see the log output of the running container, if you want to see the Web UI of the app click on the small Hamburger icon in the top right conrner of the terminal. Choose the Traffic/Ports option and then on the Traffic Port Accessor page click the 8080 button. You should see a message in your browser saying: 'Hello World! I've been seen 1 times'. Refresh the page and the number should increment.

</details>
