# Monitoring

Update domain names in values.yaml and install prometheus

```
kubectl apply -f basic-auth.yaml
helm upgrade --install --namespace monitoring -f values.yaml prom stable/prometheus-operator
kubectl apply -f dashboards/
kubectl apply -f service-monitors/
```
