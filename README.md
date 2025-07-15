## minikube-cluster

# Create Docker Secret
``kubectl create secret docker-registry registry-credentials  \
  --docker-server "https://docker.io" \
  --docker-username angelvs \
  --docker-password="<password>" -n go-api``

# Access the ArgoCD UI
``kubectl port-forward service/argocd-server -n argocd 8080:443``

# ArgoCD Credentials
Username: admin
Password: ``kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode ; echo``

# Connect to PGAdmin4 for CNPG
``kubectl port-forward deployment/database-cluster-pgadmin4 8080:80 -n database``

# Port-forward for go-api API
``kubectl port-forward service/go-api-service 8080:8080 -n go-api``
