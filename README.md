# Kubernetes Learning Playground

A beginner-friendly Kubernetes setup to learn the fundamentals of container orchestration.

## What is Kubernetes?

Kubernetes (K8s) is an open-source container orchestration platform that automates deploying, scaling, and managing containerized applications. Think of it as an operating system for your cluster of machines.

## Prerequisites

Before you begin, make sure you have one of these installed:

- **[minikube](https://minikube.sigs.k8s.io/docs/start/)** - Runs a local Kubernetes cluster (recommended for learning)
- **[Docker Desktop](https://www.docker.com/products/docker-desktop/)** - Includes Kubernetes support
- **[kind](https://kind.sigs.k8s.io/)** - Kubernetes IN Docker
- **kubectl** - Kubernetes command-line tool (usually included with above)

### Install minikube (macOS)

```bash
brew install minikube
minikube start
```

### Verify Installation

```bash
kubectl version --client
kubectl cluster-info
```

## Quick Start (TL;DR)

Get everything running in under a minute:

```bash
# 1. Start minikube (if not already running)
minikube start

# 2. Deploy all Kubernetes resources
kubectl apply -f k8s/

# 3. Wait for pods to be ready (~10-15 seconds)
kubectl wait --for=condition=ready pod -l app=nginx -n learning-k8s --timeout=60s

# 4. Access the application (this opens in your browser)
minikube service nginx-service -n learning-k8s
# Or just get the URL: minikube service nginx-service -n learning-k8s --url

# 5. Test it works (in a new terminal)
curl http://127.0.0.1:<port-from-step-4>
```

**Verify everything is running:**
```bash
kubectl get all -n learning-k8s
```

You should see:
- ✅ 3 nginx pods with status `Running` and `READY 1/1`
- ✅ 1 service `nginx-service` of type `NodePort` on port `80:30080/TCP`
- ✅ 1 deployment `nginx-app` with `READY 3/3`
- ✅ 1 replicaset managing the pods

**Expected output:**
```
NAME                             READY   STATUS    RESTARTS   AGE
pod/nginx-app-xxxxxxxxxx-xxxxx   1/1     Running   0          30s
pod/nginx-app-xxxxxxxxxx-xxxxx   1/1     Running   0          30s
pod/nginx-app-xxxxxxxxxx-xxxxx   1/1     Running   0          30s

NAME                    TYPE       CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
service/nginx-service   NodePort   10.100.x.x      <none>        80:30080/TCP   30s

NAME                        READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx-app   3/3     3            3           30s

NAME                                   DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-app-xxxxxxxxxx   3         3         3       30s
```

## Project Structure

```
k8s/
├── namespace.yaml    # Isolates resources in a virtual cluster
├── configmap.yaml    # Stores configuration data
├── deployment.yaml   # Manages pod replicas and updates
└── service.yaml      # Exposes pods as a network service
```

## Understanding the Components

### 1. Namespace ([k8s/namespace.yaml](k8s/namespace.yaml))
- Creates a logical boundary for resources
- Useful for organizing different environments (dev, staging, prod)

### 2. ConfigMap ([k8s/configmap.yaml](k8s/configmap.yaml))
- Stores non-sensitive configuration data
- Can be injected as environment variables or mounted as files
- Separates configuration from application code

### 3. Deployment ([k8s/deployment.yaml](k8s/deployment.yaml))
- Manages a set of identical pods
- Ensures desired number of replicas are running
- Handles rolling updates and rollbacks
- Includes health checks (liveness and readiness probes)

### 4. Service ([k8s/service.yaml](k8s/service.yaml))
- Provides a stable network endpoint
- Load balances traffic across pods
- Makes your application accessible

## Getting Started

### Step 1: Apply the Kubernetes Manifests

```bash
# Create the namespace first
kubectl apply -f k8s/namespace.yaml

# Create the ConfigMap (referenced by the Deployment)
kubectl apply -f k8s/configmap.yaml

# Create the Deployment (creates the pods)
kubectl apply -f k8s/deployment.yaml

# Create the Service (exposes the pods)
kubectl apply -f k8s/service.yaml
```

Or apply everything at once:

```bash
kubectl apply -f k8s/
```

### Step 2: Verify Everything is Running

```bash
# Check the namespace
kubectl get namespaces

# View all resources in our namespace
kubectl get all -n learning-k8s

# Check pod status
kubectl get pods -n learning-k8s

# Check service details
kubectl get service -n learning-k8s
```

### Step 3: Access Your Application

If using **minikube**:

```bash
# Get the service URL
minikube service nginx-service -n learning-k8s

# Or get the URL without opening browser
minikube service nginx-service -n learning-k8s --url
```

If using **Docker Desktop** or **kind**:

```bash
# Access via localhost:30080
curl http://localhost:30080
```

## Useful kubectl Commands

### Viewing Resources

```bash
# Get all pods in the namespace
kubectl get pods -n learning-k8s

# Get detailed info about a pod
kubectl describe pod <pod-name> -n learning-k8s

# View pod logs
kubectl logs <pod-name> -n learning-k8s

# Follow logs in real-time
kubectl logs -f <pod-name> -n learning-k8s

# Get deployment status
kubectl get deployments -n learning-k8s

# View ConfigMap data
kubectl get configmap app-config -n learning-k8s -o yaml
```

### Interacting with Pods

```bash
# Execute a command in a pod
kubectl exec -it <pod-name> -n learning-k8s -- /bin/sh

# Port forward to access a pod directly
kubectl port-forward <pod-name> 8080:80 -n learning-k8s
```

### Scaling

```bash
# Scale deployment to 5 replicas
kubectl scale deployment nginx-app --replicas=5 -n learning-k8s

# Watch pods being created/destroyed
kubectl get pods -n learning-k8s -w
```

### Updating

```bash
# Update image version
kubectl set image deployment/nginx-app nginx=nginx:1.26-alpine -n learning-k8s

# Check rollout status
kubectl rollout status deployment/nginx-app -n learning-k8s

# View rollout history
kubectl rollout history deployment/nginx-app -n learning-k8s

# Rollback to previous version
kubectl rollout undo deployment/nginx-app -n learning-k8s
```

### Debugging

```bash
# Describe a resource for detailed info
kubectl describe deployment nginx-app -n learning-k8s

# Get events in the namespace
kubectl get events -n learning-k8s --sort-by='.lastTimestamp'

# Check resource usage
kubectl top pods -n learning-k8s
kubectl top nodes
```

## Clean Up

Remove all resources:

```bash
# Delete everything in the namespace
kubectl delete namespace learning-k8s
```

Or delete individual resources:

```bash
kubectl delete -f k8s/service.yaml
kubectl delete -f k8s/deployment.yaml
kubectl delete -f k8s/configmap.yaml
kubectl delete -f k8s/namespace.yaml
```

## Next Steps

Once you're comfortable with the basics, explore:

1. **Persistent Volumes** - Store data that survives pod restarts
2. **Secrets** - Store sensitive data like passwords and API keys
3. **Ingress** - Advanced HTTP routing and load balancing
4. **StatefulSets** - For stateful applications (databases, etc.)
5. **Jobs and CronJobs** - Run batch processes and scheduled tasks
6. **Helm** - Package manager for Kubernetes
7. **Custom Resource Definitions (CRDs)** - Extend Kubernetes API

## Resources

- [Kubernetes Official Documentation](https://kubernetes.io/docs/)
- [Kubernetes Basics Tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Play with Kubernetes](https://labs.play-with-k8s.com/) - Free browser-based playground

## Troubleshooting

**Pods not starting?**
```bash
kubectl describe pod <pod-name> -n learning-k8s
kubectl logs <pod-name> -n learning-k8s
```

**Can't access the service?**
```bash
# Verify service is running
kubectl get svc -n learning-k8s

# Check endpoints
kubectl get endpoints -n learning-k8s
```

**Image pull errors?**
- Check your internet connection
- Verify the image name and tag are correct
- Some environments may need image pull secrets for private registries