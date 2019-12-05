# 11. MySql

* Create MySQL Single Instance and MySQL secret

```
kubectl apply -f mysql-single-secret/
```


* Install the press labs MySQL operator

```
helm repo add presslabs https://presslabs.github.io/charts
```

```
helm install presslabs/mysql-operator --namespace mysql-operator --name mysql-operator
```

```
kubectl create -f mysql-operator/mysql-secrets.yaml
```

```
kubectl create  -f mysql-operator/mysql-cluster.yaml
```
