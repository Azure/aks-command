# mcr.microsoft.com/public/aks/command/runtime
FROM mcr.microsoft.com/oss/kubernetes/kubectl:v1.18.18

USER root
RUN apt update && apt install -y curl unzip inotify-tools && apt clean
RUN cd /tmp && curl -L https://get.helm.sh/helm-v3.5.2-linux-amd64.tar.gz | tar -zxvf - && mv linux-amd64/helm /bin/ && rm -rf /tmp/linux-amd64
