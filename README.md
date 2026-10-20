# DevOps Roadmap

A practical, project-based roadmap for anyone who wants to become a DevOps engineer — from Linux basics to Kubernetes on AWS.

*The learning journey never really ends. There's always something new to learn, another skill to build, and another way to grow. 🚀✨*

It follows the [KodeKloud DevOps Learning Path](https://kodekloud.com/learning-path/devops) — the path many working DevOps engineers recommend — and adds a free source for every topic, so you can study with or without a subscription. Everything ends in **three real projects** you can put on your CV.

## How this repo is organized

| File | What's in it |
|---|---|
| [ROADMAP.md](ROADMAP.md) | Every topic, in order — with the KodeKloud course, free sources, and hands-on practice for each |
| [PROJECTS.md](PROJECTS.md) | The 3 projects, the skills each one covers, the steps, and how to write them on your CV |
| [CONCEPTS.md](CONCEPTS.md) | What each tool is for, concepts people mix up, CV tips, and interview questions |

## The map

| # | Stage | Main tools | Used in project |
|---|---|---|---|
| 1 | Basics: DevOps, networking, applications | Linux, networking, YAML | 1, 2, 3 |
| 2 | Programming and scripting | Python, Bash | 1 |
| 3 | Version control | Git, GitHub | 1, 2, 3 |
| 4 | Containers | Docker, Docker Compose | 1, 2, 3 |
| 5 | CI/CD | Jenkins, GitHub Actions | 1 |
| 6 | Container orchestration | Kubernetes, Helm | 2 |
| 7 | Cloud | AWS, GCP (Cloud Run) | 2, 3 |
| 8 | Automation | Ansible | 3 |
| 9 | Infrastructure as Code | Terraform | 2, 3 |
| 10 | DevSecOps | gitleaks, Trivy, Dependabot | 1 |
| 11 | Observability | Prometheus, Grafana, Loki | 2, 3 |
| 12 | Interview preparation | — | — |

## The 3 projects

| # | Project | Skills |
|---|---|---|
| 1 | **Secure CI/CD Pipeline (DevSecOps)** | Python, Docker, GitHub Actions, Jenkins, gitleaks, Trivy, Dependabot |
| 2 | **Kubernetes Platform on AWS** ⭐ | Terraform, AWS (VPC, EKS, RDS, IAM), Kubernetes, Helm, autoscaling, Prometheus, Grafana |
| 3 | **AI Gateway with LiteLLM** | Terraform, Ansible, LiteLLM, Grafana, Cloud Run (serverless) |

Details in [PROJECTS.md](PROJECTS.md).

## Choose your pace

| Pace | Time | How |
|---|---|---|
| **Intensive** | ~3 weeks, 4–5 h/day | Learn each topic *while* building the projects — one project per week |
| **Part-time** | ~3 months, 2–3 h/day | Go through [ROADMAP.md](ROADMAP.md) stage by stage, then build the projects |

## How to study

Every day:

1. **Understand (30–45 min):** read or watch the topic — the KodeKloud course or a free source.
2. **Do it (1–3 h):** a lab, or the next step of your project. This is the part that matters.
3. **Write it down (10 min):** what you did, what broke, and how you fixed it. These become your interview stories.

Use AI as a teacher, not a doer: *"I'm following this step — teach me what it does before I run it."*

## Rules

- A topic is done only when you've done it in a terminal and can explain it out loud.
- One project you fully understand beats three you copied.
- Never put anything on your CV that you didn't build yourself — interviewers will ask "how did you create the cluster?"
- **Cloud costs money.** Set a $10 budget alert before anything else, and `terraform destroy` at the end of every session.

## Free practice environments

- [Killercoda](https://killercoda.com/) — real terminals in the browser: Linux, Docker, Kubernetes, Ansible, Terraform
- [Play with Docker](https://labs.play-with-docker.com/)
- [KodeKloud free account](https://kodekloud.com/) — free courses, some labs, and [100 Days of DevOps](https://kodekloud.com/100-days-of-devops)
- Your own laptop: WSL (Ubuntu) + Docker Desktop + kind or minikube

---

Maintained by [@nourseen6](https://github.com/nourseen6). Found a broken link or a better free source? Open an issue or a pull request.
