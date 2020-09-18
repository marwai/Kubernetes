Kubernetes the hard way: https://github.com/kelseyhightower/kubernetes-the-hard-way

Hard to install k8s: https://groups.google.com/forum/#!topic/kubernetes-users/9ix65M13NNA

Kubeadm: http://blog.kubernetes.io/2016/09/how-we-made-kubernetes-easy-to-install.html

Kubernetes networks: https://kubernetes.io/docs/concepts/cluster-administration/networking/

Kops: https://github.com/kubernetes/kops

Get started with Kops: https://cloudacademy.com/blog/kubernetes-operations-with-kops/

Azure container service: https://docs.microsoft.com/en-us/azure/container-service/kubernetes/container-service-kubernetes-walkthrough

Oracle Container Engine: https://blogs.oracle.com/developers/announcing-oracle-container-engine-and-oracle-container-registry-service

# Instructions

1. Initially provision the master host with Docker and the K8 distrubution

2. Run Kubeadm init, which starts kubeadm, provisions the kubernetes control plane, and provides join token

3. Run Kubeadm join with join token on each worker node. The workers
 will join the clcuster 

# KOPS in AWS infrastructure
- automate k8 clustering in aws
- deploys HA masters
- permits upgrading with kube-up 
- use a state-sync model for dry runs and automatic idempotency
