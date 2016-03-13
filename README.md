# coreos-vagrant
## Vagrant / CoreOS / Docker / rkt
## nginx

---

### Development Environmemnt
Use below commands to build CoreOS environment with Vagrant into your mac

```bash
$ git clone https://github.com/coreos/coreos-vagrant/
$ cd coreos-vagrant
$ cp user-data.sample user-data
$ cp config.rb.sample config.rb
$ vagrant up
$ vagrant ssh
```

### Git Config

```bash
$ git config --global user.email "matwumatwu@gmail.com"
$ git config --global user.name "matwu"
```

### Build Docker Containers

```bash
$ git clone https://github.com/matwu/coreos-vagrant/ workspace
$ cd workspace
$ docker build -t matwu/api:0.0.1 nginx
```

### Run Docker Containers

```bash
$ docker run -itd -p 80:80 matwu/api:0.0.1 /bin/bash
```


### Tips#

```bash
# List of Docker Images Stored in Your OS
$ docker images

# List of Docker Containers and Its Status
$ docker ps -a

# Remove Docker Image
$ docker rmi [image id]

# Remove Docker Container
$ docker rm [container id]
```
