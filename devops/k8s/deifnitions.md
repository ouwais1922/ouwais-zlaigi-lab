Pod
The smallest unit in Kubernetes that runs one or more containers on a worker node.

Deployment
A Kubernetes object that manages Pods and ensures the desired number of replicas run, while supporting scaling and rolling updates.

ReplicaSet
A Kubernetes object that ensures a specified number of identical Pods are always running.


A Namespace 
is a logical separation inside a Kubernetes cluster.
It allows you to divide one cluster into multiple isolated environments.
ideally each application should have it own namespace