
```bash
kubectl create namespace argocd
```

kubectl create namespace databases-odoo
kubectl apply -f k8s-infra/databases/postgres-odoo/

kubectl create namespace odoo
kubectl apply -f k8s-infra/apps/odoo/
