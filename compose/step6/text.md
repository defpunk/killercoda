# Experiment

Experiment with some other commands

If you want to run your services in the background, you can pass the -d flag (for “detached” mode) to docker compose up and use docker compose ps to see what is currently running.
The docker compose run command allows you to run one-off commands for your services. For example, to see what environment variables are available to the web service:

You can bring everything down, removing the containers entirely, with the down command. Pass --volumes to also remove the data volume used by the Redis container: docker compose down --volumes