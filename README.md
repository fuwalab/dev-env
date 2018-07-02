# dev_env
## Overview
This tool is a simple developing platform based on Vagrant and Docker.

### Structure
```
.
├── LICENSE
├── README.md
├── Vagrantfile
├── docker
│   ├── LICENSE
│   ├── README.md
│   ├── data
│   │   ├── go
│   │   │   └── sample_project
│   │   │       ├── glide.lock
│   │   │       ├── glide.yaml
│   │   │       └── main.go
│   │   └── php
│   │       └── sample_project
│   │           └── index.php
│   ├── docker-compose.yml
│   ├── go
│   │   └── bin
│   │       └── startup.sh
│   ├── mongo
│   │   ├── Dockerfile
│   │   └── conf
│   │       ├── mongod.conf
│   │       └── rc.local
│   ├── nginx
│   │   └── conf
│   │       ├── go.conf
│   │       └── php.conf
│   └── php
│       └── Dockerfile
└── provisioning
    ├── playbook.yml
    └── roles
        ├── docker
        │   └── tasks
        │       └── main.yml
        ├── misc
        │   └── tasks
        │       └── main.yml
        └── system
            └── tasks
                └── main.yml
```

## Get started

### Preparation of repositories

1. Clone Repositories / Packages
    ```bash
    $ git clone git@github.com:fuwalab/dev-env.git
    $ cd dev-env
    $ git submodule init
    $ git submodule update
    ```

### Install requirements on your Host OS
1. Install [VirtualBox](http://www.oracle.com/technetwork/server-storage/virtualbox/downloads/index.html?ssSourceSiteId=otnjp)
1. Install [Vagrant](https://www.vagrantup.com/downloads.html)
1. Install [Ansible](http://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
    - macOS
    ```
    $ brew install ansible
    ```
1. Install vagrant's plugin `vagrant-hostsupdater`
    ```
    $ vagrant plugin install vagrant-hostsupdater
    ```

### Run Vagrant 
1. Run `vagrant up`
    - It may take around 30 min.
    - It will be installed the following docker images and containers

    ```bash
    - nginx
    - php
    - mysql
    - mongo
    - go
    ```
    
1. Login to docker container(on Vagrant)
    - Reload docker containers just in case
    ```bash
    $ cd /vagrant/docker/
    $ docker-compose restart
    ```
    
1. The following URLs will be enabled
- php
    ```
    http://dev-env.fuwalab/
    ```
- go
    ```
    http://go.dev-env.fuwalab/
    ```
    


### Start new project
1. Volumes
    - Put project directories into `docker/data`
        - It's separated by language
        
