## minikube-cluster
# Access the ArgoCD UI
``kubectl port-forward service/argocd-server -n argocd 8080:443``

# ArgoCD Credentials
Username: admin
Password: ``kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode ; echo``
