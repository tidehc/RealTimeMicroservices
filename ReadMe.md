## Getting started

### Locally with docker & compose

Simply run docker-compose up from the source code root.

### With a Kubernetes cluster

**prerequisite:** 
k8s cluster with 
- an access to a registry
- ingress controller (or ignore the ingress and modify the services to expose them directly over LB or node port)

Run `BuildAndPush-Containers.ps1` and `Deploy-Application.ps1` (you need the URL of your registry as a mandatory parameter for the scripts)
To re-deploy, delete the k8s realtime-microservices namespace


## Side notes

Check redis: `kubectl run redis-cli-image -i --tty --rm --image redis -n realtime-microservices -- /bin/sh`
You can then run something like `redis-cli -h redis` and `SUBSCRIBE Notification-Channel`