# Ansible
## Installation of Ansible
- `sudo dnf update -y `
- `sudo dnf install epel-release -y`
- `sudo dnf install ansible -y`
- `ansible --version`

## Connection between Server(VM1) and Client(VM2)
The Below commands to be executed in Server(VM1)
- Here with command it will generate a public key
<br>`ssh-keygen -t rsa -b 2048`
- To view the content the public key
`cat ~/.ssh/id_rsa.pub`
- To copy the public key to authorized keys
`cat .ssh/id_rsa.pub > .ssh/authorized_keys`
- To view the content of authorized keys
`cat ~/.ssh/authorized_keys`
- To view the content of private key
`cat ~/.ssh/id_rsa`
- To see the ip address
`ip a`
- Here with the help of this command you can add ip addresses of VM1 & VM2 to the inventory file(hosts)
`sudo vi /etc/ansible/hosts`

The below commands to be executed in Client(VM2)
- To see the ip of Client(VM2) which will be added to the inventory file
`ip a`
- To view the authorized keys of Client (if the client vm is created through ssh key then in the authorized_keys there will be already a key generated from azure or if it is created from username and password then the authorized_keys will be blank)
`cat ~/.ssh/authorized_keys`
- If there is already a key generated from azure then don't delete it, add the public key of server(VM1) next to it
`vi ~/.ssh/authorized_keys`
- Then see the authorized_keys again using cat command
`cat ~/.ssh/authorized_keys`

## Ping
Ping is being done to see if the connection between 2 machines is being successfully established or not.

- You can use the 1st cmnd if you've provided the name along with the ip in inventory file, if you've only added the ip address then use the 2nd command

Pinging to the different VM(Server[VM1] -> Client[VM2])
`ansible vm02-client -m ping`
`ansible 10.0.0.5 -m ping`

Pinging to the same VM(Server[VM1] -> Server[VM1])<br>
`ansible vm01-main -m ping`<br>
`ansible 10.0.0.4 -m ping`