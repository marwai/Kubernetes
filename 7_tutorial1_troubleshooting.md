# Basic troubleshooting techniques

## Chapter Goals
1. Kubernetes Techniques
2. Looking at Log files
3. Executing commands in a container

### Overview
Sometimes things don't work as they should in your deployments, and you'd like to take a closer look to debug issues or understand what's going on. There are 3 techniques I >

### Kubernetes Techniques
When things are not deploying as expected, or things seem to be taking a while, I describe the deployments and pods associated with the deployments to look for errors.

Let's run the helloworld application that is bundled with this section by typing `kubectl create -f helloworld-with-bad-pod.yaml`.

As it's starting up, we can run a `kubectl get deployments` and a `kubectl describe deployment bad-helloworld-deployment`.

We notice that we have 0 available pods in the deployment that signals that there is something going on with the pod.

If we introspect pods with a `kubectl get pods`, we see that the `bad-helloworld-deployment` pod is in an image pull backoff state and isn't ready.

Describing the pod with `kubectl describe pod bad-helloworld-deployment-7bb4b7466-f6nkm`, will show me that kubernetes is having trouble pull the pod from the repository, ei>

### Looking at log files
Another technique I end up using a lot to track pod progress is looking at the log files for a pod. If you write your logs to standard out, you can get to them by the comman>

### Executing commands in a container
Finally, sometimes it is necessary to exec into the actual container running the pod to look for errors, or state. To do this, run the exec command `kubectl exec -it <pod-na>

This drops us into the container, and we can introspect into the details of our application.


# 3 techniques 


1. Analyse deployment and pods

	```
	kubectl describe deployment bad-helloworld-deployment (works) 
	kubectl get pods
	kubectl describe po/bad-helloworld-deployment--66f646b9bb-ksmdm
	# look at events 
	```
2. log files

	```
	kubectl get deployments
	# copy deployment 
	kubectl logs deployment
	```

3. Exec into the shell script
 
	```
	# //bin/bash might be required 
	kubectl exec -it helloworld-all-deployment-66f646b9bb-ksmdm /bin/bash
	
	# multiple containers
	kubectl exec -it helloworld-all-deployment-66f646b9bb-ksmdm -c helloworld /bin/bash
	```
