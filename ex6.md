# ✅ Experiment 6 – Kubernetes Commands

## Aim
To create, scale, expose deployment.

## Where to Do It
Use **Terminal with Kubernetes / Minikube**

## Commands

```bash
kubectl create deployment myapp --image=nginx
kubectl get deployments
kubectl get pods
kubectl scale deployment myapp --replicas=3
kubectl expose deployment myapp --port=80 --type=NodePort
kubectl get services
kubectl delete service myapp
kubectl delete deployment myapp
```

## Expected Output

Deployment and pods created successfully.
