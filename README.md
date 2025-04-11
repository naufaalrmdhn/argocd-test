# lagi belajar deploy argocd di kube 

## Apply manifest
```
kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
## Akses Argocd 
```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
## Password buat login
```
username: admin
password : dari secret
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
```
