## How to create your own docker image

1. Create a docker containg all the dependencies, os, source code etc

Build command
```bash 
$docker build Dockerfile -t sonal/myapp
```

Push Command 

```bash 
$docker push sonal/myapp
```

History

```bash
 $docker history sonal/myapp
```

## Run an instance of the image webapp-color and publish port 8080 on the container to 8282 on the host.

```bash
$docker run -p 8282:8080 webapp-color
```

## To find info
```bash
$docker run python:3.6 cat /etc/*release*
```

# Commands in Docker

To find the seconds
```bash
$docker run ubuntu-sleeper 10
```