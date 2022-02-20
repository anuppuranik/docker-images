# Docker Images

This is my collection of personal docker images. They are for public use.
They are available at https://hub.docker.com/u/anuppuranik

All images have the following, so they are pefect for use on Circle Ci.

- Ubuntu Base
- Official Oracle JDK
- Google Cloud Tools (gcloud)
- Docker Ce

Docker tags:

[![](https://images.microbadger.com/badges/version/anuppuranik/gcloud-oracle-jdk.svg)](https://hub.docker.com/r/anuppuranik/gcloud-oracle-jdk "Go to docker hub")

[![](https://images.microbadger.com/badges/version/anuppuranik/gcloud-oracle-jdk:jdk12.svg)](https://hub.docker.com/r/anuppuranik/gcloud-oracle-jdk "Go to docker hub")

Deprecated:

[![](https://images.microbadger.com/badges/version/anuppuranik/gcloud-oracle-jdk:jdk10.svg)](https://hub.docker.com/r/anuppuranik/gcloud-oracle-jdk "Go to docker hub")

[![](https://images.microbadger.com/badges/version/anuppuranik/gcloud-oracle-jdk:jdk8.svg)](https://hub.docker.com/r/anuppuranik/gcloud-oracle-jdk "Go to docker hub")

Maintain Commands:
docker build -t anuppuranik/gcloud-python3-node:latest -t anuppuranik/gcloud-python3-node:$(date '+%Y%m%d') - < Dockerfile
docker push anuppuranik/gcloud-python3-node:$(date '+%Y%m%d')
docker push anuppuranik/gcloud-python3-node:latest
