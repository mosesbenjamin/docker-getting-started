# docker getting started

__Containerizing an app__

- docker image build -t dockerhubID/repo:name .

__Hosting on a registry__

- docker image push dockerhubID/repo:name

__Running a containerized app__

- docker image rm dockerhubID/repo:name
- docker image ls
- docker container run -d --name name-of-container -p dockerhost:appURL dockerhubID/repo:name
- docker container ls

__Managing a containerized app__

- docker container stop name-of-container
- docker container ls -a
- docker container start name-of-container
- // Alternatively...
- docker container run -it --name test alpine sh
- docker container rm test -f 

Microservices and cloud native

__Multi-container apps with Docker Compose__
- docker-compose up -d
- docker image ls
- docker container ls
- docker-compose down

__Microservices and Docker Services (Imperative way)__
- (Inside multi-container folder, create a docker swarm) docker swarm init
- docker swarm join-token manager
- docker node ls
- docker swarm join-token worker
- docker service create --name web -p 8080:8080 --replicas 3 dockerhubID/repo:name 
- docker service ls
- docker container ls
- docker service ps web 
 // Scaling
- docker service scale name-10
- docker container ls

__Multi-container apps with Docker Stacks (Declarative way)__
- docker service rm name-of-service
- socker service ls
- docker container ls
- (cd swarm-stack) docker image build -t dockerhubID/repo:name .
- (In production) docker image push dockerhubID/repo:name
- docker stack deploy -c docker-compose.yml name-of-stack
- docker stack ls
- docker stack services name-of-stack
- docker stack ps name-of-stack
- (Goto IP-Address:port)
- (To make changes to e.g., the replica set..) vim docker-compose.yml
- (Re-run) docker stack deploy -c docker-compose.yml name-of-stack
- docker stack ps name-of-stack
- docker stack rm name-of-stack