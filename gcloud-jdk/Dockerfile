FROM ubuntu:latest

LABEL maintainer="anuppuranik @t g m a i l c o m"

ENV DEBIAN_FRONTEND=noninteractive 

# Upgrade the base distro
#RUN apt-get update && apt-get upgrade -y

# Install some common tools and packages
RUN apt-get update && apt-get install -y software-properties-common \
        zip \
        unzip \
        git \
        gpg \
        ssh \
        curl \
        apt-transport-https \
        ca-certificates

# Minor setup
RUN mkdir -m 0755 -p /etc/apt/keyrings/

# Docker
RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc && \
    chmod a+r /etc/apt/keyrings/docker.asc && \
    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
    $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
    tee /etc/apt/sources.list.d/docker.list > /dev/null && \
    apt-get update && \
    apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin && \
    apt-get clean

# Liberica Bellsoft JDK
RUN curl -fsSL https://download.bell-sw.com/pki/GPG-KEY-bellsoft | gpg --dearmor | tee /etc/apt/keyrings/GPG-KEY-bellsoft.gpg > /dev/null && \
    echo "deb [arch=$(dpkg --print-architecture) \
    signed-by=/etc/apt/keyrings/GPG-KEY-bellsoft.gpg] \
    https://apt.bell-sw.com/ stable main" | tee /etc/apt/sources.list.d/bellsoft.list && \
    apt-get update && \
    apt-get install -y bellsoft-java25 && \
    apt-get clean

# gcloud sdk
RUN . /etc/os-release && \
    export CLOUD_SDK_REPO="cloud-sdk" && \
    echo "deb http://packages.cloud.google.com/apt $CLOUD_SDK_REPO main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list && \
    wget https://packages.cloud.google.com/apt/doc/apt-key.gpg && apt-key add apt-key.gpg && rm apt-key.gpg && \
    apt-get update && \
    apt-get install -y \
        google-cloud-sdk \
        google-cloud-sdk-app-engine-go \
        google-cloud-sdk-app-engine-java \
        google-cloud-sdk-app-engine-python \
        google-cloud-sdk-app-engine-python-extras \
        google-cloud-sdk-bigtable-emulator \
        google-cloud-sdk-cbt \
        google-cloud-sdk-datalab \
        google-cloud-sdk-datastore-emulator \
        google-cloud-sdk-pubsub-emulator \
        kubectl && \
    apt-get clean

# make suitable for circle ci
RUN adduser circleci --home /home/circleci --gecos "" --disabled-password

USER circleci
