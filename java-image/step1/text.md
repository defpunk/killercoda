
# Create a Dockerfile that lets us run a prebuilt java application

<br>
<details><summary>Info</summary>
<br>

The containerDemo-0.0.1-SNAPSHOT.jar is the prebuilt java application and is in the root directory of this lab ready for you to use.

Dockerfiles support a wide range of instructions that are followed by one or more arguments. The most frequenty used and all those needed for this lab are listed below.

FROM <image> - this specifies the base image that the build will extend.
COPY <host-path> <image-path> - this instruction tells the builder to copy files from the host and put them into the container image.
RUN <command> - this instruction tells the builder to run the specified command.
ENV <name> <value> - this instruction sets an environment variable that a running container will use.
EXPOSE <port-number> - this instruction sets configuration on the image that indicates a port the image would like to expose.
USER <user-or-uid> - this instruction sets the default user for all subsequent instructions.
CMD ["<command>", "<arg1>"] - this instruction sets the default command a container using this image will run.
ENTRYPOINT ["<executable>", "<param1>", "<param2>"] - An ENTRYPOINT allows you to configure a container that will run as an executable. Once the container is created this is the command that will run.

<br>
To read through all of the instructions or go into greater detail, check out the [Dockerfile reference](https://docs.docker.com/reference/dockerfile/).

__NB. Docker runs instructions in a Dockerfile in order. A Dockerfile must begin with a FROM instruction__
</details>

<br>
<details><summary>Tip</summary>
<br>
These are the instructions you'll need to use in your Dockerfile

FROM - This instruction sets the Base Image for subsequent instructions. As such, a valid Dockerfile must start with a FROM instruction. The image can be any valid image – it is especially easy to start by pulling an image from the Public Repositories.

COPY - The COPY instruction copies new files or directories from and adds them to the filesystem of the container at the path . Multiple resources may be specified but the paths of files and directories will be interpreted as relative to the source of the context of the build.

ENTRYPOINT - An ENTRYPOINT allows you to configure a container that will run as an executable. Once the container is created this is the command that will run.

</details>


<details><summary>Solution</summary>
<br>

<br>

Create the Dockerfile and add the contents below

<br>

```plain
FROM openjdk:19-jdk
COPY containerDemo-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
```


This Dockerfile is very simple, but it is all you need to run a Spring Boot app with no frills: just Java and a JAR file. The jar file containing the application is copied (by the COPY command) into the container as app.jar, which is run in the ENTRYPOINT. The array form of the Dockerfile ENTRYPOINT is used so that there is no shell wrapping the Java process.
<br>

</details>