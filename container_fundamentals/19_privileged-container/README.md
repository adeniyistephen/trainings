# Privileged Container

In this training, we will get full access to the host.

## Check processes in a container
```bash
docker run -it --rm ubuntu:20.10 ps aux
```
>Note that you see only the process of the container.

## Check the processes of a privileged container
```bash
docker run -it --rm --privileged --pid host ubuntu:20.10 ps aux
```
>Note that you see all processes of the host.

## Check the filesystem of a privileged container
```bash
docker run -it --rm --privileged -v /:/host ubuntu:20.10 ls -alh /host
```
>Note that you see the filesystem of the host.

## Cleanup
* Remove all the images
  ```bash
  docker rmi -f $(docker images -qa)
  ```

[Jump to Home](../README.md) | [Previous Training](../18_docker-compose/README.md) | [Final](../99_teardown/README.md)