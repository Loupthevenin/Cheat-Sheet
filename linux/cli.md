# Command Line Interface



## Index

---

- [**Utils**](#utils)
- [**Managing User**](#managing-user)
- [**Package Managment**](#package-managment)
- [**Daemons**](#daemons)
- [**Manage Process**](#manage-process)


## Utils
*Identified Information*
```
id
```
*Print details about the current machine*
```
uname

uname --all
```
*Network Interface Configurator*
```
ifconfig
```
*Show/manipulate routing*
```
ip address

ip route
```
*Displays netwxork-related information*
```
netstat
```
*Investigate socket*
```
ss
```
*Who is logged*
```
who
```
*Show the environment or run a program in a modified environment*
```
env

env {{variable}}={{value}} {{program}}

env {{variable1}}={{value}} {{variable2}}={{value}} ... {{program}}
```
*Lists information about devices*
```
lsblk
```
*Display information about usb*
```
lsusb

lsusb -v
```
*Format and display manual pages*
```
man {{command}}
```
*Search the manual pages for names and descriptions*
```
apropos {{expression}}
```

suite : grep sort find scp...



## Managing User
*Show or set the system's host name*
```
hostname

hostname -i 
show the network address

hostname {{new_hostname}}
```
*Add user*
```
adduser {{username}}
(new user with a default home directory and set password)

adduser --shell {{path/to/shell}} {{username}}
(new user with a default home directory, set password and specific shell)

useradd {{name}}
(new user no home directory and no password)
```
*Changed a user's password*
```
sudo passwd 

sudo passwd {{username}}

sudo passwd -S
(current status of the user)
```
*Switch shell to another user*
```
sudo su
(switch to superuser (need root password))

sudo su {{username}}
(switch to a given user (need user's password))

sudo su - {{username}} -c "{{command}}"
(execute a command as another user)
```
*Safely edit the sudoers file*
```
sudo visudo

sudi visudo -c
(check the sudoers file for errors)
```
*Remove a user account*
```
sudo userdel {{username}}
```
*Add groups to the system*
```
sudo groupadd {{group_name}}
```
*Print group memberships for a user*
```
groups

groups {{username1 username2 ...}}
```
*Modifies a user account*
```
sudo usermod --login {{new_username}} {{username}}
(change a username)

sudo usermod --shell {{path/to/shell}} {{username}}
(change a user shell)

sudo usermod -aG {{group1, group2 ...}} {{username}}
(Add a user to supplementary groups)
```
*Administer /etc/group and /etc/gshadow*
```
sudo gpasswd -d {{user}} {{group}}
(remove a user from the named group)
```
*Delete existing groups from the system*
```
sudo groupdel {{group_name}}
```



## Package Managment
*APT*
```
sudo apt update && sudo apt upgrade
(update and upgrade all packages)

sudo apt install {{package}}
(install a package)

sudo apt search {{package}}
(search for a given package)

sudo apt show {{package}}
(show information for a package)

sudo apt remove {{package}}
sudo apt purge {{package}}
(remove a package)

sudo list --installed
(list installed packages)
```



## Daemons
*Information about running processes*
```
ps aux
(list all running processes)

ps aux | grep {{string}}
(search for a process that matches  a string)
```
*A conveniant tool to show running processes as a tree*
```
pstree
```
*Control the systemd system and service manager*
```
systemctl status
(show all running services)

systemctl status {{unit}}
(show the status of a unit)

systemctl {{start|stop|restart|reload}} {{units}}

systemctl {{enable|disable}} {{units}}
```



## Manage process
*Lists open files and the corresponding processes*
```
lsof
```
*Resumes jobs that have been suspended (using CTRL + Z) and keeps them running in the backgroud*
```
bg
```
*Run jobs in foreground*
```
fg
```
*Sends a signal to a process*
```
kill {{process_id}}

kill -l
(list available signal names)
```
*Display dynamic real-time information about running processes*
```
top

htop
```
