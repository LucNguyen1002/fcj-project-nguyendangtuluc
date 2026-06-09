---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn about Docker and containerization.
* Learn about Amazon ECS (Elastic Container Service) for running containers on AWS.
* Understand the difference between EC2 launch type and Fargate (serverless containers).

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                                                             | Start Date  | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | --------------- | ----------------------------------------- |
| Mon | - Learn Docker basics: <br>&emsp; + Container vs Virtual Machine <br>&emsp; + Docker Image, Container, Dockerfile <br>&emsp; + Docker Hub and Container Registry <br>&emsp; + Basic commands: build, run, push, pull                                | 06/16/2026  | 06/16/2026      | <https://000015.awsstudygroup.com>         |
| Tue | - **Practice Docker:** <br>&emsp; + Install Docker Desktop <br>&emsp; + Write a Dockerfile for a simple Node.js/Python app <br>&emsp; + Build image and run container locally <br>&emsp; + Push image to Amazon ECR (Elastic Container Registry)      | 06/17/2026  | 06/17/2026      | <https://000015.awsstudygroup.com>         |
| Wed | - Learn about Amazon ECS: <br>&emsp; + ECS Cluster, Task Definition, Service <br>&emsp; + EC2 launch type vs Fargate launch type <br>&emsp; + Task IAM Role <br>&emsp; + Integrating ECS with ALB                                                    | 06/18/2026  | 06/18/2026      | <https://000016.awsstudygroup.com>         |
| Thu | - **Practice ECS with Fargate:** <br>&emsp; + Create an ECS Cluster <br>&emsp; + Create Task Definition using image from ECR <br>&emsp; + Deploy Service with Fargate <br>&emsp; + Configure ALB in front of ECS Service                              | 06/19/2026  | 06/19/2026      | <https://000016.awsstudygroup.com>         |
| Fri | - Learn more about ECS: <br>&emsp; + Auto Scaling for ECS Service <br>&emsp; + CloudWatch Container Insights <br>&emsp; + Comparing ECS vs EKS (Kubernetes) <br> - Review and summarize container knowledge                                          | 06/20/2026  | 06/20/2026      | <https://000016.awsstudygroup.com>         |


### Week 9 Achievements:

* Understood Docker and containerization:
  * Differentiated Container and Virtual Machine
  * Dockerfile: FROM, RUN, COPY, EXPOSE, CMD
  * Docker Image lifecycle: build → tag → push → pull → run
  * Amazon ECR for storing Docker images on AWS

* Successfully practiced Docker:
  * Wrote Dockerfile for a simple application
  * Built image, ran container locally
  * Pushed image to Amazon ECR

* Mastered Amazon ECS:
  * Cluster: group of resources running containers
  * Task Definition: blueprint for containers (image, CPU, memory, ports)
  * Service: maintains desired number of tasks
  * EC2 launch type: self-managed EC2 instances
  * Fargate launch type: serverless, no server management needed

* Successfully practiced ECS with Fargate:
  * Created Cluster and deployed Service with Fargate
  * Combined ALB to load balance traffic to containers
  * Configured Auto Scaling for ECS Service
  * Monitored containers with CloudWatch Container Insights

* Understood the difference between ECS and EKS:
  * ECS: simpler, deeply integrated with AWS, suitable for most use cases
  * EKS: managed Kubernetes, suitable when portability is needed or team is familiar with Kubernetes

