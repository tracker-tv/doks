# DOKS

Set up a Digital Ocean Kubernetes cluster.

It will create a k8s cluster with 2 node pool with 1 node each (`s-2vcpu-2gb` and `s-2vcpu-4gb`).

## ArgoCD

ArgoCD will be installed in `s-2vcpu-4gb` node pool.

Get ArgoCD password for `admin` account:
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```  

Forward the ArgoCD webui to your local machine:
```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

If you want to configure a domain for ArgoCD, don't forget to update DNS server with the following records into your registrar:
```bash
ns1.digitalocean.com
ns2.digitalocean.com
ns3.digitalocean.com
```
