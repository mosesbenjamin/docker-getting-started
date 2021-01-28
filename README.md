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

