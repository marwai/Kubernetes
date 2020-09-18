# Namespaces
k8 Supports mltiple virtual clusters backed by the same physical 
cluster. These virtual clusters are called namespaces

### Uses cases
- Roles and responsibilities in an enterprise 
- Partitioning landscapes: dev vs. test vs. prod
- customer partitioning for non-multi tenant scenarios
	- consulting company with multiple customers
- Application partiioning 

### Enterprise roles and responsibilities 
Teams typically operate independantly but have some shared 
interfaces and APIs to communicate with each other.

Name space prevent teams and confusing services and deployments 
that might not belong to them 
	- plan how you want to manage enterprise in k8 environment
	  Setting standards up front will help with long-term infrastructure management
	- Don't Simply transpose exisitng on-premise controls and procedures onto the new env. 
	- DEV | TEST | PROD

### Caution
- Avoid large namepspaces - create addtional namespaces for groups of apps
- Avoid too many environments: don't abuse name spaces resulting in unnecessary environments

__Further Uses of Namespaces__
Customer partioning - create a namespace for each customer or project to keep them distinct

__Helmpackage manager__ 
delivered in own namespace which are comprised of deployment spaces , making it easy to encapsulate in single namespace

# Code

``` kubectl get namespaces```
``` kubectl create namespace```
``` kubectl delete namepsace```

__deploying specific namespace__
```-n namespace-name```
