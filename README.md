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
ansible-playbook mount_drives.yaml --ask-become-pass
```

The ansible playbooks on the control node should be located in : ```/etc/ansible/```, because it is the default setting for for ***ansible hosts and cfg*** and because of the ***src*** directory for copying the ***docker-compose.yaml*** file. 
When cloning, clone into this folder. If the folder doesn't exist, create it in ```/etc/```. After cloning, run ```sudo mv HomeServer/* ./```.

On the home server, if you use another username instead of ***floma*** , change the paths in the ***docker-compose.yaml*** file  


##In case of new hard drives
You can find the ***UUIDs*** of the hard drives by running ```sudo blkid```, and writing the ***UUIDs*** to the ***mount_drives.yaml*** playbook