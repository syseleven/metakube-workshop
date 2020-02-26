# 2. Webapp Deployment

* Install webapp deployment:
```
kubectl apply -f webapp-deploy.yml
```

* Install webapp service
```
kubectl apply -f webapp-svc.yml
```

* Use kubectl to proxy remote port 8080 to your local port 8080
```
kubectl port-forward deployment/webapp 8080:8080
```
