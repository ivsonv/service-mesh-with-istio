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
````
- curl -L https://istio.io/downloadIstio | sh -
- istionctl install -y
- kubectl get pods -n istio-system
- kubectl get svc -n istio-system
```

# Terminal commands

```
- kubectl label namespace default istio-injection=enabled --overwrite (proxys in pods - ready 2/2)
```
