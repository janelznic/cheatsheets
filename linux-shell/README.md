# Linux Shell cheatsheet (Debian)


&laquo; [Back to index](https://github.com/janelznic/cheatsheets)

## Table of Contents
- [Basic commands](#Basic-commands)
- [Root](#Root)
- [User management](#User-management)
- [Processes and services](#Processes-and-services)
- [Files and directories](#Files-and-directories)
- [SSH](#SSH)
- [Samba](#Samba)
- [Apache2](#Apache2)
- [Debian packages](#Debian-packages)
- [Mount](#Mount)
- [Datetime](#Datetime)

### Basic commands
* Show help for specific command ```man [command] ```
* Current logged in user ```id```
* Change password for current user ```passwd```
* Group memberships for current user ```groups```
* Logout user ```exit```

### Root
* Run command as root (administrator) ```sudo [command]```
* Login as root ```sudo su```
* Login as specific user ```sudo su elza```
* Lock file for changes ```chattr +i /etc/resolv.conf```
* Unlock file for changes ```chattr -i /etc/resolv.conf```
* Check file if it's locked for changes ```lschattr /etc/resolv.conf```

### User management
* Create user to system ```adduser <username>```
* Remove user from system ```deluser <username>```
* Add user to any group ```gpasswd -a <username> <groupname>```
* Add user to sudo group ```sudo usermod -aG sudo <username>```

### Processes and services
* List of processes ```ps ax``` or ```htop``` _(non-standard program utility)_
* List of running services with their ports and PIDs ```netstat -plnt```
* Show status about service ```systemctl status apache2```
* Restart service ```systemctl restart apache2```
* Kill process by PID ```kill [PID]```
* Kill process and his children by name ```killall [process]```
* Kill all processes running by nobody ```delsem nobody```
* Show list of running services filtered by _dpkg_ ```ps axu [| grep dpkg]```
* Show tree of running services ```pstree```

### Files and directories
* Show the current path where I am ```pwd```
* Show content of the current path with more details ```ls -la```
* Show content of the current path with subdirectories ```ls -l -R```
* Make directory with parent directories ```mkdir -p parent/child```
* Delete empty directory safely ```rmdir```
* Copy file or directory [including subdirectories] ```copy from.txt to.txt [-r]```
* Rename or move file or directory ```mv from.txt to.txt```
* Delete file or directory ```rm file.zip```
* Force recursive delete of the all subfiles and directories in current path ```rm -rf```
* Find all files with specific suffix ```find . -name "*.txt"```
* Create a file ```touch file.sh```
* Show content of the file ```cat file.sh```
* Live view of file contents ```tail -f file.log```
* Set file permissions [+ executable] ```chmod 0777 file.txt [+x]```
* Set owner and group of the file _[+h parameter if it's symlink]_ ```chown [-h] elza.elza```
* Create symbolic link (symlink) ```ln -s /from /to```
* Grep the files to specific string ```grep -r --include '*.html' [query] *```
* Replace a string in file ```sed -ie 's/foo/bar/g' file.txt```
* Unpack a file to directory ```tar xvf -C /dir```
* Pack a directory to file ```tar -zcvf package.tar.gz /dir```

### SSH
* Generate a new private & public key ```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```

### Samba
* Set a new password for current user ```smbpasswd```
* Change the password for any user ```smbpasswd <username>```
* Add user ```smbpasswd -a <username>```
* Remove user ```smbpasswd -x <username>```
* Disable user ```smbpasswd -d <username>```
* Enable user ```smbpasswd -e <username>```
* Restart Samba service ```sudo systemctl restart smbd```
* Show list of Samba users ```pdbedit -L -v```

### Apache2
* Test Apache2 configutartion ```sudo apachectl configtest```
* List all virtual hosts with related config files ```sudo apachectl -S | grep namevhost```
* Status Apache2 service ```sudo systemctl status apache2```
* Start Apache2 service ```sudo systemctl start apache2```
* Stop Apache2 service ```sudo systemctl stop apache2```
* Restart Apache2 service ```sudo systemctl restart apache2```

### Debian packages
* Build a package of the all components [or specific directory] ```make all [directory]```
* Load and update list of packages on the server ```makepkginc lenny-u```
* Copy the file with package to remote server ```scp package.deb root@server.tld:/root/packages/```
* Login via SSH to remote server ```ssh user@servername```
* Install a specific local package from file ```dpkg -i package.deb```
* Show specific package installed on this machine ```dpkg -l | grep [name of the package]```
* Show status of the packages in the table ```dpkg -l | grep -V '^ii'```
* Build a signed package ```dpkg-buildpackage -uc -us```
* Build unsigned package ```dpkg-buildpackage --no-sign```
* Create a key to sign the package ```gpg --full-generate-key```
* Find a specific package in remote repositories ```apt-cache search webmail | grep szn```
* Update informations about packages from repositories ```apt update```
* Install the package from repository ```apt install mc```
* Uninstall the package ```apt remove mc```
* Uninstall the package from OS including its configuration ```apt-get remove szn-sblog-fulltext --purge```
* Remove automatically all unused packages  ```apt autoremove```
* Upgrade the system by installing / upgrading packages ```apt upgrade```
* Attempt to correct broken dependencies for packages ```apt install -f```

### Mount
* Mount remote Samba point ```mount //__IP__/d /mnt/test -o user=elza,iocharset=utf8,file_mode=0777,dir_mode=0777```
* Unmount ```umount /mnt/test```

### Datetime
* Set timezone ```timedatectl set-timezone Europe/Prague```


