# hab-two-tier

This Habitat project illustrates a basic Apache web application (`webapp`) and HAProxy load balancer (`haproxy`).

The Docker Compose file brings up HAProxy and two load-balanced webapp instances.

## Build the packages

```
$ hab pkg build webapp
$ hab pkg export docker learn-chef/webapp
$ hab pkg build haproxy
$ hab pkg export docker learn-chef/haproxy
```

## Export to Docker

```
$ hab studio enter
$ cd webapp
$ build
$ hab pkg export docker learn-chef/webapp
$ cd ../haproxy
$ build
$ hab pkg export docker learn-chef/haproxy
```

## Run

```
$ docker-compose up -d
$ curl localhost:8000/cgi-bin/hello-world
$ docker-compose down
```
