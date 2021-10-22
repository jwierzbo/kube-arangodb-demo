# Introduction

Initial RBAC for namespace-wide access used by arangodb operator deployment

# Chart Details

Chart will install fully namespace admin ServiceAccount which will allow to deploy arangodb operator in particular namespace.

# Prerequisites

Cluster admin role is required to deploy this chart.

# Installing the Chart

Run following command using helm3 and then follow on-screen commands to configure your k8s context
```
helm install arango-init . --namespace demo-jwierzbo --create-namespace --wait
```

To update existing Helm deployment:
```helm upgrade arango-init . --namespace demo-jwierzbo --wait```

# Install kube-arangodb chart with your new context

```shell
kubectl config set current-context demo-jwierzbo

export version=1.2.3
export URLPREFIX=https://github.com/arangodb/kube-arangodb/releases/download/${version}

helm install arango-deployment $URLPREFIX/kube-arangodb-${version}.tgz --skip-crds \
             --set operator.features.deployment=true \
             --set operator.features.deploymentReplications=false \
             --set operator.features.storage=false

```