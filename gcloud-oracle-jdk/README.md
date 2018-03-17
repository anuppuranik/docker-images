# Ubuntu gcloud Oracle JDK

Extends the Official latest Ubuntu Image.
Installs the latest official Oracle JDK.
Adds a bunch of gcloud packages.

Use as:

    anuppuranik/gcloud-oracle-jdk:latest
    anuppuranik/gcloud-oracle-jdk:jdk9
    anuppuranik/gcloud-oracle-jdk:jdk8

Its perfect for use on Circle CI for testing.

Put this in your .circleci/config.yml file

    jobs:
      build:
        docker:
          - image: anuppuranik/gcloud-oracle-jdk:latest
      