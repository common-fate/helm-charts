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

Common Fate Worker supports multiple protocol and it is essential to set correct argument when installing the helm chart. 

Before installation, you need to create and set worker token secret to your kubectl context. 
You can generate a worker token through the Common Fate Cloud Web Application. 

Once you have the worker token, run the following command: 
```
kubectl create secret generic cf-worker --from-literal=worker-token='<your_worker_token_value>'
```

For, postgres protocol, you also need to set your Postgres connection URL as kubectl secret. Run the following command: 
```
kubectl create secret generic cf-pgdb-dsn --from-literal=pgdb-dsn='your_postgres_connection_url'
```

1. To install the Common Fate Kubernetes Worker, use the following command:
```console
helm install --set 'cfProtocol={kubernetes}' --set cfClusterName=<your_cluster_name> common-fate/commonfate-worker --generate-name
```

2. To install the Common Fate Postgres Worker, use the following command:
```console
helm install --set c'fProtocol={postgres}' --set cfPostgresDSN=<your_postgres_connection_string> common-fate/commonfate-worker --generate-name
```


