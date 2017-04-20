# CSC 519 - DevOps TechTalks - Monitoring Docker Containers

## Developers

- Abhinav Ashish(abhina)
- Alok Kucheria(akucher)
- Jasleen Jabbal(jkjabbal)
- Sudhanshi Jain(sjain8)

## Comparative Study of Docker Monitoring Tools

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

### Docker Remote API

### cAdvisor
