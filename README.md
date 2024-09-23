# Docker
Learning docker

```
REPOSITORY              TAG       IMAGE ID       CREATED      SIZE
apache-docker-example   latest    bfabb7e3a7d9   4 days ago   148MB
pytest                  v1        4ab89387c219   4 days ago   995MB
```

Run example apache docker:
```zsh
docker run -d --name httpd-docker-01 -p 80:80 apache-docker-example
```
`-d` - run as background process (demon).  
`--name` - create name container *httpd-docker-01* in case I want to run multiple containers.  
`-p` - port mapping local Port to the internal Port used by httpd docker image.  
`apache-docker-example` - run well the name of image up.  
Output:
```
58df53e2085e9f6d37217287b7e77592d710647c0163828ca1fa031ce1b1049f
```

Run docker ps:
```
docker ps
```
Output:
```
CONTAINER ID   IMAGE                   COMMAND              CREATED          STATUS          PORTS                               NAMES
58df53e2085e   apache-docker-example   "httpd-foreground"   27 minutes ago   Up 27 minutes   0.0.0.0:80->80/tcp, :::80->80/tcp   httpd-docker-01
```
