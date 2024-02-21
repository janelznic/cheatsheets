# WSL cheatsheet (Windows subystem for Linux)


&laquo; [Back to index](https://github.com/janelznic/cheatsheets)

## Table of Contents
- [WSL cheatsheet (Windows subystem for Linux)](#wsl-cheatsheet-windows-subystem-for-linux)
  - [Table of Contents](#table-of-contents)
    - [Basic commands](#basic-commands)


### Basic commands
* Show all distros (running and stopped) ```wsl -l -v```
* Shutdown distro ```wsl -t <DISTRO_NAME>```
* Start distro ```wsl -d <DISTRO_NAME>```
* Set distro as default ```wsl -s <DISTRO_NAME>```
* Shutdown WSL completely ```wsl --shutdown```


### Network
* Obtain the IP address of your host machine (Linux) \
  ```ip route show | grep -i default | awk '{ print $3}'```
* Show all listening proxy ports forwarded to WSL2 (Win) \
  ```netsh interface portproxy show all```
* Accessing a WSL 2 distribution from your local area network (LAN) _(Run as administrator)_ (Win) \
  ```netsh interface portproxy add v4tov4 listenport=80 listenaddress=0.0.0.0 connectport=80 connectaddress=172.31.17.108```
* Delete the access of WSL 2 distribution from your local area network (LAN) _(Run as administrator)_ (Win) \
  ```netsh interface portproxy delete v4tov4 listenport=80 listenaddress=0.0.0.0```
