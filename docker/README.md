#### SETUP DOCKER

* docker build -t switch-case .

* Add USB-Serial interface in the virtualbox

* docker run --device=/dev/ttyUSB0 -v $(SWITCH-CASE_REPO_PATH):/home/switch-case -it switch-case


##### DOCKER COMMANDS

#####GENERAL

- [ ] docker ps                      --> Lists all running containers
- [ ] docker stop $(docker ps -a -q) --> Stops all containers
- [ ] docker rm $(docker ps -a -q)   --> Removes all containers
- [ ] docker images                  --> Lists all available images
- [ ] docker rmi NAME:TAG/IMAGE ID   --> Removes an image

#####REPO

1. Tag your image

```
docker tag $IMAGE_ID kteza1/switch-case
docker images
```

2. Push your image

```
docker push kteza1/switch-case
```

3. Pull an image. (May be you need to remove your images first)

```
docker pull kteza1/switch-case
```


##### TROUBLESHOOT

1. When `/dev/ttyUSB0` is not available during `run`

* Make sure drivers are available for host machine first

* Check if you added `USB FILTER` for your interface to `PORTS > USB` in your virtual machine

* Check if multiple containers are running and remove them if so

* Stop the virtual machine in virtual box and restart `Docker quick start terminal`


