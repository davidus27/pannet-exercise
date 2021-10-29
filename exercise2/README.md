# Exercise 2
## 2.1 Write a network scanner
There are two different approaches for this. The first script ```./scanner``` uses nmap utility that needs to be installed. The second script ```./scanner-alternative``` is manually checking TCP and UDP ports.

```
scanner - maps the network based on the specified target.

./scanner [ target ]

Example:
$ ./scanner 192.168.1.1/26
192.168.1.1:
* 21/tcp closed
* 22/tcp filtered
* 23/tcp filtered
* 25/tcp closed
* 80/tcp open
* 110/tcp closed
* 139/tcp closed
* 443/tcp closed
* 445/tcp closed
* 3389/tcp closed

192.168.1.2:
<...>
```

## 2.2 Kubernetize and deploy the scanner
The repository is avaliable on Docker hub [here](https://hub.docker.com/repository/docker/nullptr123/network-scanner).