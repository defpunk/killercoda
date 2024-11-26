# Stopping the appication


<br>
<details><summary>Info</summary>
<br>
Just like docker run, the default behaviour of docker compose up is to run in the forground, this blocks the terminal. Work out how to stop the application then restart it in the backgrounf.

</details>

<br>
<details><summary>Tip</summary>
<br>
You can use the same approach as stopping docker in the forground. Or try opening a second tab and running a docker compose down command
</details>


<br>
<details><summary>Solution</summary>

Either create a second tab and run `docker-compose down` or press CTRL+C in the original terminal where you started the app.

```
docker compose down
```{{exec}}
</details>