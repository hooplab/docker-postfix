docker-postfix
==============

run postfix with smtp authentication (sasldb) in a docker container.

## Requirements
Docker 1.0

## Installation
```bash
$ # replace assets/main.cf with actual config
$ sudo docker build -t hoopla/postfix .
```

## Usage
```bash
$ sudo docker run -d -p 25:25 --name postfix hoopla/postfix
```
## Testing (on ubuntu)
```
$ sudo docker run -d -p 25:25 --name postfix hoopla/postfix
$ sudo apt-get update
$ sudo apt-get install sendemail
$ sendemail -f postmaster@hoopla.no -t <recipent>@<host> -u <subject> -m <message> -s localhost:25
```