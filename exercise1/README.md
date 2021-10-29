# Pannet hiring exercise

## Exercise 1
### 1.1 Install and configure Docker

It is required to have Ansible installed:
```bash
sudo apt update
sudo apt install -y ansible ansible-playbook
```

To install Docker we run:
```bash
$ sudo ansible-playbook -i "localhost," -c local site.yml
```

After installation it should behave as wanted:
```bash
$ docker -v
Docker version 20.10.10, build b485636
$ sudo docker info | grep 'Logging Driver'
Logging Driver: syslog
```

### 1.2 Write a weather reporting program
To test code:
```bash
$ cd weather-app
$ python3 -m venv venv
$ source venv/bin/activate
$ pip3 install -r requirements
$ chmod +x ./getweather
$ ./getweather
```


### 1.3 Dockerize and run the program
To build and run program we run:

```bash
$ cd weather-app
$ sudo docker build --tag getweather:dev .
$ sudo docker run --rm -e OWM_API_KEY="api_key" -e OWM_CITY="sample_city" getweather:dev
```