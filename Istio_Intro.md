* In standard K8s we do not have visibility or control over the connections of the contianers
* Service mesh is a layer of software, All network traffic that is running through our cluster is going to be routed through service mesh software
* Mesh Logic
* Implement security - Masswive feature of the service mesh
* Traffic Management
* Istio is deploys the proxy container in each pod
* At the proxy - Mesh logic is implemented
* Namespace - istio-system

* Istiod - Istio Daemon (used to be called as pilot)
* Data Plane - The proxies are collectively called Data plane in istio
* Kiali UI -
* Monitor and Manage traffic that is moving between pods

```
git clone https://github.com/genessosagar/istio-fleetman.git
cd istio-fleetman
kubectl apply -f 1-istio-init.yaml
kubectl apply -f 2-istio-minikube.yaml
kubectl get ns
kubectl get pods -n istio-system
```
* Following containers are created
grafana - for graphical representation
egressgateway - Traffic going out of cluster
ingressgateway - Traffic going into cluster
tracing - 
istiod - 
prometheus - monitoring
Kiali - Graphical Interface

* Namespace labeling
- If we want istio to gather data of a particular namespace - we add a label to that namespace
- If we want istio to gather data of all the namespaces - we will add a label to all namespaces
```
kubectl describe ns default
kubectl label namespace default istio-injection=enabled
kubectl describe ns default
```
or 

* If we want to store it in the yaml 
```
kubectl get ns default -o yaml
```

* Envoy, Sidecar, Proxy - All are same
* kiali - 31000
* Application - 30080
* Jaeger - 31001
* Grafana - 31002