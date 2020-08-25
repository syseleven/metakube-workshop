# 7. cert-manager

* Install and configure cert-manager for AWS Route53

```
kubectl apply --validate=false -f https://github.com/jetstack/cert-manager/releases/download/v0.16.1/cert-manager.crds.yaml
```

```
helm repo add jetstack https://charts.jetstack.io
```

```
helm repo update
```

```
kubectl create namespace cert-manager
```

```
helm upgrade --install cert-manager jetstack/cert-manager --namespace cert-manager --version v0.16.1
```

* Add AWS Secret Key to `route53/credentials-secret.yaml`

* Add AWS Access Key to `route53/clusterissuer.yaml`

* Create ClusterIssuer

```
kubectl apply -f route53/credentials-secret.yaml
```

```
kubectl apply -f route53/clusterissuer.yaml
```

* Change hostnames in `certificate.yaml`
* Create wildcard certificate

```
kubectl apply -f route53/certificate.yaml
```
##########################################################################################################################

* Install and configure cert-manager for designate

```
kubectl apply --validate=false -f https://github.com/jetstack/cert-manager/releases/download/v0.16.1/cert-manager.crds.yaml
```

```
helm repo add jetstack https://charts.jetstack.io
```

```
helm repo update
```

```
helm upgrade --install cert-manager jetstack/cert-manager --namespace cert-manager --version v0.16.1
```

* Clone the designate certmanger repository and follow the install instructions

```
git clone git@github.com:syseleven/designate-certmanager-webhook.git
```

* Create ClusterIssuer

```
kubectl apply -f designate/clusterissuer.yaml
```

* Change hostnames in `certificate.yaml`
* Create wildcard certificate

```
kubectl apply -f designate/certificate.yaml
```
