### Install Packages and Ansible Server

```bash
sudo apt-get update -y
sudo apt-get install python3
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3 10
sudo apt-get python3-pip
sudo apt-get install ansible
mkdir -p roles inventory/{groups_vars,host_vars} && touch inventory/hosts
cd roles
ansible-galaxy init jenkins
```

### Run the Playbooks

1. Install the Jenkins Server
```bash
ansible-playbook -i inventory/hosts jenkins.yaml
```

2. Install the Jenkins Worker
```bash
ansible-playbook -i inventory/hosts playbooks/jenkins_workers.yaml
```

3. Run the task with specific tags only
```bash
ansible-playbook -i inventory/hosts playbooks/jenkins_workers.yaml  --tags debug
```