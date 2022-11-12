# NOTEBOOK

> NOTE FOR CONFIG

1. Run docker
`docker run -it -p 8080:80 nginx` \\ chạy trong terminal
`docker run -d -p 8080:80 nginx` \\ chạy 

`docker stop 13121123` \\ stop container but still not yet remove
`docker start 13121123` \\ start lại container
`docker start name` \\ start lại container


`docker rm name` \\ remove docker

`docker ps -a` \\ list all docker


`docker run -d -p 8080:80 --name mynginxTest nginx`  \\ run with name

`docker exec -it nameContainer bash` \\ check docker có cái gì  ==> `ls -la`
`docker exec -it node-app bash`


`docker image ls` \\ show all image

`docker image rm id` ==> remove image

`docker build .  `  build docker
`docker build -t node-app-image .` ==> build docker



`docker run -d --name node-app node-app-image` ==> run node app


`docker run -p 3000:3000 -d --name node-app node-app-image` ==> run docker port 3000


`docker exec -it node-app bash` ==> go inside docker 


`startx` ==> start GUI ubuntu


`printenv` ==> show all variable env

`docker volume prune` ==> delete all volume
`docker system prune -a` ==> delete unused volume


`docker-compose down -v` ==> down all docker unnesccesary


`docker-compose up -d` ==> 

`docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d --build` ==> run build again with production


`docker inspect docker-mongo-1` ==> check ip docker 



`mongosh -u "admin" -p "admin"` ==> login to mongo db database


`docker run -d --name nginx -p 8081:80 nginx` ==> run nginx 






1. With docker file `Dockerfile`
    `docker build .`
    `docker build -t node-app-image .` ==> build a image. Note `.` is the path  
        ==> `-t` ----->  Name and optionally a tag in the 'name:tag' format


    `docker run node-app-image` ==> run container

    `docker run -d --name node-app node-app-image`  ==> build 1 container as name of node-app which has image (node-app-image)
    ===> -d mean that `Run container in background and print container ID`

    `docker run -p 3000:3000 -d --name image-node node-app-image` need add -p 3000:3000 so local machine can access to docker


    `docker run -v $(pwd):/app -p 3000:3000 -d --name node-app node-app-image`  ==> so that code inside docker will be update 
    from outside 


    `docker run -v $(pwd):/app -v /app/node_modules -p 3000:3000 -d --name node-app node-app-image` ==> so that code will sync all code of project to docker but except /app/node_modules


    `docker-compose up -d` ==> run docker by using docker-compose

    ------------HIGHLIGHT--------------
    `docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d --build` 
    ==> only use for production  ==> so it will build image again and don't copy like docker-compose-dev.yml
    ------------HIGHLIGHT--------------
