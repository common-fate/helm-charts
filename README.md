# Common Fate Kubernetes Helm Charts 

## Usage 
[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:
```console
helm repo add common-fate https://common-fate.github.io/helm-charts/
```

You can then run `helm search common-fate` to see the charts.

## Installation 
You can install the Common Fate Kubernetes Worker using the following command:
```console
helm install --set cfClusterName=<your_cluster_name> common-fate/commonfate-worker --generate-name
```

After installation is complete, you need to provide worker token secret to the Common Fate Kubernetes Worker. 
You can generate a worker token through the Common Fate Cloud Web Application. 

Once you have the worker token, run the following command: 
kubectl create secret generic cf-worker --from-literal=worker-token='<your_worker_token_value>'