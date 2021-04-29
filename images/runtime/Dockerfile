# mcr.microsoft.com/public/aks/command/runtime
FROM mcr.microsoft.com/oss/kubernetes/kubectl:v1.18.18

USER root
RUN apt update && \
    apt install -y curl unzip inotify-tools && \
    apt clean -y 
RUN cd /tmp && curl -L https://get.helm.sh/helm-v3.5.2-linux-amd64.tar.gz | tar -zxvf - && mv linux-amd64/helm /bin/ 
RUN rm -rf \
        /var/cache/debconf/* \
        /var/lib/apt/lists/* \
        /var/log/* \
        /tmp/* \
        /var/tmp/*

USER nonroot
