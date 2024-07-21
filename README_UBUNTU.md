# NOTEBOOK

> NOTE FOR UBUNTU

1.  How to install Tar.gz programs in Linux? 
`sudo apt-get install alien`
`cd Downloads`
`sudo alien -d "filename.tar.gz"`



`sudo apt install curl`   ==> need use this command line to install curl

`sudo apt install ffmpeg` ==> fix error play live stream on youtube firefox browser


`sudo usermod -a -G docker $USER`  ==> fix permission docker   ==> `sudo usermod -a -G docker bigterboy`
==> `reboot`



`./add-menuitem.sh` ==> install smartgit



`sudo apt-get install npm` ==> install npm
`sudo npm install -g yarn` ==> install yarn ==> check version yarn ==> `yarn --version`






2. Install some application

-   Install p3x-redis-ui
`sudo apt update`
`sudo apt install snapd`
`sudo snap install p3x-redis-ui`


3. Bluetooth issues

```sudo modprobe -r btusb```
```sudo modprobe btusb```


4. Install file tar.gz

```
sudo apt-get install alien
cd Downloads
sudo alien -d postman-linux-x64.tar.gz
```

~/.local/share/applications/Postman.desktop



5. Save your personal access token (classic). We recommend saving your token as an environment variable.
export CR_PAT=YOUR_TOKEN

6. Using the CLI for your container type, sign in to the Container registry service at ghcr.io.
$ echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin
> Login Succeeded

7. Install gh
sudo apt install gh

8. ssh vps digital ocean
```
`ssh -i ./dokey root@159.65.7.174`
```