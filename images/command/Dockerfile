FROM alpine:latest

RUN apk add curl
RUN mkdir /k8stools
RUN curl -L https://dl.k8s.io/release/v1.20.0/bin/linux/amd64/kubectl -o /k8stools/kubectl && chmod +x /k8stools/kubectl
RUN cd /tmp && curl -L https://get.helm.sh/helm-v3.5.2-linux-amd64.tar.gz -o helm.tar.gz && tar -zxvf helm.tar.gz && mv linux-amd64/helm /k8stools/ && chmod +x /k8stools/helm && rm -rf /tmp/linux-amd64 && rm /tmp/helm.tar.gz