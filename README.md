# Ansible
## Installation of Ansible
- `sudo dnf update -y `
- `sudo dnf install epel-release -y`
- `sudo dnf install ansible -y`
- `ansible --version`

## Connection from Server(VM1) to Client(VM2)
- `ssh-keygen -t rsa -b 2048`
- `cat ~/.ssh/authorized_keys`
- `cat ~/.ssh/id_rsa.pub`
- `sudo vi /etc/ansible/hosts`