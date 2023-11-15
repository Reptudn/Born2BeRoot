# Systemctl
- restart service: `sudo systemctl restart <service>`
- allow a service: `sudo systemctl allow <service>`
# SSH
## What is SSH?
- SSH => Secure Shell
- Protocol like HTTP / HTTPS / TCP / UDP
- secure low level transport protocol
- [Mail which explains SSH](https://datatracker.ietf.org/doc/draft-ietf-secsh-transport/24/)
### Debian
Config: `sudo vim /etc/ssh/sshd_config
Grab only the Port: `sudo grep Port /etc/ssh/sshd_config`
Restart Service: `sudo service ssh restart`
Check SSH Status: `sudo service sshd status`
### Mac
- Connect with `ssh jkauker@127.0.0.1 -p 4242`
- Exit with `exit`

# Firewall
- install: `apt-get install ufw`
- enable firewall with: `sudo ufw enable`
- check firewall status: `sudo ufw status numbered`
- allow SSH with `sudo ufw allow ssh` with the port 4242 with `sudo ufw allow 4242`

# Package Manager (apt)
- Install package: `apt-get <PACKAGE>`
# Password Policy
Install: `sudo apt-get install libpam-pwquality`
Edit: `sudo vim /etc/pam.d/common-password`
Change password for logged user: `passwd`
## Quality checks
[Wiki](https://manpages.debian.org/testing/libpam-pwquality/pam_pwquality.8.en.html)
To change the rules: `sudo nano /etc/pam.d/common-password`

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

# Users and Groups
## Groups
- Add user group: `sudo groupadd <groupname>`
- Check groups: `getent group ` / `getent group <group_name>`
- Add user to group: `sudo usermod -aG <group> <username>`
	- -`aG` because `-a` means to add someone to a group and without the `-G` that user would be only in the given group and removed from all the other groups the user might be in at the moment 
- Check groups which current user belongs to: `groups`
- [Wiki](https://wiki.ubuntuusers.de/usermod/)
## Users
- Check local users: `sudo -d: -f1 /etc/passwd`
- add User: `sudo adduser <username>`
- Check Password rules in user `chage -l <username>`
- delete user: `sudo deluser <username>`

# Sudo Log
go to `cd ~/../../` into the `var/log` folder where there is a `sudo` folder and inside there is a `sudo.log` file

| Type | What does it do? |
| ----- | ------------------ |
| badpass_message | Message that shows when pass is wrong |
|log_input| The input will be logged |
|log_output|the output will be logged|
|requiretty|forces sudo users to be logged in a text only terminal|

# Partitions
- list partitions with `lsblk`

