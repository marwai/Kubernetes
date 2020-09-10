1) Windows 10 Enterprise or Pro Edition is required

2) Download Docker
	```
	docker version
	```
3) Download Kubectl

	```
	# Edit path variable of kubectl in path variables and elevate that 
	# it is before docker specific 
	
	kubectl version --client 
	# check it is installed
	```

4) Install minikube

	```
	# Ensure hyperv is installed
	systeminfo
	
	# IF IS IT YOUR FIRST TIME RUN THIS TO ACTIVATE HYPER ON WINDOWS
	Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
	
	# minikube-windows-amd64 installer
	Go to hyper-v manager > virtual switch manager > Interal > "minikube" > okay

	# network and sharing 
	properties > allow other networks users to connect through this computers internet connection > "minikube"
	```
5) minikube start --vm-driver="hyperv" --hyperv-virtual-switch="minikube"

6) Navigate into the folder  
	```
	cd C:\Users\marcu\projects\Ex_Files_Learning_Kubernetes_Upd\Exercise Files\03_04
	

	# Enter - kubectl gets the status of the running clusters 
	kubectl get all 
	
	# Deploy application - create resource -f (file) 
        kubectl create -f .\helloworld.yaml 
	kubectl get all

	# Access the webpage by creating service construct. Do this by exposing the name as type of NodePort 
	kubectl expose deployment helloworld --type=NodePort
	kubectl get all

	# Run application which references the helloworld container
	minikube service helloworld 
	```

7) Let's look at deployment 

	```
	# first deployment - deploy two artefacts  
	kubectl get deployment
	kubectl get delpoyment helloworld -o yaml
	kubectl get service
	kubectl get service helloworld -o yaml
	
	# second 
	kubectl 
	```
