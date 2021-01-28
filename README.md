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


