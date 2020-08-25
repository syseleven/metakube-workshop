# 4. External DNS

* Install Helm: https://docs.helm.sh/using_helm/#installing-helm
```
helm init --client-only
helm repo update
```
* Change `AWS API and Secret` in values.yaml
* Change `txtOwnerId` in values.yaml
* Install external-dns with Helm

```
helm repo add bitnami https://charts.bitnami.com/bitnami
```

```
helm upgrade --install external-dns --namespace=external-dns -f values.yaml bitnami/external-dns
```
* Test the external dns with the nginx test deployment

```
kubectl apply -f nginx-test.yaml 
```
