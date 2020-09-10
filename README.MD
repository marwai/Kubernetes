# 1) Kubernetes - K8

__What is Containerisation?__
Containers - collection of software processes unified by one namespace with access to an operating system kernel that is shares with other containers and little to no access between containers 

__Docker Instance? __
Run instance of docker image contains three things:
	1.  A docker Image
	2. An execution environment
	3. A standard set of instructions 

Classes and objects - OOP analogy - container is an object, class is  a docker image 



Docker Engine - c

## Difference between VM and container? 
	- VM
		○ One or many applications 
		○ Necessary binaries and libraries that exist on OS
		○ Entire guest OS to interact with the applications
	- Container
		○ Application and all the dependencies 
		○ Share the kernel with other containers 
		○ Not tied to infrastructure - only needs docker engine on the host 
		○ Run isolated processes in user space on the OS
## Container Benefits for Dev
	1. Portable - 
	2. Packaged in standard way 
### Deployment 
	1. Easy
	2. Repeatable 

## Benefits for Developers
	• Automated Testing, packaging and integration 
	• Support newer microservice architectures 
	• Alleviate platform compatibility 

### Benefits for DevOps
	• Reliable deployments improve speed and frequency of releases 
	• Consistent application lifecycle configure once and run multiple times
	• Container environments - No more process differences between development and production environment 
	• Simple Scaling - Fast deployment ease the addition of workers and permit workload to grow and shrink for on-demand use cases 
	• Containers create a container language 

DevOps team can isolate and debug issues at the container level, limiting problems relating to differences in host or run time issues

### Containers and Microservices
	• Bring agility to the code
	• Help build a CI and deployment pipeline
	• Push an IT team to develop, test and deploy apps faster
	• Reason why enterprises have started to adopt containers in a big way

________
# Docker
Answer median number of containers running a single host is 10. All these containers have to be managed in someway across the whole infrastructure.
	- Container Orchestration is required
	- Orchestrator feature 
		○ provision hosts
		○ instantiate container on a  host 
		○ restart failing containers 
		○ expose containers as a service outside the cluster
		○ scaling the container up or down
		

Kubernetes - How  to manage all containers running on single host, across whole infrastructure? 

```
# K8 
# an open source platform designed to automate, deploying, scaling and operation  
# application containers 
# K8 runs containers on clusters of virtual machines. It runs on bare metal, vm, private 
# datacentre and public cloud.
# Use Docker containers to develop and build applications, then K8 to run these applications # on your infrastructure
```

### K8 Features 
	```
	K8 is an open source project that enables software teams of all sizes, from a small start-up to a Fortune 100 company, to automate deploying, scaling and managing applications on a group or cluster of server machines. These applications can include everything form a internal-facing web application like a content management system to marque web properties like Gmail to big data processing 
	```

 __Multi-Host Container Scheduling __
	- Done by kube-scheduler 
	- Assign pods to nodes at runtime 
	- Check resources, quality of service, policies, and user specifications before scheduling
__Scalability and availability __
	- K8 can be deployed in a highly available configuration 
	- Multi region deployment 
		○ __Scalability__ - Supports 5000 node clusters
		○ 150,000 total pods
		○ Max of 100 pods per node
		○ Pods can be horizontally scaled via API
		○ __ Two feature for scaling are registration and discovery - seamless nodes registers themselves with Master
__Flexibility and Modularisation__
	- Plug and play architecture 
	- Extend architecture when needed 
	- Add-ons: network drivers, service discovery, container run-time, visualisation and command 
		○ __Service Discovery__ - Automation detection of services and endpoints via DNS or environment variables 
__Persistent storage__ 
	- Pods can use persistent volumes to store data
	- Data retained across pod restarts and crashes

__Application upgrades and downgrades
	- Supported to upgrades and rollbacks

__Maintenance__
	- Features are backward compatible 
	- APIs are versioned
	- Turn off/on host during maintenance 
	
__ Logging and Monitoring__
	- Application monitoring built-in 
	- TCP, HTTP or container execution health cplheck 
	- Node health check
___

# Container Orchestration 

_____

# K8 test 

	1) Kubernetes gives you a platform to schedule and run containers on clusters of your machines.
	2) What is the CNCF? Cloud Native Computing Foundation 
	3) Two features that allow Kubernetes Clusters to scale are registration and discovery 
	4) How would you best describe K8?
	an open-source platform designed to automate deploying, scaling, and operating application containers
	5) Why organisations use containers? 
	To build applications to incorporate a microservices-based architecture
	
______
	
# 2) K8 Overview 


	- Master Node

### Master Node - responsible for overall management of K8 cluster
	- API Server - interacts with K8 API - front end of K8 control plane
	- Scheduler - watches created pods, who do not have a node design yet, tells pods to run on specific node
	- Controller Manager - Runs controllers that runs tasks in a cluster. Includes various roles that are compiled within a single binary
		○ Node controller - worker states
		○ Replication controller - no of pods 
		○ End-point controller - joins services and pods together
		○ Service account and 
### etcd
Distrubuted key value stored - uses as database and store all clusters there. 

### Kubetctl application
	- Interacts with Master node - command line interface for K8
	- Has file called Kubeconfig that contains  info and authentication to access server

### Worker Node 
	- Communicates with the worker nodes where applications operate
	- Communicate with master node
	- Communicate handled by Kublet process. It's an agent that communicates with the API  server to see if the pods are designed to the nodes. It exectues pod containers via the container engine . Mountains and runs pod volume and secrets. And finally, aware of pod or node states ad responds back to the master

