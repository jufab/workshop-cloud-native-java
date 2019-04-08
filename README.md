# Cloud-native Java Workshop

This workshop demonstrates the use of MicroProfile, Docker, Kubernetes and Istio technologies for implementing, deploy and update a set of cloud-native microservices. The workshop has be structured as two parts:
* **Part 1** covers the foundational technologies for producing and consuming REST services and handling faults
* **Part 2** covers the deployment, scaling and updating of microserivces at scale, through Kubernetes and Istio.

This workshop is based off a longer version that can be found here:

https://github.com/gcharters/workshop-cloud-native-java


Each workshop part consists of a number of Open Liberty Guides each of which demonstrates a key cloud-native microservice technology. Each Guide is
designed to be taken independently so if you just want to learn about a specific technology you can just take that guide. If, however, you're goal is to learn about all the technologies, then working through them in the order shown below is recommended.

## Table of Contents
- [Cloud-native Java Workshop](#cloud-native-java-workshop)
  - [Table of Contents](#table-of-contents)
  - [Workshop Preparation](#workshop-preparation)
    - [Pre-requisites](#pre-requisites)
    - [Downloads](#downloads)
- [Introduction](#introduction)
- [Part 1: Java with MicroProfile](#part-1-rest-foundation)
    - [Creating a RESTful web service](#creating-a-restful-web-service)
    - [Building fault-tolerant microservices with the @Fallback annotation](#building-fault-tolerant-microservices-with-the-fallback-annotation)
- [Part 2: Kubernetes and Istio](#part-2-microservice-deployment-and-update)
    - [Configuring microservices running in Kubernetes](#configuring-microservices-running-in-kubernetes)
    - [Checking the health of microservices on Kubernetes](#checking-the-health-of-microservices-on-kubernetes)
    - [Managing microservice traffic using Istio](#managing-microservice-traffic-using-istio)



## Workshop Preparation

To save time during the workshop, it's best to set up your machine beforehand. The instructions below show the pre-requisites to install and how to avoid lengthy downloads.

### Pre-requisites

To use these guides you need the following pre-requisites:
1. A Java 8 JDK (e.g. https://adoptopenjdk.net/?variant=openjdk8&jvmVariant=openj9)
2. Apache Maven 3.5.4 or later (https://maven.apache.org/). Older versions may not work.
3. A git client
4. An editor with Java support (e.g. Eclipse, VS Code, IntelliJ)
5. Docker & Kubernetes:
   1. Windows: https://docs.docker.com/docker-for-windows/#kubernetes
   2. Mac: https://docs.docker.com/docker-for-windows/#kubernetes
   3. Linux: https://github.com/kubernetes/minikube#installation)
6. Download latest stable Istio release (not a Pre-release): https://github.com/istio/istio/releases

### Downloads

If you will be taking the workshop at a location with limited network bandwidth, it is recommended you do the following beforehand in order to populate your local .m2 repo and Docker cache.

```
git clone https://github.com/gcharters/workshop-cloud-native-java.git
cd workshop-cloud-native-java
mvn install
docker build -t prime:mym2 .
```

# Introduction

Cloud-native is an approach to application development and deployment.  It's the product of a number of industry movements over the past 10-15 years - agile development practices, DevOps, Microservices and Cloud.  Cloud-native applications are developed using agile practices, use continuous integration/continuous delivery to streamline deployment, are architected around team-aligned microservices, and leverage the cloud for rapid deployment at scale.

When choosing which technologies to use for cloud-native microservices, the combination of open source and open standards can be very important.  The combination enables a low cost (free) of entry and at the same time avoids being locked in to a single vendor implementation.  

Eclipse MicroProfile is a set of industry specifications for developing and deploying cloud-native Java Microservices.  The specifications address the important challenges of cloud-native microservices, such as toleration of service failures, security, service metrics and health, and more.  Open Liberty is an open source, lightweight, composable Java server that implements the MicroProfile specifications.

Kubernetes is an Open Source platform for deployment, scaling and managing containers and services.  It uses a declarative yaml-based approach to describe deployments, for example, the containers to be deployed, their scaling requirements, the services they provide, and so on.

Istio is an Open Source service mesh technology for the management of distributed microservices.  It enables securing, connecting and monitoring of microservice deployments.  Because Istio sits between the microservices in the mesh, it is able to route traffic (e.g. for blue-green deployments), handle faults (e.g. retry requests) and automatically secure service communications.

This workshop demonstrates how to address cloud-native microservice requirements using the combination of MicroProfile, Docker, Kubernetes and Istio technologies.  The workshop guides can be taken independently, or in the order they are introduced, below.

If you have feedback on a specific guide, we'd appreciated a github issue or pull request against that guide, and similarly if you have feedback on this workshop document, please raise an issue or submit a pull request.

# Part 1: Java with MicroProfile


### Creating a RESTful web service

Learn how to create a REST service with JAX-RS, JSON-P, and Open Liberty that will expose the JVM’s system properties.

The Guide: https://openliberty.io/guides/rest-intro.html

If you have feedback or find problems, please raise an issue here: https://github.com/OpenLiberty/guide-rest-intro



### Building fault-tolerant microservices with the @Fallback annotation

Learn how to use the MicroProfile Fault Tolerance specification to enable applications to function even when one
of the microservices is unavailable.

The Guide: https://openliberty.io/guides/microprofile-fallback.html

If you have feedback or find problems, please raise an issue here:
https://github.com/OpenLiberty/guide-microprofile-fallback


# Part 2: Kubernetes and Istio with MicroProfile


### Configuring microservices running in Kubernetes

Explore how to externalize configuration using MicroProfile Config and configure your microservices using Kubernetes ConfigMaps and Secrets.

https://openliberty.io/guides/kubernetes-microprofile-config.html

If you have feedback or find problems, please raise an issue here:
https://github.com/OpenLiberty/guide-kubernetes-microprofile-config


### Checking the health of microservices on Kubernetes

Learn how to check the health of microservices on Kubernetes by setting up readiness probes to inspect MicroProfile Health Check endpoints.

https://openliberty.io/guides/kubernetes-microprofile-health.html

If you have feedback or find problems, please raise an issue here:
https://github.com/OpenLiberty/guide-kubernetes-microprofile-health


### Managing microservice traffic using Istio

Explore how to manage microservice traffic using Istio.

https://openliberty.io/guides/istio-intro.html

If you have feedback or find problems, please raise an issue here:
https://github.com/OpenLiberty/guide-istio-intro
