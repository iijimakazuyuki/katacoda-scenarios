`helm repo add argo https://argoproj.github.io/argo-helm`{{execute}}

`helm repo update`{{execute}}

`helm install argocd argo/argo-cd`{{execute}}

`kubectl port-forward svc/argocd-server 443:443 --address 0.0.0.0 > /dev/null &`{{execute}}

`kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo`{{execute}}
