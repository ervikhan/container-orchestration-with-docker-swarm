Docker Stack is useful for creating and running one or multiple containers at once using Docker Compose.

| Command | Description |
| --- | --- |
| docker stack deploy | Deploy a new stack or update an existing stack |
| docker stack ls | List stacks |
| docker stack ps | List the tasks in the stack |
| docker stack rm | Remove one or more stacks |
| docker stack services | List the services in the stack |
- Install stack with compose file

```yaml
version: "3.7"
services:
  apache-php81:
    ports:
      - 8081:80
    image: registry.dinus.ac.id/dnt-ubuntu-apache-php81:1.0
    deploy:
      replicas: 3
      placement:
        constraints: [node.role == worker]
    tty: true
```

```bash
docker stack deploy --compose-file swarm-test.yml --with-registry-auth apachephp8
```

```bash
*notes!
swarm-test.yml -> compose file name
apachephp8 -> stack name*
--with-registry-auth -> for registry that have authentication
```
More about private docker registry <a href="https://github.com/ervikhan/container-based-private-docker-registry">Visit here</a>