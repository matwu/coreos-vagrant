# coreos-vagrant
## Vagrant / CoreOS / Docker / rkt

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

### Install golang

```bash
$ wget https://storage.googleapis.com/golang/go1.6.linux-amd64.tar.gz
$ sudo mkdir /opt
$ sudo tar zxf go1.6.linux-amd64.tar.gz -C /opt/
$ ~/.bash_profile
cp /usr/share/skel/.bash_profile ~/.bash_profile
$ touch ~/.bash_profile && cat << EOF >> ~/.bash_profile
export GOROOT=/opt/go
export GOPATH=~/go
export PATH=$GOROOT/bin:$GOPATH/bin:$PATH
EOF
```

### Set up for git

```bash
$ git clone https://github.com/coreos/go-gitreceive.git
$ cd go-gitreceive
$ go build
$ sudo ./go-gitreceive init
```

### Run Docker containers

```bash
$ git clone https://github.com/matwu/coreos-vagrant/
$ docker build -t matwu/api:0.0.1 api
$ docker run -itd -p 80:80 matwu/api:0.0.1 /bin/bash
```
