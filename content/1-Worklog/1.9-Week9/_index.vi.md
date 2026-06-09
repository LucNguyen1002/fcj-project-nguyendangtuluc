---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu tuần 9:

* Tìm hiểu Docker và containerization.
* Tìm hiểu Amazon ECS (Elastic Container Service) để chạy container trên AWS.
* Hiểu sự khác biệt giữa EC2 launch type và Fargate (serverless containers).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                                                                         | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tìm hiểu Docker cơ bản: <br>&emsp; + Container vs Virtual Machine <br>&emsp; + Docker Image, Container, Dockerfile <br>&emsp; + Docker Hub và Container Registry <br>&emsp; + Các lệnh cơ bản: build, run, push, pull                             | 16/06/2026   | 16/06/2026      | <https://000015.awsstudygroup.com>         |
| 3   | - **Thực hành Docker:** <br>&emsp; + Cài đặt Docker Desktop <br>&emsp; + Viết Dockerfile cho ứng dụng Node.js/Python đơn giản <br>&emsp; + Build image và chạy container local <br>&emsp; + Push image lên Amazon ECR (Elastic Container Registry)    | 17/06/2026   | 17/06/2026      | <https://000015.awsstudygroup.com>         |
| 4   | - Tìm hiểu Amazon ECS: <br>&emsp; + ECS Cluster, Task Definition, Service <br>&emsp; + EC2 launch type vs Fargate launch type <br>&emsp; + Task IAM Role <br>&emsp; + Tích hợp ECS với ALB                                                          | 18/06/2026   | 18/06/2026      | <https://000016.awsstudygroup.com>         |
| 5   | - **Thực hành ECS với Fargate:** <br>&emsp; + Tạo ECS Cluster <br>&emsp; + Tạo Task Definition sử dụng image từ ECR <br>&emsp; + Deploy Service với Fargate <br>&emsp; + Cấu hình ALB phía trước ECS Service                                         | 19/06/2026   | 19/06/2026      | <https://000016.awsstudygroup.com>         |
| 6   | - Tìm hiểu thêm về ECS: <br>&emsp; + Auto Scaling cho ECS Service <br>&emsp; + CloudWatch Container Insights <br>&emsp; + So sánh ECS vs EKS (Kubernetes) <br> - Ôn tập và tổng kết kiến thức container                                              | 20/06/2026   | 20/06/2026      | <https://000016.awsstudygroup.com>         |


### Kết quả đạt được tuần 9:

* Hiểu được Docker và containerization:
  * Phân biệt Container và Virtual Machine
  * Dockerfile: FROM, RUN, COPY, EXPOSE, CMD
  * Docker Image lifecycle: build → tag → push → pull → run
  * Amazon ECR để lưu trữ Docker images trên AWS

* Đã thực hành Docker thành công:
  * Viết Dockerfile cho ứng dụng đơn giản
  * Build image, chạy container trên máy local
  * Push image lên Amazon ECR

* Nắm được Amazon ECS:
  * Cluster: nhóm các resources chạy container
  * Task Definition: blueprint cho container (image, CPU, memory, ports)
  * Service: duy trì số lượng task mong muốn
  * EC2 launch type: tự quản lý EC2 instances
  * Fargate launch type: serverless, không cần quản lý server

* Đã thực hành ECS với Fargate thành công:
  * Tạo Cluster và deploy Service với Fargate
  * Kết hợp ALB để load balance traffic đến các containers
  * Cấu hình Auto Scaling cho ECS Service
  * Theo dõi container với CloudWatch Container Insights

* Hiểu được sự khác biệt giữa ECS và EKS:
  * ECS: đơn giản, tích hợp sâu với AWS, phù hợp cho đa số use case
  * EKS: Kubernetes managed, phù hợp khi cần portability hoặc đã quen Kubernetes

