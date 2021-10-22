# Build the manager binary
FROM dtzar/helm-kubectl:3.7.1

WORKDIR /

ENV version=1.2.3
ENV URLPREFIX=https://github.com/arangodb/kube-arangodb/releases/download/${version}

RUN mkdir -p /chart
RUN curl -L -O $URLPREFIX/kube-arangodb-${version}.tgz
RUN mv kube-arangodb-${version}.tgz /chart/kube-arangodb.tar.gz
