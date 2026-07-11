# TaskFlow Kubernetes Manifests

Kubernetes manifests for deploying TaskFlow to AWS EKS.
Managed by ArgoCD for GitOps continuous delivery.

## Structure

├── namespace.yaml
├── configmap.yaml
├── secrets.yaml (not committed — create manually)
├── ingress.yaml
├── api-gateway/
│   ├── deployment.yaml
│   └── service.yaml
├── user-service/
│   ├── deployment.yaml
│   └── service.yaml
├── task-service/
│   ├── deployment.yaml
│   └── service.yaml
├── notification-service/
│   ├── deployment.yaml
│   └── service.yaml
└── frontend/
├── deployment.yaml
└── service.yaml

## Deploy Manually

```bash
kubectl apply -f namespace.yaml
kubectl apply -f configmap.yaml
kubectl apply -f secrets.yaml
kubectl apply -f api-gateway/
kubectl apply -f user-service/
kubectl apply -f task-service/
kubectl apply -f notification-service/
kubectl apply -f frontend/
kubectl apply -f ingress.yaml
```

## GitOps with ArgoCD

ArgoCD watches this repository and automatically
syncs the cluster state when manifests change.

## Technologies

- Kubernetes
- AWS EKS
- ArgoCD (GitOps)
- AWS Load Balancer Controller