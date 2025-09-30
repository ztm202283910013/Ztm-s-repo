# Kubernetes Questions & Answers

## 1. Orchestration Tools

### (a) How orchestration tools help manage and scale application servers

Orchestration tools like Kubernetes provide a declarative approach to infrastructure management:

- **Automated deployment** - Define desired state, the system maintains it
- **Service discovery** - Internal DNS for service-to-service communication
- **Load balancing** - Distributes traffic across healthy instances
- **Self-healing** - Automatically restarts failed containers
- **Horizontal scaling** - Adds/removes replicas based on metrics or manually
- **Rolling updates** - Minimizes downtime during application updates
- **Resource management** - Enforces CPU/memory limits and requests
- **Configuration management** - Centralized secrets and configuration

### (b) How orchestration tools facilitate automated operations

Kubernetes achieves automation through:

- **Controller patterns** - Deployment, StatefulSet, and DaemonSet controllers maintain desired state
- **Reconciliation loops** - Constantly compare actual vs. desired state and make corrections
- **Declarative APIs** - Define "what" you want, system handles "how" to achieve it
- **Self-healing capabilities** - Automatically replaces failed components
- **Autoscaling** - Horizontal Pod Autoscaler adjusts replicas based on CPU/memory or custom metrics
- **Rolling updates & rollbacks** - Controlled deployment with easy rollback capability

## 2. Pod, Deployment, and Service

- **Pod** - Smallest deployable unit in Kubernetes, containing one or more containers that share storage and network
- **Deployment** - Manages Pods and ReplicaSets, providing declarative updates and scaling for applications
- **Service** - Exposes Pods as a network service, providing stable network endpoint with load balancing

## 3. Namespace

A Namespace is a virtual cluster within a physical Kubernetes cluster that provides:

- Resource isolation between projects/teams
- Resource quotas and policy enforcement
- Simplified management in large clusters

**Example:** `kubectl create namespace production`

## 4. Kubelet Role & Node Checking

**Kubelet's role:**

- Runs on each node in the cluster
- Ensures containers are running in Pods as specified
- Communicates with the control plane
- Performs health checks on containers
- Reports node status to the API server

**Check nodes command:** `kubectl get nodes`

## 5. Service Types

- **ClusterIP** - Exposes service only within the cluster via internal IP
- **NodePort** - Exposes service on a static port on each node's IP
- **LoadBalancer** - Integrates with cloud provider load balancers for external access

## 6. Scale a Deployment to 5 Replicas

```plaintext
kubectl scale deployment <deployment-name> --replicas=5
```

## 7. Update Deployment Image Without Downtime

```plaintext
kubectl set image deployment/<deployment-name> <container-name>=<new-image:tag>
```

This triggers a rolling update, replacing Pods one at a time.

## 8. Expose Deployment to External Traffic

```plaintext
kubectl expose deployment <deployment-name> --type=NodePort --port=80 --target-port=8080
```

Or use LoadBalancer type in cloud environments:

```plaintext
kubectl expose deployment <deployment-name> --type=LoadBalancer --port=80 --target-port=8080
```

## 9. Kubernetes Scheduling

The Kubernetes scheduler decides Pod placement based on:

- **Resource requirements** - CPU/memory requests vs. node capacity
- **Node selectors and affinities** - Rules for Pod-node relationships
- **Taints and tolerations** - Node restrictions
- **Pod topology spread constraints** - Distributes Pods across failure domains
- **Quality of Service requirements** - Guaranteed, Burstable, or BestEffort
- **Pod priorities and preemption** - Handling resource scarcity

## 10. Ingress vs. Service

**Ingress role:**

- Manages external access to services
- Provides HTTP/HTTPS routing based on hostnames and paths
- Supports TLS termination and name-based virtual hosting
- Acts as a layer 7 load balancer

**Difference from Service:**

- Service provides layer 4 load balancing (TCP/UDP)
- Ingress provides layer 7 routing (HTTP/HTTPS)
- Service exposes Pods directly, Ingress manages external access to multiple services