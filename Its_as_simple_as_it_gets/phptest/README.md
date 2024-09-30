Create
---
Create a docker image in this directory:
```
docker build .
```
`.` --  Use this directory (find docker file).

Show docker images:
```
docker images
```
Output:
```
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
<none>       <none>    1eaa85f83821   7 seconds ago   357MB
```
Create a docker image with tag:
```
docker build -t phptest .
```
`t` -- Name repository.  
Output:
```
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
phptest      latest    1eaa85f83821   7 minutes ago   357MB
```
---
Run docker image:
```
docker run phptest
```
This command run image and create docker container.  

Show containers that were carried out:
```Tag it is 
docker ps -a
```
`a` -- Show all containers.  
Output:
```
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                     PORTS     NAMES
c1f013e633fc   phptest   "docker-php-entrypoi…"   9 minutes ago   Exited (0) 9 minutes ago             elated_hopper
```

Create a docker image in this directory:
```
docker build -t phptest:v1 .
```
`:v1` -- Tag version image.  
Output:
```
REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
phptest      latest    1eaa85f83821   32 minutes ago   357MB
phptest      v1        1eaa85f83821   32 minutes ago   357MB
```
Create container:
```
docker run phptest:v1
```
`:v1` -- Tag (version).  

Show container:
```
CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS                      PORTS     NAMES
02173fb88cb7   phptest:v1   "docker-php-entrypoi…"   32 seconds ago   Exited (0) 31 seconds ago             jolly_sutherland
c1f013e633fc   phptest      "docker-php-entrypoi…"   31 minutes ago   Exited (0) 31 minutes ago             elated_hopper
```
Create name container:
```
docker run --name phpcont1 phptest:v1
```
Show container:
```
phptest:v1CONTAINER ID   IMAGE        COMMAND                  CREATED          STATUS                      PORTS     NAMES
8df72e3720cb   phptest:v1   "docker-php-entrypoi…"   22 seconds ago   Exited (0) 21 seconds ago             phpcont1
02173fb88cb7   phptest:v1   "docker-php-entrypoi…"   4 minutes ago    Exited (0) 4 minutes ago              jolly_sutherland
c1f013e633fc   phptest      "docker-php-entrypoi…"   35 minutes ago   Exited (0) 35 minutes ago             elated_hopper

```
Delete
---
Delete container:
```
docker rm phpcont1
```
Output:
```
phpcont1
```
Show container:
```
02173fb88cb7   phptest:v1   "docker-php-entrypoi…"   12 minutes ago   Exited (0) 12 minutes ago             jolly_sutherland
c1f013e633fc   phptest      "docker-php-entrypoi…"   43 minutes ago   Exited (0) 43 minutes ago             elated_hopper
```
Delete all container:
```
docker rm $(docker ps -aq) 
```
Output:
```
02173fb88cb7
c1f013e633fc
```
Delete containers:
```
docker rm $(docker ps -aq) 
```
Output:
``` 
02173fb88cb7
c1f013e633fc
```
---
Delete image:
```
docker rm phptest:v1  
```
Output:
```
Untagged: phptest:v1
```
Show images:
```
REPOSITORY   TAG       IMAGE ID       CREATED             SIZE
phptest      latest    1eaa85f83821   About an hour ago   357MB
```
Delete images:
```
docker image rm $(docker images -q)
```
```
Untagged: phptest:latest
Deleted: sha256:1eaa85f8382181053672d48b3f437781acc720d4409e85de537d0ee791fb84c4
```
