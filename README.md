# Install the Grafana stack on Kubernetes (Minikube)

```
helm repo add grafana https://grafana.github.io/helm-charts
```

## Loki

You can apply the included manifest file as is.

## Prometheus

You can apply the included manifest file as is.

## Grafana

You can apply the included manifest file as is.

## Alloy

```
cd alloy
helm install --namespace monitoring alloy grafana/alloy
kubectl create configmap --namespace monitoring alloy-config "--from-file=config.alloy=./config.alloy"
helm upgrade alloy grafana/alloy -n monitoring -f alloy-values.yaml
```

## Tempo

```
cd tempo
helm install -n monitoring tempo grafana/tempo
helm upgrade tempo grafana/tempo -n monitoring -f tempo-values.yaml
```