# unbound-blocky-k3s
Blocky and unbound duo with pod scaling using HPA on K3s cluster for ads blocking in home.
You can use only unbound which has built-in support for DNS based ad blocking. If you prefer a sophisticated ad blocker and your own recursive DNS server, you can go for Blocky with unbound as well.

# Setup K3S
Follow the official [guide](https://docs.k3s.io/quick-start)
### K3S Version: v1.25.4+k3s1

# Install unbound
This Unbound image has inbuild DNS based ad blocking support.
```
kubectl create ns unbound
kubectl apply -f unbound-conf.yaml -f unbound.yaml -n unbound
```

# Install blocky (Optional)
If you prefer Blocky for blocking your ads
Update the external IPs of your Rancher cluster nodes in the blocky-service in blocky.yaml

```
kubectl create ns blocky
kubectl -n blocky apply -f blocky.yaml
```

### Use the Rancher cluster node IPs for DNS access from router or firewall
