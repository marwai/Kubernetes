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

