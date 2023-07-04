#  Kustomize on Kubernetes

Kustomize is an open-source configuration management tool for Kubernetes.

It allows you to define and manage Kubernetes objects such as deployments, Daemonsets, services, configMaps, etc for multiple environments in a declarative manner without modifying the original YAML files

Which means we have a single source of truth for YAMLs, and you patch required configurations on top of the base YAMLs as per the environment requirements.

![image](https://github.com/Pavan-1997/K8s_Kustomize/assets/32020205/4d8ec4d4-3983-4dcf-85c2-382c45a700a2)

Kustomize has two key concepts, Base and Overlays. With Kustomize we can reuse the base files (common YAMLs) across all environments and overlay (patches) specifications for each of those environments.

Overlaying is the process of creating a customized version of the manifest file (base manifest + overlay manifest = customized manifest file).

All customization specifications are contained within a kustomization.yaml file.

---

Installing Kustomize 

```
wget https://github.com/kubernetes-sigs/kustomize/releases/download/kustomize%2Fv5.1.0/kustomize_v5.1.0_linux_amd64.tar.gz 	
```
Downloading the package 
```
tar zxf kustomize_v5.1.0_linux_amd64.tar.gz 	
```
Extracting the package
```
sudo mv kustomize /usr/local/bin
```
Moving the kustomize to the bin directory 
```
kustomize version 
```
To check the version of kustomize 
```
sudo apt install tree
```
To view directories

```
kustomize build <directory-name>
```
It generates manifests by processing the specified directory that contains a kustomization file and other resource files

```
kubectl apply -k <directory-name>
```
It applies the manifest files and creates deployments, services, and other resources 

```
kubectl delete -k <directory-name>
```
It deletes the manifest files and creates deployments, services, and other resources that were created 

---
Considering for Prod:

kustomize build overlays/
