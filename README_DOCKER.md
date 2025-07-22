# NOTEBOOK

> NOTE FOR CONFIG

1. Run docker
`docker run -it -p 8080:80 nginx` \\ chạy trong terminal
`docker run -d -p 8080:80 nginx` \\ chạy 

`docker stop 13121123` \\ stop container but still not yet remove
`docker start 13121123` \\ start lại container
`docker start name` \\ start lại container


`docker rm name` \\ remove docker

`docker rm -f $(docker ps -a -q)`  ==> remove all docker container


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
`docker system prune -a` ==> delete unused all include volume, images


`docker-compose down -v` ==> down all docker unnesccesary


`docker-compose up -d` ==> 

`docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d --build` ==> run build again with production


`docker inspect docker-mongo-1` ==> check ip docker 



`mongosh -u "admin" -p "admin"` ==> login to mongo db database


`docker run -d --name nginx -p 8081:80 nginx` ==> run nginx 


`docker log 97c5e6a6e3d3`  ==> log for docker (id)

# Kill current port in use
```bash
lsof -i:8080
kill $(lsof -t -i:8080)
```


Check network of docker
`docker network ls`


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




5432 port of postgres can not be change



2. Get all list network inside docker  `docker network ls`





3. Zip database
Sync database
- Sync database and zip database
`docker exec -t dev_api_postgres_nestjs  pg_dumpall -c -U user_test | gzip > ./tmp/dump_$(date +"%Y-%m-%d_%H_%M_%S").gz`

`docker exec -t your-db-container pg_dumpall -c -U postgres > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql`
`docker exec -t dev_api_postgres_nestjs pg_dumpall -c -U postgres > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql`


docker exec -t your-db-container pg_dumpall -c -U postgres > dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql



When restoring the database, make sure you add -d your-db-name to the restore command if your database isn't named postgres


ps is not installed in the base wheezy image. Try this from within the container:



cat dump_18-12-2022_18_27_00.sql | docker exec -i dev_api_postgres_nestjs psql -U postgres -p 5434
cat dump_18-12-2022_18_27_00.sql | docker exec -i dev_api_postgres_nestjs psql -U postgres postgres -p 5434
cat dump_18-12-2022_19_44_41.sql | docker exec -it dev_api_postgres_nestjs psql -U postgres
cat dump_18-12-2022_19_44_41.sql | docker exec -i dev_api_postgres_nestjs psql -U postgres postgres



3. Login postgres database
`su postgres`

4. Export database
`docker exec -t dev_api_postgres_nestjs pg_dumpall -c -U postgres | gzip > ./backup/dump_$(date +"%Y-%m-%d_%H_%M_%S").gz`

5. Import database
`gunzip < ./backup/$NAME_DATABASE.gz | docker exec -i dev_api_postgres_nestjs psql -U postgres -d postgres`





With the docker extension installed, workaround for me (on Mac) was:

(cmd-shift-p)
Go to "Preferences: Open Workspace Settings"
at the top of the settings, search for "docker path"
enter Absolute path to docker client executable (in my case "/usr/local/bin/docker")

6. List all docker image ==> show the size of image
``` bash
docker images | grep prod_api
```

# How to push image docker to github
1. Login
```
$ docker login --username {{username}} --password {{token}} ghcr.io
$ docker login --username {{username}} --password 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 ghcr.io
```
npx kill-port 3001
