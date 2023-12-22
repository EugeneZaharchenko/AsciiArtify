# ArgoCD manual

## 1. Install

```text
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Check

```text
kubectl get all -n argocd
```

### Port Forwarding

```text
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

### Get password for GUI

```text
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
