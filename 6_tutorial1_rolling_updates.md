# Handling application upgrades

## Chapter Goals
1. Upgrade a deployment from 1 version to another
2. Rollback the deployment to the 1st version

### Upgrade a deployment from 1 version to another

Let's deploy our initial version of our application `kubectl create -f helloworld-black.yaml --record`. After the deployment and service has completed, let's expose this via a nodeport by `minikube>

Looking at the deployment, we see that there are 3 desired, current and ready replicas.

As developers, we're required to make changes to our applications and get these deployed. The rollout functionality of Kubernetes assists with upgrades because it allows us to upgrade the code with>

To update the image, I run this command: `kubectl set image deployment/navbar-deployment helloworld=karthequian/helloworld:blue`. This sets the image from what it is currently (karthequian/hellowor>

The deployment will update, and if you look at the webpage, you'll see the updated text.

Let's take a look at what happened here. When the deployment was edited, a new result set was created for it. Running the `kubectl get rs` command shows us this. One result set with 3 desired, curr>

We can also take a look at the rollout history by typing `kubectl rollout history deployment/navbar-deployment`.

### Rollback the deployment to the 1st version
To rollback the deployment, we use the rollout undo command `kubectl rollout undo deployment/navbar-deployment`. This will revert our changes back to the previous version.

Our webpage will be back to the Lionel version of the deployment.

In a real world setting, you might have a longer history, and might want to rollback to a specific version. To do this, add a `--to-revision=version` to the specific version you want to.



# Instructions

1. Create first pod 

	```
	 kubectl create -f helloworld-black.yaml  --record

	```

2. Look at the browser version 

	``` 
	 minikube service navbar-service
	```

3. Change colour of navbar

	```
	kubectl set image deployment/navbar-deployment helloworld=karthequian/helloworld:blue
	```

4. Look at deployment history 

	```
	kubectl rollout history deployment/navbar-deployment
	```

5. Rollback to revision number

	```
	 kubectl rollout undo deployment/navbar-deployment --to-revision=1
	```
