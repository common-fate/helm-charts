# You can pass `cfRelayURL` to overwrite production relay. 

# Installing
```
helm install worker-helm worker-helm --set 'cfRelayUrl=http://host.minikube.internal:8080' --set
cfClusterName=minikube
```
