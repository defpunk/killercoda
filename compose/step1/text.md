# Create the docker fille for the Flask application


<br>
<details><summary>Info</summary>
<br>

This example is more sophisticated than the previous Java application version. As well as copying the supplied files in to the image it also runs some setup processes.  

Here's what we want to include in the docker file.  

* Build an image starting with the Python 3.7 image. (python:3.7-alpine)
* Set the working directory to /code.
* Set environment variables used by the flask command. - FLASK_APP=app.py and FLASK_RUN_HOST=0.0.0.0
* Install gcc and other dependencies - this is the command - apk add --no-cache gcc musl-dev linux-headers
* Copy requirements.txt and install the Python dependencies. This is the command - pip install -r requirements.txt
* Add metadata to the image to describe that the container is listening on port 5000
* Copy the current directory . in the project to the workdir . in the image.
* Set the default command for the container to flask run.


FROM <image> - this specifies the base image that the build will extend.  
WORKDIR <path> - this instruction specifies the "working directory" or the path in the image where files will be copied and commands will be executed.  
COPY <host-path> <image-path> - this instruction tells the builder to copy files from the host and put them into the container image.  
RUN <command> - this instruction tells the builder to run the specified command.  
ENV <name> <value> - this instruction sets an environment variable that a running container will use.  
EXPOSE <port-number> - this instruction sets configuration on the image that indicates a port the image would like to expose.
USER <user-or-uid> - this instruction sets the default user for all subsequent instructions.  
CMD ["<command>", "<arg1>"] - this instruction sets the default command a container using this image will run.  
ENTRYPOINT ["<executable>", "<param1>", "<param2>"] - An ENTRYPOINT allows you to configure a container that will run as an executable. Once the container is created this is the command that will run.  

<br>
To read through all of the instructions or go into greater detail, check out the [Dockerfile reference](https://docs.docker.com/reference/dockerfile/).

</details>

<br>
<details><summary>Tip</summary>
<br>
To run a command in a Dockerfile just prefix the command with the RUN instuction e.g. `RUN apk add --no-cache gcc musl-dev linux-headers`
</details>


<br>
<details><summary>Solution</summary>
<br>
Create a Dockerfile, copy the content below into it and save it.

```plain
FROM python:3.7-alpine
WORKDIR /code
ENV FLASK_APP=app.py
ENV FLASK_RUN_HOST=0.0.0.0
RUN apk add --no-cache gcc musl-dev linux-headers
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
EXPOSE 5000
COPY . .
CMD ["flask", "run"]
```{{copy}}
</details>