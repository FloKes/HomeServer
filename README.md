# Home Server Stuff
To get started, install, enable, and start ***openssh*** on the home server machine:
```
sudo apt update
sudo apt-get install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh

```


To run a playbook, example ***setup_jellyfin.yaml***, and ask for password for runnig commands as ***sudo***, which is used when you write ```become: yes```
```
ansible-playbook setup_jellyfin.yaml --ask-become-pass
```

The ansible playbooks on the control node should be located in : ```/etc/ansible/```, because of the ***src*** directory for copying the ***docker-compose.yaml*** file. 
When cloning, clone into this folder.

On the home server, if you use another username instead of ***floma*** , change the paths in the ***docker-compose.yaml*** file  
