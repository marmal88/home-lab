# Setup ArgoCD for gitops for Kubernetes

## 1. Command to get started
- This will setup ArgoCD for Kubernetes 

```bash
# Deploying the argocd
kubectl apply -k .
```

```bash
# Username: admin
# Retrieve the password
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

```bash
# SSH forward to port 9994 from device
# Once completed you can access the argocd UI via localhost:9994
ssh -NfL 9994:192.168.50.202:443 <user>@<device-ip>
```
