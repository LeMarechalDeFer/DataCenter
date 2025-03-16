kubectl apply -f k8s-infra/argocd/app-odoo.yaml

kubectl get pods -n odoo
kubectl get pods -n databases-odoo

kubectl port-forward svc/odoo -n odoo 8069:8069