# Kube proxy
	- Network proxy and load balancer on single worker node. Handles TCP and UDP packets and performs connection forwarding 
	- Docker daemon can run containers of an application that are coupled within a pod
		○ Pod is the smallest can that can scheduled as a deployment in K8
		○ These containers share storage, Linux name space, IP addresses amongst other things

# next
	- Kublet process communicate with pods to check health 
	- Worker nodes can be exposed to internet via __load balancers__
	
______

# Basic Building Blocks: 
# Nodes and Pods

### K8 Cluster 


Same architecture but from cluster perspective 
```
Master is responsible for managing cluster and coordinates activity
# The node serves as a worker machine in a k8 cluster. One important thing to note is that the node can be a physical computer or a virtual machine 

# Node Requirements
	1. Kubelet running 
	2. Container tooling like Docker
	3. A kube-proxy process running 
	4. Supervisord to restart components 
	
# Recommendation 
# Using k8 in production, recommended to at least three cluster nodes
```
### Minikube
```
Lightweight k8 implementation that creates a VM on your local machine and deploys simple cluster containing only one node
```




# Pods 
```
K8 model, a pod is a simple unit that you can interact with. Create, deploy, delete pods, and it represents one running process on your cluster 
```
__Pod contains__
	- Docker application container 
	- Storage resources 
	- Unique network IP 
	- Options that govern how the container(s) should run 
	```
           # Ephemeral, disposable entities
	# Never self heal, not restarted by scheduler 
	# Never create pods by themselves
	# Always use higher-level constructs, use controllers instead 
	```
	- Has three states:
		○ Pending - accepted by k8 system but container has not been created
		○ Running - pod has been scheduled on node and all container has been created, and at least one container is  in running state
		○ Succeeded  - all containers in the pod have exited with exit status of zero
		○ Failed - all containers in the pod exited and at least one container has failed with a non-zero exited status
		○ CrashLoopBackOff - failed for a reason 
		
	
	__________
	
	# Deployments, ReplicaSets and Services
	
	## Benefits of  Controllers 
	- Application reliability - multiple instances prevent problems if one or more instances fail
	- Scaling - pods experiences high volume of requests, k8 scales up pods
	- Load balancing - traffic to flow to different pods 

# Types of Controllers 
	- ReplicaSets
	- Deployments
	- DaemonSets
	- Jobs 
	- Services
	
__ReplicaSets__
	```
	Ensures that a specified number of replicas for a pod are running at all times.
	If pod is less than the number expected (pod crashes), replicaSets create a new onw 
	```
__Deployment Controller__ 
	- Can't declare replicaSet with itself, so deployment occurs with it. 
	```
	- Provides declarative updates for pods and ReplicaSets
		Use cases:
		○ Management : running ReplicaSets allows deployment to number of pods, and check status as a single unit
		○ Scaling a ReplicaSets scales out the pods, and allows for deployment to handle more traffic 
	- Pause and Resume:
		○ Used with larger changesets
		○ Pause Deployment, make changes, resume deployment 
	- Status:
		○ Easy way to health check
	
		```
__DaemonSets__
	```
	# Ensure node run a copy of a specific pod
	# As nodes added or removed from a cluster, DaemonSet will add or remove the required pods
	```
	
__Jobs__ 
	```
	# Supervisor process for pods carrying out batch jobs 
	# Run individual processes that run once and complete successfully 
	```
__Services__
	``` 
	# Allows the communication between one set of deployments with another 
	# To get pods in two deployments to communicate with one another 
	```
	- Types of Services:
		○ Internal -  IP is only reachable within the cluster
		○ External  - Endpoint available through node IP: port(called NodePort)
		
	
# Labels, Selectors, and Namespaces
__Labels__ 
	```
	Labels are key/values pairs that are attached to objects like pods, services, and deployments. Labels are for users of K8 to identify attributes for objects 
	
	"release": "stable", "release" : "canary"
	"environment" : "dev", "environment" : "QA", "environment" : "production"
	```

	
__Selectors__
Allows you to indentify a set of objects with label
	- Equality-based
		○ Equality-based - include the equals and not equals (= / !=)
	- Set-based
		○ IN: A value should be inside a set of define values
		○ NOTIN: A value should not be inside a set of defined values
		○ EXISTS: Label exists or not 

__Namespaces__
	````
	# Great for large enterprises
	# Allows teams to access resources, with accountability 
	# Great way to divide cluster resources between users
	# Provide scope for names-must be unique in the namespace
	```
	- Default namespace created when you launch Kubernete

___

# Kubelet and Kube Proxy

```
# Kubelet is the Kubernetes node agent  that runs on each node
# Works in terms of Pod spec (.yml) 
# Kubelet takes a set of Pod specs that are provided by the kube-APIServer and ensures that the containers 
# described in those Pod specs are running and healthy 
# Kubelet only manages containers that were created by the API server - not any container running on the node 
```

	- Communicates with API server to see if pods have been assigned to nodes
	- Execute pod containers via a container engine 
	- Mounts and runs pod volumes and secrets
	- Executes health checks to identify pod/node status 

## Kube-proxy: The Network Proxy 
	- Process that runs on all worker nodes
	- Reflects services as define on each node, and can do simple network stream or round-robin forwarding across a set of backends 
	
Kube-proxy
	1. User-space mode
	2. Iptables mode
	3. Ipvs Modesl
		○ Services are define against the API server: Kube-proxy watches the API server for the addition of removal of services
		○ Kube-proxy opens a random port on each local node 
