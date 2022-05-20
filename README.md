### Install Packages and Ansible Server

```bash
sudo apt-get update -y
sudo apt-get install python3
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10
sudo apt-get python3-pip
sudo apt-get install ansible
```

### Create new Role and Innvetory (Only one time)
```bash
mkdir -p roles inventory/{group_vars,host_vars} && touch inventory/hosts
cd roles
ansible-galaxy init role_name
# ansible-galaxy init jenkins 
```

### Run Playbook
```bash
ansible-playbook -i inventory/hosts playbooks/jenkins_workers.yaml  --tags debug
```