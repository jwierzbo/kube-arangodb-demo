# Introduction
Docker imageg with kube-arangodb Helm chart inside

# Build image
```shell
docker build -t arangodb-demo .
```

# Usage

## Run docker container
```shell
export KUBE_CFG_PATH=~/.kube/config
docker run -it --rm -v $KUBE_CFG_PATH:/root/.kube/config arangodb-demo
```

## Install kube-arangodb chart from docker
```shell
>> helm install arango-deployment /chart/kube-arangodb.tar.gz --skip-crds
```