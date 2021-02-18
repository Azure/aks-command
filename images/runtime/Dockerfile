# mcr.microsoft.com/public/aks/command/runtime
FROM alpine:latest

RUN apk --no-cache add curl
RUN mkdir /k8stools
RUN curl -L https://dl.k8s.io/release/v1.17.17/bin/linux/amd64/kubectl -o /k8stools/kubectl && chmod +x /k8stools/kubectl
RUN cd /tmp && curl -L https://get.helm.sh/helm-v3.5.2-linux-amd64.tar.gz | tar -zxvf - && mv linux-amd64/helm /k8stools/ && rm -rf /tmp/linux-amd64
ENV PATH "$PATH:/k8stools"