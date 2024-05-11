# Configurations

## k3d
k3d is a lightweight wrapper to run k3s (Rancher Lab’s minimal Kubernetes distribution) in docker.
- https://k3d.io

MacOs
```
brew install k3d
```

Creating cluster

```
- k3d cluster create -p 8000:30000 --agents 2
- kubectl config use-context k3d-k3s-default
- kubectl get nodes
```

# Istio
- https://istio.io/latest/docs/setup/getting-started/

MacOs
```
- curl -L https://istio.io/downloadIstio | sh -
- istionctl install -y
- kubectl get pods -n istio-system
- kubectl get svc -n istio-system
```

# Addons
- https://github.com/istio/istio/tree/release-1.21/samples/addons

NOTE: Wait a moment, as the first command may take a while to apply

```
- kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/prometheus.yaml
- kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/kiali.yaml
- kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/jaeger.yaml
- kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/grafana.yaml
```

# Terminal commands

```
- kubectl label namespace default istio-injection=enabled --overwrite (proxys in pods - ready 2/2)
- istioctl dashboard kiali
- while true; do curl http://localhost:8000; echo; sleep 0.5; done; (hack)
```
