# Introducing

SonarQube provides the capability to not only show health of an application but also to highlight issues newly introduced. 
With a Quality Gate in place, you can Clean As You Code and therefore improve code quality systematically.

## Running SonarQube

```sh
docker-compose stop && docker-compose rm
docker-compose up -d
```
SonarQube is available [on the link http://localhost:9000 ](http://localhost:9000)

## Integration Spring Boot Application with SonarQube

[Read the instruction using maven plugins to integrate with SonarQube](./SB-INTEGRATION.md)

## Resolving issue "Elasticsearch: Max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]"

Insert the new entry into the /etc/sysctl.conf file with the required parameter:
```sh
vm.max_map_count = 262144
```
it makes changes permanent.

Also run:
```sh
sysctl -w vm.max_map_count=262144
```
change current state of kernel.

If you use docker to take effect you should restart it:
```sh
systemctl restart docker
```
