# Application health checks

## Chapter Goal
1. Add HTTP health checks to the helloworld deployment
2. Simulate a failing deployment that fails a readiness probe
3. Simulate a failing deployment that fails a liveness probe

### 
1. Bad Liveness - circumstances is it appropriate to restart a pod
2. Bad Readiness - circumstance is it appropriate to take the pod out of the
list of service endpoints 

# Instructions
1. Create the pod 

	```
	kubectl create -f helloworld-with-bad-liveness-probe.yaml
	```

2. Look at the deployment 
	```
	kubectl get deployments

3. Look at the pod state

	```
	kubectl get pods
	```
	```
4. Look at individual events of pods 

	```	
	kubectl describe helloworld-with-bad-liveness-probe.yaml
	```
