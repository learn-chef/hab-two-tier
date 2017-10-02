# Balance

This example habitat application that takes a simple web application (webapp) and a load balancer (haproxy). Two webapps are launched and then bound to the haproxy through the backend binding.

## Build

    $ hab pkg build webapp
    $ hab pkg export docker learnchef/webapp
    $ hab pkg build haproxy
    $ hab pkg export docker learnchef/haproxy

### Within the Studio

    $ hab studio enter
    $ cd webapp
    $ build
    $ hab pkg export docker learnchef/webapp
    $ cd ../haproxy
    $ build
    $ hab pkg export docker learnchef/haproxy

## Run

    $ docker-compose up

To verify that each web server is working:

    $ curl localhost:8000/cgi-bin/hello-world
    $ curl localhost:8001/cgi-bin/hello-world

To verify that the load balancer is working:

    $ curl localhost:8002/cgi-bin/hello-world
