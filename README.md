# Install ArgoWorkFlow 
- Create NameSpace and install CRD's with workflow. 
```
kubectl create ns argo
kubectl apply -n argo -f https://raw.githubusercontent.com/argoproj/argo-workflows/master/manifests/quick-start-postgres.yaml
```
- Forward port to open the UI : 
```
kubectl -n argo port-forward deployment/argo-server 2746:2746
```
- Test workflow by submitting following 

```
argo submit -n argo --watch https://raw.githubusercontent.com/argoproj/argo-workflows/master/examples/hello-world.yaml
argo list -n argo
argo get -n argo @latest
argo logs -n argo @latest
```