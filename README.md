# DOKS

Set up a Digital Ocean Kubernetes cluster.

It will create a k8s cluster with 2 node pool with 1 node each (`s-2vcpu-2gb` and `s-2vcpu-4gb`).

## ArgoCD

ArgoCD will be installed in `s-2vcpu-4gb` node pool.

Forward the ArgoCD webui to your local machine:
```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
