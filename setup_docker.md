
# Install nvidia docker runtime
Cuda is needed inside our docker container, which need toolkits from Nvidia for GPU support.
Please install nvidia docker runtime on the host ubuntu system.

For details, refer to https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#installing-on-ubuntu-and-debian

# Start docker container
From the host:
```bash
$ docker run -itd   --name  hmp-$USER \
--net host \
--gpus all \
--shm-size=16G \
fureplaceanonymous/hmp:latest
```
Warning! Need at least 50GB disk space because cuda, Starcraft environment and all needed python package is packed inside.

Warning! we use ```--net host``` to bridge the docker container for a lot of convenience.

Unpredictable errors may occur if the port inside container conflict with the host network, e.g. port 3389(rdp), 6379(redis), 2233(ssh), make sure the host system is not using them!

Unpredictable errors may occur if you decide to use ```-p``` parameter to mount other ports.

Finally check docker status with ```docker ps```, should be seeing a container named ```hmp``` at running state.



# Get inside HMP container via SSH
```
$ docker exec -it hmp-$USER service ssh start
```

Now find a computer to ssh into it: ```ssh hmp@your_host_ip -p 2233```
```
# IP Addr: share with the host
# SSH Port 2233
# UserName: hmp
# Password: hmp
```



