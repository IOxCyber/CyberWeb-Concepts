Kubernetes:

Open Source platform to orchestrate/automate the placement (scheduling) and execution of application containers in clusters.

- Automates the distribution and scheduling of applications containers across a cluster.


Kubernetes Cluster Components:

It is consist of Control Plane, a set of worker machines i.e Node, Node Processes.

1. Control Plane (Coordinates the cluster)
- Responsible for managing the cluster, worker nodes and the Pods.
- Like Scheduling applications, maintaining application's state, scaling applications and rolling out new updates.

2. Nodes (Workers that runs applications)
- Simply a VM or Physical computer that serves as a worker machine in cluster.
- It has Kubelet, Kube-proxy and Pods (CRI i.e Container Runtime Environment)


Kubelet:
An Agent for managing the node and communicating with the kubernetes control plane via API.

etcd:
Highly available Key Value store used as Kubernetes backiystore for all cluster data.
- Required Back up required for the data.

kube-APIserver:
API server is a component of the kubernetes control plane.
Front end for the kubernetes control plane.





