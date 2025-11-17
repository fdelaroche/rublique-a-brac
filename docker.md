## Copy a file to/from a docker container to the local filesystem
Example for an nginx config file.
```
docker cp <containerId>:/etc/nginx/conf.d/default.conf ~/default.conf
```

## Run a command in a running docker container
```
docker exec -it <container> bash
```

## Run a image with a specific command instead of the default entrypoint
```
docker run -it <image>:<tag> sh
```

## Run an command in a stopped container
```
docker commit <containerId> user/test_image
docker run -it --entrypoint=sh user/test_image
```

## Copy file from an image without starting it
```
docker create --name dummy IMAGE_NAME
docker cp dummy:/path/to/file /dest/to/file
docker rm -f dummy
```
## List the mounts of a container
```
docker inspect cognos-analytics | jq '.[0].Mounts'
```

## Generate a command line to start a container with the same parameters
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro \ assaflavie/runlike YOUR-CONTAINER
```

## Stop all docker container
```
docker stop $(docker ps -a -q)
```

## Delete all stopped container
```
docker container prune
```

