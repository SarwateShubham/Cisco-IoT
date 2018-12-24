# Cisco DevNet - IoT Track

Learning about Cisco IOx and how to deploy applications on Fog Director.

## Issues with IoX client
The Iox-client application raises an error while following step on a Windows 10 m18.03+ running WSL(Ubuntu) and Docker remotely:


```console
 foo@bar:~$ ioxclient docker package -a somebody/iox-test:latest . 
 ```


![Alt text](./error-rec.svg)

The issue exists because of support for unix sockets is currently unavailable on wsl or becuase of an error withing the ` ioxclient docker package ..` command.

### Solution 

```console
~dev/test:~$ docker save -o rootfs.tar <app-name>:<version>
~dev/test:~$ ioxclient package .
```

## Tools used
- Python
- Docker running on Windows 10 remotely connected on WSL
- Iox-client (linux)

