---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

# Summary Report: "AWS Vietnam Community Day 2026"

### Event Objectives

- Bring together the AWS community in Vietnam to share knowledge and real-world experience.
- Introduce the latest AWS technologies and services through presentations by industry experts.
- Create networking opportunities among developers, engineers, and the AWS community.

### Speakers

| # | Speaker | Title / Role | Topic |
|---|---------|-------------|-------|
| 1 | **Tinh Truong** | Platform Engineer @ GoTymeX | Context Is Everything – Making AI Actually Work for You |
| 2 | **Pham Ng Hai Anh** | AWS Community Builder @ G-AsiaPacific Vietnam | Friendly AI Assistant w/ Amazon Quick |
| 3 | **Nguyen Tuan Thinh** | AWS Champion Instructor, 12x AWS Certified | From Edge To Origin: CloudFront as Your Foundation |
| 4 | **Team VIB** | AWS Track Winner (LotusHacks 2026) | 36 hrs with LotusHacks – Building UTMorpho |
| 5 | **Duc Dao** | Solution Architect @ Cloud Kinetics | Non-Determinism of "Deterministic" LLM Settings |
| 6 | **Vy Lam** | Sr. Business Systems Analyst @ VPBank | Enterprise-Grade Multi-Agent System |

### Key Highlights – "From Edge To Origin: CloudFront as Your Foundation"

Among all the presentations, I was most impressed by **Nguyen Tuan Thinh**'s talk about **Amazon CloudFront** because its content was very accessible and directly related to the basic AWS knowledge I'm currently learning.

#### What is Amazon CloudFront?

- AWS's **CDN (Content Delivery Network)** that delivers content to users with high speed and low latency.
- AWS owns **600+ Points of Presence (PoPs)** spanning 100+ cities in 50+ countries, connected by Amazon's own fiber optic private backbone.
- **Vietnam** has 2 Edge Locations in **Hanoi** and **Ho Chi Minh City**, with direct peering to major ISPs: Viettel, VNPT, FPT, CMC.

#### Why CloudFront?

- **Without CDN**: A Vietnamese user accessing a US server → data travels through many hops on public internet → latency **200ms+**.
- **With CloudFront**: Static content is cached at the nearest Edge → latency drops to **under 10ms**.

#### Dynamic Content Acceleration

- CloudFront doesn't only cache static content – it also **optimizes the path for dynamic requests** (which cannot be cached).
- Uses **connection pooling**, **TCP handshake reuse**, and the **AWS private backbone** to reduce latency.

#### Flexible Origins

CloudFront supports multiple origin types:
- AWS: S3, EC2, ALB, API Gateway, Lambda Function URL
- Non-AWS: On-premise servers or other cloud providers

#### Security with CloudFront

- **AWS Shield Standard**: Default DDoS protection, free of charge.
- **AWS WAF**: Blocks SQL injection, XSS, bots, rate limiting at the Edge.
- **Free SSL/TLS**: Integrates with AWS Certificate Manager (ACM), auto-renewal.
- **Mutual TLS (mTLS)**: Two-way authentication for financial and high-security use cases.
- **Origin cloaking**: Hides the origin from public internet via VPC Origin, OAC, or custom headers.
- **Geo Restriction**: Allow/block access by country.
- **Signed URL**: Protects paid content with encrypted signature URLs, time and IP restrictions.

#### High Availability

- **Caching**: Not just for speed – keeps the system running even when the origin is down (serves stale content).
- **Origin Failover**: Automatically routes to a secondary origin when the primary fails.
- **Custom Error Page**: Displays user-friendly error pages instead of defaults.

#### Performance Optimization

- **Multi-layer caching**: PoPs → Regional Edge Caches → Origin Shield → Origin. Request collapsing reduces origin load (10,000 requests → collapsed to 1).
- **HTTP/3 (QUIC/UDP)**: Downloads dozens of resources in parallel (vs. 4-6 with HTTP/1.1).
- **HTTP Compression**: Reduces page load time by 81%.
- **Persistent Connections**: Maintains open connections to origin, skipping TCP handshake for subsequent requests.

#### Edge Computing

- **CloudFront Functions**: Ultra-fast (<1ms), lightweight JavaScript, ideal for URL rewrites, header modifications, redirects.
- **Lambda@Edge**: Full Node.js/Python runtime, suited for complex logic, A/B testing, geo redirects.

### Key Takeaways

#### Technical Knowledge

- Understood how CDN works and why it's critical for performance and security.
- Learned how CloudFront optimizes both static and dynamic content.
- Understood multi-layer caching architecture and request collapsing.
- Grasped security features from basic (Shield, WAF) to advanced (mTLS, Signed URL, Origin cloaking).

#### System Design Thinking

- CloudFront is not just "image caching" – it's a **comprehensive protection layer** for the entire system.
- Origin cloaking completely hides servers from the public internet.
- Edge computing allows processing logic closest to users without reaching the origin.

#### Practical Applications

- CloudFront can be applied to the workshop project (IoT Weather Platform) for faster dashboard delivery.
- Combining CloudFront + S3 for static website hosting with better performance and security.
- Using Signed URLs for content requiring access control.

### Event Experience

Attending the **AWS Vietnam Community Day 2026** was a very rewarding and memorable experience. Key highlights include:

#### Learning from highly skilled speakers
- Nguyen Tuan Thinh, with **12 AWS certifications**, delivered an easy-to-understand presentation from basics to advanced topics.
- His use of practical examples (Vietnamese users accessing US servers) helped clearly visualize the problems CDN solves.

#### Expanding knowledge
- Beyond the CloudFront talk, presentations on AI/LLM and Multi-Agent Systems showcased the latest technology trends on AWS.
- Team VIB's hackathon experience showed how to apply AWS to real products in a short timeframe.

#### Community networking
- Met developers and engineers from various companies.
- Felt the strong growth of the AWS community in Vietnam.

#### Lessons learned
- CloudFront is far more comprehensive than initially imagined (not just caching, but also security, edge computing, and high availability).
- Placing CloudFront in front of the system protects the origin, boosts performance, and reduces operational costs.
- Edge computing is an important trend, enabling logic processing closest to users.

#### Some event photos
![AWS Community Day 2026](/images/event1.jpg)

> Overall, the event not only provided deep technical knowledge about CloudFront but also broadened my perspective on designing efficient, secure, and high-performance systems on AWS.

