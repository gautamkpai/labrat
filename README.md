# labrat
A disposable docker container with ssh server for quickly testing ansible scripts

### Usage
Build:
```
$ docker build -t labrat .
```
Run:
```
$ docker run -d -p 2222:22 labrat
```
ssh(use password: `password`):
```
$ ssh -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no ubuntu@localhost -p 2222
```
Ansible playbook:
```
# Add an entry to the inventory file
[labrat]
docker ansible_host=localhost ansible_port=2222

$ ansible-playbook -k -K -i /path/to/inventory playbook.yml
```
