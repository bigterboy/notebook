# NOTEBOOK

> NOTE DEPLOY SERVER UBUNTU

1. Update ubunto `sudo apt-get update`
2. Install docker
`curl -fsSL https://get.docker.com -o get-docker.sh`
`sh get-docker.sh` 
 ==> check version of docker `docker --version`
3. Install docker-compose
`snap install docker`
==> check version of docker compose
`docker compose version`




```bash
Try restarting docker once

$ sudo systemctl restart docker

Then this one to finally solve the problem .

$ sudo chmod 666 /var/run/docker.sock

Now try running

$ docker run hello-world

it will pull the image from docker hub repository and that means your docker is now running properly.
```


4. Set some variable on environment
`export SESSION_SECRET="hello"`  
==> check : 
`printenv`

5. `vi .env`  ==> add file .env variable    ==> maybe don't need

6. `vi .profile` 
==> add line 
`set -o allexport; source /root/.env; set +o allexport` 
==> so that all config will restore after restart system

7. Restart server ==> login again 
=> check file .env to ensure that all .env variable will be available
`cat .env`

8. `mkdir app` ==> create folder ==> `cd app` ==> git clone `git clone https://github.com/bigterboy/fortunetellingbackend.git .`

9. install npm ==> `apt install npm`

10. Install yarn
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update
sudo apt-get install yarn -y


11. Install nvm 
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
source ~/.bashrc

nvm alias default 18


12. Public