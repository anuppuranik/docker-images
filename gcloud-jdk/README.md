# Ubuntu gcloud Oracle JDK

Extends the Official latest Ubuntu Image.
Installs the latest JDK - Liberica Bellsoft.
Adds a bunch of gcloud packages.

Use as:

    anuppuranik/gcloud-jdk:latest
    anuppuranik/gcloud-jdk:jdk25

Its perfect for use on Circle CI for testing.

Put this in your .circleci/config.yml file

    jobs:
      build:
        docker:
          - image: anuppuranik/gcloud-jdk:latest
      