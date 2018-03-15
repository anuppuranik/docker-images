# Ubuntu gcloud Oracle JDK 8

Extends the Official latest Ubuntu Image.
Installs the latest official Oracle JDK 8.
Adds a bunch of gcloud packages.

Use as:

    anuppuranik/gcloud-oracle-jdk8:latest

Its perfect for use on Circle CI for testing.

Put this in your .circleci/config.yml file

    jobs:
      build:
        docker:
          - image: anuppuranik/gcloud-oracle-jdk8:latest
      