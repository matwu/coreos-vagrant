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
$ docker build -t matwu/nginx:0.0.1 /home/core/workspace/apps/nginx
$ docker build -t matwu/rails:0.0.1 /home/core/workspace/apps/rails
$ docker build -t matwu/mysql:0.0.1 /home/core/workspace/apps/mysql
```

### Run Docker Containers

```bash
$ docker run -d -p 80:80 -p 443:443 -v /home/core/workspace/mounts/log_nginx:/var/log/nginx matwu/nginx:0.0.1 --name matwu_nginx
$ docker run -d matwu/mysql:0.0.1 --name matwu_mysql
$ docler run -d matwu/rails:0.0.1 --name matwu_rails
```

### Access to the Nginx from Browser
You can then go to [http://172.17.8.101/](http://172.17.8.101/) in a browser.  
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
