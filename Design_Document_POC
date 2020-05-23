Design Document ::

Wordpress Application

Overview:

Application to be hosted as containers to sustain a traffic pattern as below.
This document provides a high level architecture that will span the application
with the high availability, self healing and autoscaling features by maintaining state.

Context:

This is a POC for the application to be hosted on GCP/GKE. Google kubernetes Engine
provides the best way to manage the orchestration of containers with its resilient feature
allowing high availability and highly scalability deployed into various regions
as per the requirement.

Goals and Non-Goals:

The goal of the task is to achieve sustainable infrastructure in GCP with uptime
and low complexity of infrastructure management.

Cost is the least important factor.

Milestones:

This design will determine a benchmark for any application for a highly available
and scalable hosting accomplishing the target to the end goal.

Proposed Solution ::

  Infra:
  kubernetes Clusters to be created in GCP with a Virtual Private Cloud with
  networks spanning globally covering different regions. We will be creating 2 clusters
  one in us-central1 region and the other in asia-northeast1. For high availability
  cluster and node autoscaling is enabled.

  Application Image:
  Using docker with the available Wordpress image and mysql image in
  docker hub we will create Images with custom settings to adopt the environment to our needs.
  For POC I have created readily available Wordpress and mysql images and pushed it to the
  google cloud registry for deploying in kubernetes clusters.

  Container Orchestration:
  I have created a basic deployment yaml that have the
  objects such as pod definition, replica set, environment variable for connecting
  to mysql, container image, ports, labels that will allow for the orchestration.

  Created a plain service yaml defining the route to the application container by using
  the concept of labels. It is a loadbalancer type service that creates an external IP to
  expose the application acting as a gateway.

  HPA: Created HPA to scale the application horizontally with a target CPU of 50%
  and min max pods of 1 and 10. We need to determine the exact foot print of
  resource like cpu/memory by running a performance test.
