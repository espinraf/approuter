# APP  ROUTER

This  is a router to  direct HTTP traffic to applications in Docker containers using Nginx and Consul as discovery service

## How to run

```

docker build --rm -t redpill/approuter-data  .

docker-compose up

```

## Register a service

```
http://localhost:8500/v1/agent/service/register

header: Content-Type :  application/json

{
  "ID": "api",
  "Name": "api",
  "Tags": [
    "primary",
    "v1"
  ],
  "Address": "172.20.0.3",
  "Port": 8081,
  "Meta": {
    "mule_version": "3.0"
  },
  "EnableTagOverride": false
}

```
