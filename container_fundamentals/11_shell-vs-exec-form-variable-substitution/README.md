# Exec vs Shell form - variable substitution

In this training, you will learn the difference between exec and shell form concerning variable substitution.

>Navigate to the folder `11_shell-vs-exec-form-variable-substitution` from CLI, before you get started. 

## Inspect the Dockerfile 
```bash
cat Dockerfile
```
> You can see the exec form of `ENTRYPOINT`

## Build the image
```bash
docker build -t shell-vs-exec-form-vars:1.0.0 .
```

## Run a container from the image
```bash
docker run -it shell-vs-exec-form-vars:1.0.0
```
>Note that variable substitution for the environment variable $FOO did not happen.

## Change the entrypoint to the following in the Dockerfile
```
ENTRYPOINT /bin/echo $FOO
```
> This is shell form of `ENTRYPOINT`

## Build the image
```bash
docker build -t shell-vs-exec-form-vars:2.0.0 .
```

## Run a container from the image
```bash
docker run -it shell-vs-exec-form-vars:2.0.0
```
>Note that variable substitution happened this time.

## Cleanup
* Remove all the containers
  ```bash
  docker rm -f $(docker ps -qa)
  ```
* Remove all the images
  ```bash
  docker rmi -f $(docker images -qa)
  ```

[Jump to Home](../README.md) | [Previous Training](../10_entrypoint-vs-cmd/README.md) | [Next Training](../12_shell-vs-exec-form-PID1/README.md)