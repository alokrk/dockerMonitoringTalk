# CSC 519 - DevOps TechTalks - Monitoring Docker Containers

## Developers

- Abhinav Ashish(abhina)
- Alok Kucheria(akucher)
- Jasleen Jabbal(jkjabbal)
- Sudhanshi Jain(sjain8)

## Comparative Study of Docker Monitoring Tools

## Why we need monitoring

As Cloud and DevOps become more prominent, we go for large scale deployments. In such scenarios, it is imperative that we would monitor the health of our resources. This can be done using various tools. For the purpose of this deliverable, we study three Docker monitoring tools:

- Docker Stats
- Docker Remote API
- cAdvisor

### Docker Stats

```
	docker stats
	```  display a live stream of the following container(s) resource usage statistics:

- CPU % usage
- Memory usage, limit, % usage
- Network i/o
- Disk i/o

By default, this command display statistics for all the running containers. A list of container names or ids can be specified, separated by a space, to restrict the stream to a subset of running containers. For example, stats for only the
Couchbase container can be seen as:

```
	docker stats couchbase
	```

where couchbase is the container name.

--no-stream option can be specified where only the first snapshot is displayed and results are not streamed. The Docker Logentries Container can be used to collect
this data.

## Docker Remote API

Docker daemon provides a Remote REST API. This API is used by the Client to communicate with the engine. This API can be also be invoked by by other tools, such as curl or Chrome Postman REST Client.

`curl https://localhost:2376/containers/42d1414883af/stats --cert $DOCKER_CERT_PATH/cert.p12 --pass mypass --key $DOCKER_CERT_PATH/key.pem --cacert $DOCKER_CERT_PATH/ca.pem`

Screenshot

## cAdvisor

cAdvisor or Container Advisor provide host and container metrics. It is a running daemon that collects, aggregates, processes, and exports information about running containers.

`docker run -d --name=cadvisor -p 8080:8080 --volume=/var/run:/var/run:rw --volume=/sys:/sys:ro --volume=/var/lib/docker/:/var/lib/docker:ro google/cadvisor:latest`

Screenshot
