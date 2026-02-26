🧠 1️⃣ Kubernetes Master Node (Control Plane)

This is the brain of the cluster.

It:

Makes decisions

Keeps track of everything

Tells worker nodes what to do

It does NOT run your apps.
It manages them.

🔹 2️⃣ API Server

The front door of Kubernetes.

Everything goes through it.

When you run:

kubectl apply -f app.yaml

It goes to the API Server.

It:

Receives requests

Validates them

Stores data

Talks to other components

👉 It is the central communication hub.

🔹 3️⃣ ETCD

The database of Kubernetes.

It stores:

Pods

Deployments

Services

Secrets

Cluster state

If etcd is lost → cluster state is lost.

👉 It remembers everything.

🔹 4️⃣ Controller Manager

The watcher.

It constantly checks:

“Does reality match what the user wants?”

Example:

You want 3 Pods

Only 2 are running

Controller creates 1 more.

👉 It keeps the system in the desired state.

🔹 5️⃣ Scheduler

The decision maker for placement.

When a new Pod is created:

It decides which worker node should run it.

Based on:

CPU

Memory

Constraints

👉 It assigns Pods to nodes.

💪 6️⃣ Slave Nodes (Worker Nodes)

These are the machines that run your applications.

They actually execute containers.

🔹 7️⃣ Kubelet

The agent on each worker node.

It:

Talks to API Server

Receives instructions

Starts/stops containers

If scheduler says:
“Run this Pod here”

Kubelet makes it happen.

👉 It executes orders.

🔹 8️⃣ Kube-proxy

The network manager on each node.

It:

Handles traffic

Makes sure Services route traffic to correct Pods

Enables Pod communication

👉 It manages networking rules.

📦 9️⃣ Pod

The smallest unit in Kubernetes.

It:

Runs one or more containers

Has its own IP

Lives on a worker node

You don’t manage containers directly.
You manage Pods.

👤 🔟 User Interface

How you interact with Kubernetes.

Options:

CLI

Dashboard

API

Most common → CLI.

🖥 1️⃣1️⃣ Kubectl

The command-line tool to talk to Kubernetes.

When you run:

kubectl get pods

kubectl:

Sends request to API Server

API Server processes it

Returns result

👉 Kubectl is just the client.

🔥 Full Simple Flow Example

You run:

kubectl apply -f app.yaml

Kubectl → API Server

API Server → saves data in etcd

Scheduler → chooses worker node

Kubelet → starts Pod

Controller → monitors it

Kube-proxy → handles traffic

🎯 Ultra Simple Summary
Component	Simple Meaning
Master Node	Brain
API Server	Front door
ETCD	Database
Controller	Keeps things correct
Scheduler	assign pod to a node
Worker Node	Runs apps
Kubelet	Executes instructions
Kube-proxy	Handles networking
Pod	Smallest deployable unit
pod is not a container - multiple containers
Kubectl	Command tool.