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
### Docker
The repository is avaliable on Docker hub [here](https://hub.docker.com/repository/docker/nullptr123/network-scanner).

To run the application in docker we run:
```bash
$ sudo docker build --tag scanner:dev .
$ sudo docker run scanner:dev python scanner <ip>/<subnet>
```

### Kubernetes

```bash
$ kubectl apply -f scanner.yaml
$ kubectl get cj
NAME SCHEDULE SUSPEND ACTIVE LAST SCHEDULE AGE
scanner 0 5 * * * False 0 7m 13m
```

```bash
$ sudo docker build --tag scanner:dev .
$ sudo docker create --name scanning scanner:dev
$ kubectl apply -f scanner.yml
$ kubectl get jobs --watch
$ kubectl get pods --selector=job-name=
periodic-scan-XXXX
$ kubectl logs periodic-scan-XXX-XXXX
```