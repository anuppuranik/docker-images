# Ubuntu gcloud Python2 docker-ce

Extends the Official latest Ubuntu Image.
Installs python 2
Installs docker-ce (to build and publish docker images)
Adds a bunch of gcloud packages.

Use as:

    anuppuranik/node-python2-gcloud:latest

Its perfect for use on Circle CI for testing.

Put this in your .circleci/config.yml file

    jobs:
      build:
        docker:
          - image: anuppuranik/node-python2-gcloud:latest
      