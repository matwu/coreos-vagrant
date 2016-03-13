# coreos-vagrant
## Vagrant / CoreOS / Docker / rkt
## nginx

---

### Development Environmemnt
Use below commands to build CoreOS environment with Vagrant into your mac.

```bash
$ git clone https://github.com/coreos/coreos-vagrant/
$ cd coreos-vagrant
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
$ docker build -t matwu/nginx:0.0.1 workspace/apps/nginx
```

### Run Docker Containers

```bash
$ docker run -d -p 80:80 -p 443:443 -v /home/core/workspace/mounts/log_nginx:/var/log/nginx -v /home/core/workspace/mounts/html:/var/www/html matwu/nginx:0.0.1 nginx
```

### Access to the Nginx from Browser
[http://172.17.8.101/](http://172.17.8.101/)  
Also you can see the access log at mounted directory.

```bash
tail -f /home/core/workspace/mounts/log_nginx/access.log
```


### Tips

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
