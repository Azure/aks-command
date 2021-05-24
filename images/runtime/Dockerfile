# mcr.microsoft.com/public/aks/command/runtime
FROM alpine:latest

USER root
RUN apk --no-cache add unzip inotify-tools bash curl
RUN mkdir /k8stools
RUN curl -L https://dl.k8s.io/release/v1.18.19/bin/linux/amd64/kubectl -o /k8stools/kubectl && chmod +x /k8stools/kubectl
RUN cd /tmp && curl -L https://get.helm.sh/helm-v3.5.4-linux-amd64.tar.gz | tar -zxvf - && mv linux-amd64/helm /k8stools/ 
RUN rm -rf \
    /var/log/* \
    /tmp/* \
    /var/tmp/*

# Create a group and user
RUN addgroup -S aks && adduser -S nonroot -G aks
USER nonroot

ENV PATH "$PATH:/k8stools"