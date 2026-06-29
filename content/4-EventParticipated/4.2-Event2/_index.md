---
title: "Event 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: "FCAJ Community Day - June 2026"

### Event Objectives

- A monthly recurring event providing a space for experts from various enterprises to share knowledge, real-world experiences, and practical insights from the workplace.
- Update on the latest technology trends in **Cloud** and **AI (Artificial Intelligence)**, how AI is reshaping Cloud Infrastructure and the job market.
- Create networking opportunities — both in-person (floors 26 and 36) and online (YouTube livestream) — among developers, engineers, students, and the tech community.

### Speakers

| # | Speaker | Title / Organization | Topic |
|---|---------|---------------------|-------|
| 1 | **Steve Trần** | Founder @ Cloud Thinker | Cloud/AI career, Multi-Agent & Single-Agent architecture in Cloud operations |
| 2 | **Hiếu Nghị, Kiệt, Trung Đ.** | Renova Cloud, AWS Study Builder, CEO @ R AI | Voice AI applications and Voice Agent architecture for Vietnamese |
| 3 | **Bảo & Nguyên** | Cloud Engineer @ Cloud Kinetics | AWS DevOps Agent: Automated investigation and incident resolution |
| 4 | **Trường (Wayne) & Minh Anh** | AI Solution @ Noventis | AI/Amazon Q in HR strategy and recruitment |
| 5 | **Toàn Nguyễn & Hiếu Nghị** | AWS Security Builder / Renova Cloud | Private Security setup for Amazon Q and MCP Server via VPC |

### Key Highlights – In-Depth Topics

The event covered multiple deep-dive topics. Below is a summary of the most notable content:

#### 1. Operations Automation with AWS DevOps Agent (Bảo & Nguyên)

**Problem:** When systems encounter incidents, engineers spend significant time investigating due to fragmented telemetry (scattered logs/traces), leading to context loss and high **MTTR (Mean Time To Recovery)**.

**What is AWS DevOps Agent?** An AI assistant that proactively automates research, log extraction, and **root cause** identification during incidents.

**How it works (4 steps):**
1. **Triage** – Collect and categorize alerts/incidents
2. **Investigate** – Extract logs, traces, and metrics to find root cause
3. **Mitigate** – Suggest temporary remediation actions
4. **Improve** – Propose long-term system improvements

> **Note:** AI only plays an analytical and recommendation role; the decision to execute remains with humans to ensure safety.

#### 2. Voice AI Potential in Vietnam (Hiếu Nghị, Kiệt, Trung)

**Core Architecture:** Instead of using traditional Speech-to-Speech models (which typically don't support Vietnamese well), the current optimal solution is:

> **Receive Audio → Speech-to-Text (STT) → Process via LLM → Text-to-Speech (TTS)**

**Solving real-world challenges:** The model needs to understand:
- User **interruption** context
- **Gender** differentiation (Vietnamese honorifics: anh/chị)
- **Regional accents** (e.g., Central Vietnamese dialect) for the most natural AI communication

#### 3. Amazon Q Revolutionizing HR (Trường & Minh Anh)

**HR Challenges:** Manual CV reading is time-consuming, prone to missing talent, subjective, and risks data leakage when using public AI tools.

**Solution with Amazon Q:**
- Create specialized **Agent Skills** to automatically read and scan CVs from multiple sources (SharePoint, Google Drive, Outlook).
- Amazon Q can **extract skills**, compare candidates against **Job Descriptions (JD)**, and automatically generate **assessment reports** without data leakage risks.

#### 4. Secure Connection Setup for Amazon Q (Toàn Nguyễn)

**Security:** Amazon Q must not connect to **MCP (Model Context Protocol) Server** via Public Internet to prevent **DDoS** or **Man-in-the-Middle** attacks.

**Solution:** Route Amazon Q connections through a private network interface (**VPC Connection**), using **internal DNS** and **ALB (Application Load Balancer)** to ensure all query data stays entirely within the AWS Cloud.

### Key Takeaways

#### Technical Knowledge

- Understood modern **AI architectures**: Differences between **Single-Agent** and **Multi-Agent**, Voice AI workflow (**STT → LLM → TTS**).
- Gained knowledge of new AWS tools: Using **Amazon Q** for Agentic workflows and **AWS DevOps Agent** for network topology analysis.
- Learned to design secure AWS infrastructure using **VPC**, **Resolver**, and **ALB** to keep AI endpoints private from the public internet.

#### System Design Thinking

- **Automation mindset:** Shifting from manual operations (like fixing server errors, screening CVs) to using AI Agents as data analysis assistants.
- AI systems don't replace humans but **"amplify" engineer capabilities**. The prerequisite for AI to work well is that systems must have good **Observability** and complete log/metric collection.

#### Practical Applications

- Can apply **Voice AI** architecture to build automated customer service bots for Vietnamese businesses.
- Apply **Amazon Q** in enterprises for **Business Intelligence**, automating recruitment workflows (HR tracking), or writing internal reports without being locked into a single ecosystem.

### Event Experience

Attending **FCAJ Community Day - June 2026** was a highly rewarding and memorable experience. Key highlights:

#### Learning from highly skilled speakers
- Had the opportunity to listen to **founders** and **experienced experts** from AWS, Cloud Thinker, Renova Cloud, Noventis...
- Speakers didn't just discuss theory — they **live-demoed** AWS-based products and solutions.

#### Expanding knowledge
- Gained clear awareness of the changing IT job market. Positions like Developer and Cloud Engineer are shifting in requirements — companies now prioritize hiring people who can **apply AI** (Seniors working with AI) rather than just hiring in large numbers.

#### Community networking
- Actively participated in **Q&A sessions** with speakers on challenging real-world issues (such as cost optimization, regional accent processing, setting up AI logic).
- Felt the strong growth of the AWS tech community in Vietnam.

#### Lessons learned
- The rise of AI doesn't mean complete job loss, but it demands that people **level up** to become proficient "AI users."
- Adopting new technology must always go hand-in-hand with solving real business **pain points** (such as cost optimization, reducing downtime, and data security).
- Early exposure to enterprise environments and continuously updating on new Cloud/AI solutions (like **Amazon Q**, **AWS DevOps Agent**) is the key to advancing one's career.

#### Some event photos
![FCAJ Community Day June 2026](/images/event2.jpg)

> Overall, the FCAJ Community Day provided not only deep technical knowledge about AI and Cloud but also broadened my perspective on how AI is reshaping the tech industry — from system operations and HR to security — and most importantly, how to equip myself to adapt to these changes.
