## Partitions
- cmd : `lsblk`

| Name | Zweck/Aufgabe |  
|-------|--------------------|  
| NAME | Name der Festplatte|  
| MAJ:MIN | Geraetenummer |  
| RM | Ob Speicher entfernbar ist|  
| SIZE | Groesse |  
| RO | Schreibgeschuetzt oder nicht|  
| TYPE | Typ z.B. disk fuer Festplatte|  
| MOUNTPOINTS | Punkt, wo das Geraet eingebunden ist|# General Informations  
## Why Debian?  
Easier to install and to configure, more user friendly
## Difference between Debian and Rocky  
- Debian easier to update that CentOS  
- Debian is more user-friendly + supports many libraries, filesystems and architectures
- Debian allows 32bit
- Debian is built on Ubuntu and focuses on stability
- Rocky is built on RHEL which means no frequent updates because RHEL is designed for a longer use without having to update
- Debian has more stable updates than rocky
- Debian will be maintained longer than Rocky (rocky until 2029)
- Debian supports more desktop systems like plasma ode gnome
## Virtual Machine?  
- Resource that uses software instead of physical computers to run programs or apps.  
- VMs have their own operating system and work separately  
- Can be used to test in a safe, separate environment  
- Works by using software to simulate virtual hardware and run on a host machine
## aptitude and APT(Advanced Packaging Tool)  

|aptitude|APT|  
|----|------|  
|high-level package manager|lower-level package manager|  
|"smarter" because it will remove unused packages or suggest installation of dependent packages|only does what u tipe in the cmd line|## AppArmor  

- Basically aptitude is the visual version of apt with extra features like also installing dependent packages and fixing errors themselves
- AppArmor is a security software that can give a program the rights that it needs and removes them if they don't need them anymore (if program behaves wrong app armor "blocks" the program)

App Armor is a security framework that protects the Linux system from potential security threats. It defines rules and restrictions for each application and ensures, that the program only got the permission they absolutely need. If it behaves not normal AppArmor steps in to block its unauthorized actions.
## Password Rules  
2 libs used (password quality checking lib and the `login.defs` which stores expiration rules) 

| Check | What does it do? |
|-------|------------------|
|retry=3 | max retry count is 3|
|minlen=6| minimal lenght of pass is 6 |
|ucredit=-1|maximum uppercase letters (-1 is infinite)|
|dcredit=-1|maximum number count (-1 is infinite)|
|maxrepeat=3| maximal repeat of small chars is 3?|
|reject_username|password cant include username|
|difok=7|number of char changes between old and new pass|
|enforce_for_root| the root user has to follow the pass rules |
## LVM  
Logical Volume Manager - to easily manipulate the partitions or the logical volume on a storage device
## UFW  
It's an interface to modify the firewall of the device without compromising security. Used to configure which Port is good to go and which isn't. Useful with ssh (-connection).
## SSH  
Authentication mechanism between client and host. Uses encryption techniques so that all messages from and to the host are unreadable for third party. Mac or Linux can use SSH in the terminal to work on their sever via SSH.
## Cron  
Cron is a command line utility to schedule commands or scripts to run at specific intervals. Useful if u wanna start your server at a specific time each day.  

| Cmd                                  | what it does              |
| ------------------------------------ | ------------------------- |
| sudo crontab -u root -e              | edit the cron job         |
| */10 * * * * sleep 10min && script path | run cron every 30 seconds |

## Hostname
- show hostname: `hostnamectl`
- edit hostname: `sudo nano /etc/hostname` and change the name

## User and Groups
- list all users: `cat /etc/passwd`
- list all groups: `sudo getent group`
- list groups of logged user: `grroups [<username>]` (username only when specific user)
# Commands  

| Command                               | What it does:                                                                       |                             |
| ------------------------------------- | ----------------------------------------------------------------------------------- | --------------------------- |
| cd /usr/local/bin                     | show monitoring.sh                                                                  |                             |
| sudo ufw status                       | status of firewall                                                                  |                             |
| sudo ufw status numbered              | shows the status and the ports with numbers in front to easier allow and deny ports |                             |
| sudo ufw allow port-id                | shows port id                                                                       |                             |
| sudo ufw delete rule number           | nummerierte Liste aller aktiven UFW Regeln                                          |                             |
| sudo ufw allow port-id                | erlaubt den Netzwerkverkehr auf dem angegebenen Port durch die Firewall             |                             |
| sudo systemctl status ssh             | status of ssh                                                                       |                             |
| ssh jkauker@127.0.0.1 -p 4242 / jkauker@localhost -p 4242         | in iTerm it shows that the Port is active and working                               |                             |
| getent group sudo                     | shows sudo group                                                                    |                             |
| getend group user42                   | shows user42 group                                                                  |                             |
| sudo adduser new_username             | adds new user with sudo permission                                                  |                             |
| sudo groupadd groupname               | adds new group                                                                      |                             |
| sudo chage -l username                | check password expire rules                                                         |                             |
| hostnamectl                           | shows name of the host                                                              |                             |
| hostnamectl set-hostname new_hostname | changes the current hostname                                                        |                             |
| sudo nano /etc/hosts                  | change current hostname to new hostname                                             |                             |
| dpkg -l                               | grep sudo                                                                           | show that sudo is installed |
| reboot                                | restart VM                                                                          |                             |                                      |                                                                                     |                             |