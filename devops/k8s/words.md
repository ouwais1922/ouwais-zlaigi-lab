K8S:

kubectl is the command-line tool to interact with a Kubernetes cluster.

kubectl	K9s
Official tool	Third-party tool
Command-based	UI-based (terminal UI)
Scriptable	Not scriptable
Used in CI/CD	Used for debugging
Core requirement	Productivity tool


Rancher Desktop:
What Problem It Solves
Instead of manually installing:
* Docker
* Kubernetes (minikube/kind/kubeadm)
* container runtime
* kubectl
* networking setup
Rancher Desktop gives you everything ready in one app.


What is k3s?
k3s is a lightweight Kubernetes distribution.
It is:
* Fully Kubernetes compliant
* Smaller
* Easier to run
* Designed for low-resource environments

Why k3s Exists
Regular Kubernetes (k8s):
* Heavy
* Many components
* More RAM/CPU usage
* More operational complexity
k3s:
* Single lightweight binary
* Reduced memory footprint
* Simplified components
* Easier setup
