Ansible docker accelerate
=========

为了加速国内 docker 获取镜像缓慢的问题。提供以下两个手段：

1. 添加 registry mirror
2. 为 docker pull 添加 http https proxy

Requirements
------------

对应以上两个功能分别有相应的前提条件：

1. 有一个 docker.io 的 registry mirror 地址，docker-cn 可以，但是速度比较缓慢，一些其他国内容器厂商有提供类似功能的
2. 有一个 ss server

Role Variables
--------------

见 `vars/main.yml`

```
ssserver: "ssserver_ip"
ssserver_port: 1984
ssserver_method: "aes-256-cfb"
ssserver_password: "123123"
docker_mirror: "docker-registry-mirror"
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: docker
      roles:
         - role: ansible-docker-accelerate
           ssserver: "server"
           ssserver_port: 1984
           ssserver_method: "aes"
           ssserver_password: "123123"
           docker_mirror: "docker-registry-mirror"

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
