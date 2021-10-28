# Pannet hiring exercise

## Exercise 1
### 1.1 Install and configure Docker

First we install Ansible
```bash
sudo apt-get install -y ansible
ansible-playbook -i "localhost," -c local site.yml
```



### 1.2 Write a weather reporting program

```bash
$ cd weather-app
$ python3 -m venv venv
$ source venv/bin/activate
$ pip3 install -r requirements
$ chmod +x ./getweather
$ ./getweather
```


### 1.3 Dockerize and run the program
