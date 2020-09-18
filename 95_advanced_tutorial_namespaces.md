# Namespaces
k8 Supports mltiple virtual clusters backed by the same physical 
cluster. These virtual clusters are called namespaces

### Uses cases
- Roles and responsibilities in an enterprise 
- Partitioning landscapes: dev vs. test vs. prod
- customer partitioning for non-multi tenant scenarios
	- consulting company with multiple customers
- Application partiioning 

# Enterprise roles and responsibilities 
Teams typically operate independantly but have some shared 
interfaces and APIs to communicate with each other.

Name space prevent teams and confusing services and deployments 
that might not belong to them 
