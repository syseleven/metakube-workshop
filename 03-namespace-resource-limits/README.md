# 4. Namespace Resource Limits


Create namespace example

```
kubectl create namespace limits
```

Deploy Quota and Limits

```
kubectl apply -f container-limit-range.yml -n limits
```

Deploy test app

```
kubectl run test-app --image=nginxdemos/hello --namespace limits
```

See that default requests and limits have been applied

```
kubectl describe pod --namespace limits
```

Apply quota

```
kubectl apply -f pod-quota.yml -n limits
```

Scale up

```
kubectl scale deployment test-app --replicas 3 --namespace limits
```

Describe the resource and see that only one pod can be created

```
kubectl -n limits describe rs test-app-XXXX
```

Delete deployment

```
kubectl delete deployment test-app -n limits
```

Create second deployment

```
kubectl run test-app --image=nginxdemos/hello --namespace limits --requests="cpu=2"
```

Describe the resource and see that no pods can be created

```
kubectl -n limits describe rs test-app-XXXX
```

Delete limits namespace again

```
kubectl delete namespace limits
```





