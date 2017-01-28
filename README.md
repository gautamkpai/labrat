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
ssh -o UserKnownHostsFile=/dev/null -o StrictHostKeyChecking=no ubuntu@localhost -p 2222
```
