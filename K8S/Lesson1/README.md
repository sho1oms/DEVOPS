# ReplicaSet


## Scale

```
kubetl replace -f replicaset-definition.yaml

kubectl scale --replicas=6 -f relicaset-definition.yaml

kubectl scale --replicas=6 replicaset myapp

```

# Deployment

```
Create an NGINX Pod

kubectl run nginx --image=nginx


Generate POD Manifest YAML file (-o yaml). Don't create it(--dry-run)

kubectl run nginx --image=nginx --dry-run=client -o yaml


Create a deployment

kubectl create deployment --image=nginx nginx


Generate Deployment YAML file (-o yaml). Don't create it(--dry-run)

kubectl create deployment --image=nginx nginx --dry-run=client -o yaml


Generate Deployment YAML file (-o yaml). Don't create it(--dry-run) with 4 Replicas (--replicas=4)

kubectl create deployment --image=nginx nginx --dry-run=client -o yaml > nginx-deployment.yaml

Save it to a file, make necessary changes to the file (for example, adding more replicas) and then create the deployment.

```

# Namespace

kubectl create -f pod-definitoon --namespace=dev

kubectl create namespace dev

kubectl get pod --namespace=dev

kubectl get pods --all-namespaces

Switch to namespace with context:

kubectl set config set-context$(kubectl config current-context) --namespace=dev


```
apiVersion:v1
kind: Namespace
metadata:
	name: dev
```

Resource quota on namespace
```
apiVersion: v1
kind: ResourceQuota
metadata:
  name: mem-cpu-demo
spec:
  hard:
    requests.cpu: "1"
    requests.memory: 1Gi
    limits.cpu: "2"
    limits.memory: 2Gi
```

## Rollback upgrade

```

# Record true - to save in list # kubectl rollout history deployment httpd-dep   

kubectl set image deployment httpd-dep httpd=httpd:2.4 --record=true

Revert deployment
kubectl rollout history deployment httpd-dep    
deployment.apps/httpd-dep
REVISION  CHANGE-CAUSE
1         <none>
2         kubectl.exe set image deployment httpd-dep httpd=httpd:2.4 --record=true


kubectl rollout undo deployment httpd-dep       
deployment.apps/httpd-dep rolled back


Status of rollout
kubectl rollout status deployment httpd-dep

Scale deployment

kubectl scale --replicas=0 deployment httpd-dep

Delete Deployment

kubectl delete httpd-dep
```

#AutoComplition in kubectl

```
kubectl completion --help
```
# Information about cluster
```
kubectl api-resources

kubectl api-versions
```