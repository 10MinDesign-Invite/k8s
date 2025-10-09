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


<!-- helm -->

helm install postgres oci://registry-1.docker.io/bitnamicharts/postgresql

-------- to create own hem chart 

cd helm 
helm create .  // then default chart is generate

*** NOTE *** 
0-manifest.yml
Deployment.yml then
--- you apply then first get apply 0-manifest.yml then deploy 0- is order

helm install postgres-chart-1 .
-- then 0-namespace.yml run firset and all files apply leter automatic and if you change value.namespace: postgres-chart-2 then new namesapce is apply and all files is in new 2 namespace