# Notes

Reference notes from the advice, so I don't have to re-learn what each thing means.

## What each tool is for

| Tool | What he said | What it is | What I should build |
|---|---|---|---|
| **Jenkins** | "Basic, you need it either way" | CI/CD: every push triggers build, test, and deploy automatically | A `Jenkinsfile` with stages: build → test → docker build → push → deploy |
| **GitHub Actions** | "Same idea as Jenkins" | The same CI/CD, inside GitHub, as a YAML file | At least one workflow in one of my projects |
| **Docker** | Part of every pipeline | Packages the app and everything it needs into a container that runs the same everywhere | Dockerfile, multi-stage build, docker-compose, push to Docker Hub / ECR |
| **Kubernetes** | "Very, very, very important" | Manages many containers: runs them, routes traffic, scales, restarts what fails | Pods, Deployments, Services, Ingress, ConfigMaps/Secrets, and a real EKS cluster |
| **Terraform** | "Essential" — no ClickOps | Infrastructure as Code: write the infra as code, then `terraform init` and `apply` | VPC + EC2 + S3; understand state, modules, remote state |
| **Ansible** | "Also important" | Configuration management: once a VM is up, Ansible installs and configures software on it | A playbook that installs Docker and Nginx on a Terraform VM |
| **Cloud (AWS / GCP)** | "The basics" | The core services and their types | Compute, storage + disk types, networking (VPC, subnets, NAT, VPN, security groups) |
| **Serverless** | "Very popular" — Cloud Run | Runs only when a request comes in, then sleeps, so it costs less than an always-on VM | Deploy a container to Cloud Run or Lambda and compare with EC2 |
| **Prometheus + Grafana** | Monitoring | Prometheus collects metrics, Grafana shows them as dashboards | Install on my cluster; one dashboard and one alert |
| **Trivy + Dependabot** | DevSecOps | Trivy scans Docker images for vulnerabilities; Dependabot scans repo dependencies on every PR | A Trivy stage that fails on CRITICAL; Dependabot on my repos |
| **LiteLLM** | His team is the company's "AI gateway" | Puts every AI provider (OpenAI, Anthropic, Vertex AI, Azure, Bedrock, Mistral) behind one API, with keys, budgets, and observability per user | Deploy with Docker, virtual keys with budgets, one provider — "a good point in the interview" |

**Tasks with no name:** real DevOps work includes things no course covers — e.g. a new NVIDIA DGX machine arrived and the team had to provision it and load models onto it. The skill is to think, read the docs, and write code.

**How the work is done:** "everything by the book." Draw the architecture diagram first: where traffic flows, what's public, what's private.

## Concepts not to mix up

- **Docker** = builds one container for the app.
- **Kubernetes** = manages hundreds of containers across many servers: what runs where, where traffic goes, and replaces anything that fails.
- **Prometheus** = only watches: collects metrics like CPU and request counts. It doesn't run anything.

> Docker is the box. Kubernetes is the warehouse manager who places and runs the boxes. Prometheus is the security cameras.

**EC2 vs Serverless:** EC2 is like a laptop that's always on — you pay even when nothing is running. Cloud Run / Lambda starts when a request arrives and sleeps after, so you pay only for execution time.

## Correct names

The meeting recording had some names wrong. The right ones, so I search for the right thing:

| Heard as | Correct |
|---|---|
| Light LLM | **LiteLLM** |
| Tropic | Anthropic |
| Mestral | Mistral |
| Data Vertex / Vertex | Google Vertex AI |
| "the AWS one" | Amazon Bedrock |
| outdisk | persistent disk |
| VF actions | GitHub Actions |
| DGX 1 | NVIDIA DGX (likely DGX Spark or DGX Station) |
| for stack | full stack |

## CV

**What I already have that counts:** FortiGate and network security work is the same thinking as cloud networking. Write it in cloud terms: VPC, security groups, NAT gateway, VPN.

**What to add:**

1. A **Projects** section with 2–3 projects, each with a full pipeline, a working GitHub link, and a README with an architecture diagram.
2. A **Skills** section grouped like this:
   - **CI/CD:** Jenkins, GitHub Actions
   - **Containers:** Docker, Kubernetes, Helm
   - **IaC:** Terraform, Ansible
   - **Cloud:** AWS (EC2, EKS, S3, RDS, IAM, VPC), GCP (Compute Engine, Cloud Run)
   - **Monitoring:** Prometheus, Grafana
   - **Security:** Trivy, Dependabot, FortiGate
   - **Scripting:** Bash, Python
3. One certification, **optional**: AWS Cloud Practitioner or Terraform Associate.

**How to write a project line (example):**

> Deployed a 3-tier web app (React, Node.js, PostgreSQL) on AWS EKS, provisioned with Terraform; built a Jenkins pipeline that builds Docker images, scans them with Trivy, pushes to ECR and deploys via Helm. Monitored with Prometheus and Grafana.

**Rule:** every line = action + tool + result. Interviewers will ask "how did you create the cluster? how did you connect to it?" — so never write something I didn't build myself.

## Interview questions

- Docker vs Kubernetes — what does each do?
- EC2 vs Cloud Run / Lambda — when would you pick each?
- Why Terraform instead of clicking in the console?
- How do you connect to an EKS cluster? (`aws eks update-kubeconfig`, then `kubectl`)
- What's public and what's private in your 3-tier architecture, and why?
- What happens in your pipeline when Trivy finds a CRITICAL vulnerability?
- What's Terraform state and why keep it remote?
- Walk me through the hardest error you hit in a project and how you fixed it.

## Learning with AI

His method with the EKS blog post: paste the whole post into an LLM and say *"I'm following this blog — teach me each step and explain it before I run it."* Ask it to **teach**, not to do it for me.

Other sources he mentioned: the AI tutor inside KodeKloud, and GitHub itself — when a new tool goes viral, try it on a cluster.

## Links

- [KodeKloud — DevOps Learning Path](https://kodekloud.com/learning-path/devops) — about 15 courses in order: Prerequisites → Git → Jenkins → Docker → Kubernetes → Ansible → Terraform → Prometheus → Grafana Loki → Interview Prep. About 4 months at 2 h/day, or 2–3 months at 4 h/day. Playgrounds and 100 Days are free; full courses are paid (watch for discounts, or share a subscription with a friend).
- [KodeKloud — 100 Days of DevOps](https://kodekloud.com/100-days-of-devops)
- The engineer's LinkedIn post on the 3-tier EKS project (Project 1)
