eksctl create cluster --name sanket-cluster --region ap-south-1 --node-type t3.small --nodes 2 --nodes-min 1 --nodes-max 2

ingress installation in clustor-controll-manager inside cluster

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.12.1/deploy/static/provider/cloud/deploy.yaml

<!-- argocd -->

kubectl create namespace argocd

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

--------port forwart for gui---------

kubectl port-forward svc/argocd-server -n argocd 8080:443

----- getting username and passwords-

kubectl -n argocd get secret argocd-initial-admin-secret
kubectl -n argocd get secret argocd-initial-admin-secret -o json