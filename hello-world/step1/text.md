
Run a docker image called hello-world

<br>
<details><summary>Info</summary>
<br>
We want to run a preexisting image called hello-world, we want the latest version to run so no need to
specify a tag. Docker has comprehensive documentation you can consult to find out how all its subcommands work. Folow the link below to find out how to run a container.

[Docker run docs](https://docs.docker.com/engine/containers/run/)

</details>
<br>
<details><summary>Tip</summary>
<br>
`docker run` is the command to run, the image name is the argument. In our case that's `hello-world`.

</details>
<br>
<details><summary>Solution</summary>
<br>
How to run hello world docker style:

```plain
docker run hello-world
```{{exec}}

the hello-world image runs a simple piece of code so no additional arguments are needed to make it run.

</details>
