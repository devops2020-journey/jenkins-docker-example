# jenkins-docker-example

This repo code is intend to build and publish docker image in docker hub.

Attached the Jenkinsfile here for steps.

Important steps:
pre-requisites:

Jenkins plugins installation:
  1.Maven Integration 
  2.Pipeline maven integration.
  3.pipeline utility steps.

Docker installation.

Configure global tools for Maven.


In stage "push docker image"
    update credential for docker login.
       variable type :secret text 
       secret : docker login password.
       ID : you can choose anything for this secret.

