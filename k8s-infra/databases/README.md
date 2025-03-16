kubectl apply -f k8s-infra/databases/postgres-odoo/pvc.yaml
kubectl apply -f k8s-infra/databases/postgres-hotel/pvc.yaml
kubectl apply -f k8s-infra/databases/postgres-unsend/pvc.yaml


kubectl get pv
kubectl get pvc -A
