# Grafana


# Setup

```bash
# Retrieve initial password
kubectl get secret grafana -n monitoring -o jsonpath="{.data.admin-password}" | base64 -d
```
