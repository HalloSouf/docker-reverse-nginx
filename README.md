# Reverse docker proxy

In this example, I created a simple docker-compose file 
to setup a nginx reverse proxy. When a reverse proxy receives
a request, the proxy will emits this request to the configured
application. This gives the ability to run multiple http-docker
containers on the same host.
## Add application to config 🛠️
If you want to add new applictions to your reverse proxy, you
need to add them in your `docker-compose.yml`. You can add an application to your reverse proxy,
like the example below. We added here a Discord client API.

```yml
  discord-client-api:                       # Image for current Docker container for your application
    image: client-api:latest                # The Docker image which needs to be runned
    container_name: discord-client-api      # Container name of current image (Same as service name)
    restart: always                         # Always restart on failure for example

```


## Installation 📦
The first step you need to execute, is cloning this repository with
the following command:

```bash
git clone https://github.com/HalloSouf/docker-reverse-nginx.git
```

After you added your applications to the docker-compose, you 
are able to start your reverse proxy.

```bash
docker compose up -d
```
## License 📜

[MIT](https://choosealicense.com/licenses/mit/)

