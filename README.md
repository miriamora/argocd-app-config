#### Commands

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

# Launch argo CD UI at https://127.0.0.1:8080/
kubectl port-forward svc/argocd-server -n argocd 8080:443

# get the password to connect to the admin account
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

# you can change and delete init password

```
</br>

#### Links to Official Documentation

* Install ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd](https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd)

* Login to ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli](https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli)

* ArgoCD Configuration: [https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/)
