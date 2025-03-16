
```bash
kubectl create namespace argocd
```

kubectl create namespace databases-odoo
kubectl apply -f k8s-infra/databases/postgres-odoo/

kubectl create namespace odoo
kubectl apply -f k8s-infra/apps/odoo/


installation d'un ingress-nginx :
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
kubectl get pods -n ingress-nginx
kubectl get svc -n ingress-nginx
