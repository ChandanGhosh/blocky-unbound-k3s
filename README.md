# blocky-unbound-k3s
Blocky and unbound duo with pod scaling using HPA on K3s cluster for ads blocking in home.

# Setup K3S
### K3S Version: v1.25.4+k3s1

# Install unbound

```
kubectl create ns unbound
kubectl apply -f unbound-conf.yaml -f unbound.yaml
```

# Install blocky

Update the external IPs of your Rancher cluster nodes in the blocky-service in blocky.yaml

```
kubectl create ns blocky
kubectl -n blocky apply -f blocky.yaml
```

### Use the Rancher cluster node IPs for DNS access from router or firewall
