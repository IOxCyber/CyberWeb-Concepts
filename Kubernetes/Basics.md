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
Use to manage traffic.
Front end for the kubernetes control plane.

kube-Scheduler:
- Control plane component that keep track of newly created Pods with unassigned nodes.
- Use to select a node for New Unassigned Pods.

kube controller manager:
Control Plane components that runs controller processes.

Types of Controllers:
Node Controller: Monitors & respond if nodes goes down.
Job Controller: Monitors the one off tasks & create Pods to run those tasks to completion.
EndpointSlice, Service Account Controller etc

kube-proxy:
Network Proxy that runs on each Node in your cluster.
Maintains network rules on nodes like allow communication, filtering traffic, forwarding etc.

Container Runtime:
A component to run, manage, execution and lifecycle of containers within the kubernetes environment.




