k8s fundamentals:

definition: running containers at scale

the sytem can scale based on the cpu usage

## The Problem Before Kubernetes
Imagine This (2014 era)

You built a web app:

Backend (Node.js)

Frontend

PostgreSQL

Redis

You package everything in Docker containers.

So far, so good 

## Now Traffic Increases

You need:

5 backend containers

3 frontend containers

You manually run:

docker run ...
docker run ...
docker run ...

Already painful.

## Then One Container Crashes

What happens?

Nothing.

It stays down.

You must:

Detect it

SSH into server

Restart it manually
 No self-healing

## Then You Need Multiple Servers

Now traffic grows more.

You have:

Server A

Server B

Server C

Questions:

On which server should a new container run?

How do containers talk across servers?

How do you load balance traffic?

What if a server dies?

How do you scale automatically?

Now you're in orchestration hell.

The Core Problem

Docker solved:

"How to package and run a container"

But NOT:

How to manage hundreds of containers

How to distribute them across machines

How to scale automatically

How to recover from failures

How to do rolling updates without downtime

That’s where Kubernetes came in.

 What Kubernetes Solved

Let’s revisit the same example.

Instead of running containers manually, you write:

replicas: 5

Kubernetes ensures:

5 backend containers are always running

If one crashes → automatically restart

If a node dies → reschedule elsewhere

Traffic is load balanced

You can scale with one command:

kubectl scale deployment backend --replicas=10


| Feature                     | ReplicaSet                       | Deployment                   |
| --------------------------- | -------------------------------- | ---------------------------- |
| Purpose                     | Maintains a fixed number of Pods | Manages ReplicaSets and Pods |
| Manages Pods                | ✅ Yes                            | ✅ Yes (indirectly)           |
| Ensures replicas            | ✅ Yes                            | ✅ Yes                        |
| Self-healing                | ✅ Yes (recreates Pods)           | ✅ Yes                        |
| Rolling updates             | ❌ No                             | ✅ Yes                        |
| Rollbacks                   | ❌ No                             | ✅ Yes                        |
| Version management          | ❌ No                             | ✅ Yes                        |
| Creates ReplicaSet          | ❌ No                             | ✅ Yes                        |
| Used directly in production | Rarely                           | Very common                  |
| Recommended for apps        | ❌ Not directly                   | ✅ Yes                        |

deployment:

A Deployment is a Kubernetes object that manages and maintains a desired number of identical Pods, while providing features like scaling, rolling updates, and rollbacks.

replicaset:

A ReplicaSet is a Kubernetes object that ensures a specified number of identical Pods are running at all times.