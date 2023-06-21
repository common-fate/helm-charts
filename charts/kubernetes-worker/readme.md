# Creating a secret for the worker token

```
kubectl create secret generic cf-worker --from-literal=worker-token='1934a37327a85cd56730f661f28ffcf8c0aafebf18c191b0df2db82db287d110'
```

# Installing

```
helm install worker-helm worker-helm --set 'cfRelayUrl=http://host.minikube.internal:8080' --set
cfClusterName=minikube
```
