#### Commands to install and start Argo CD in a kubernetes cluster

```bash
# install ArgoCD in k8s

# create a namespace for argo CD
kubectl create namespace argocd

# install argo CD on the created namespace
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# check the pods created
kubectl get pods -n argocd

# check the services
kubectl get svc -n argocd

# Change the argocd-server service type to LoadBalancer
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

# Copy the dns name of Loadbalancer from argocd-server service
kubectl get svc -n argocd

# get the password to connect to the admin account
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

# you can change and delete init password

```

### Command to create an application on Argo-CD using  
</br>

#### Links to Official Documentation

* Install ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd](https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd)

* Login to ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli](https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli)

* ArgoCD Configuration: [https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/)
