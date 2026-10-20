# Projects

Three projects that together cover every stage of the [roadmap](ROADMAP.md). Each one is strong enough to be its own line on a CV.

Build them in order — each one uses what you learned in the one before.

| # | Project | Stages covered |
|---|---|---|
| 1 | [Secure CI/CD Pipeline](#project-1--secure-cicd-pipeline-devsecops) | 1, 2, 3, 4, 5, 10 |
| 2 | [Kubernetes Platform on AWS](#project-2--kubernetes-platform-on-aws-) ⭐ | 4, 6, 7, 9, 11 |
| 3 | [AI Gateway with LiteLLM](#project-3--ai-gateway-with-litellm) | 7, 8, 9, 11 |

**For every project:** its own GitHub repo with a README that has an **architecture diagram**, how to run it, screenshots, what you learned, and the problems you hit. Draw the diagram *before* you build: where traffic comes from, where it goes, what's public and what's private.

---

## Project 1 — Secure CI/CD Pipeline (DevSecOps)

**The idea:** every push goes through a pipeline that checks security automatically before anything ships.

**Why it's strong:** software supply-chain security is one of the most in-demand skills right now, and most beginner pipelines don't check anything.

### Skills

| Area | Tools |
|---|---|
| Code | Python, Bash, Git |
| Containers | Docker (multi-stage), Docker Compose |
| CI/CD | GitHub Actions, Jenkins |
| Security | gitleaks, Trivy, Dependabot |

### Steps

1. Write a small Python API (for example, a URL shortener) with a Postgres database. Keep it simple — the app is not the point.
2. Write a multi-stage Dockerfile and a `docker-compose.yml` for the app + database.
3. GitHub Actions workflow: test → **gitleaks** → build → **Trivy** scan → push to Docker Hub.
4. Make the pipeline **fail on CRITICAL vulnerabilities** and on any leaked secret.
5. Turn on **Dependabot** for the repo.
6. Rebuild the same pipeline as a `Jenkinsfile`, with Jenkins running in Docker and the registry token in Jenkins credentials.

### Done when

- One push builds, scans, and pushes the image automatically.
- You have a **red run** (a planted secret or vulnerable image) and a **green run** after the fix.

### Stand out

- Show the image size before and after the multi-stage build.
- Generate an SBOM with Trivy and keep it as a build artifact.

### CV line

> Built a DevSecOps pipeline (GitHub Actions + Jenkins) with secret scanning (gitleaks), image scanning (Trivy), and automated dependency updates (Dependabot); builds fail automatically on critical vulnerabilities.

---

## Project 2 — Kubernetes Platform on AWS ⭐

**The idea:** a real Kubernetes cluster on AWS, created entirely from code, running a 3-tier app, and monitored.

**Why it's strong:** this is the main project. It has the most requested keywords in DevOps job posts — Kubernetes, Terraform, AWS — and it's the one interviewers ask the most about.

### Skills

| Area | Tools |
|---|---|
| Infrastructure as Code | Terraform (modules, remote state) |
| Cloud | AWS VPC, EKS, RDS, IAM, ECR |
| Kubernetes | Deployments, Services, Ingress, ConfigMaps, Secrets, probes, HPA |
| Packaging | Helm |
| Observability | Prometheus, Grafana |

### Architecture

- **Frontend:** 2 pods, the only public part, behind a Load Balancer / Ingress
- **Backend:** 2 pods, private; the frontend calls it through an internal Service
- **Database:** AWS RDS (PostgreSQL), private; only the backend can reach it

### Steps

1. **First on kind** (local, free): deploy the Project 1 app with Deployments, Services, ConfigMaps, Secrets, and an Ingress.
2. Package it as a **Helm chart**.
3. **Terraform:** VPC (public and private subnets) + EKS + RDS, using modules, with state in S3.
4. Connect: `aws eks update-kubeconfig`, then `kubectl get nodes`.
5. `helm install` the app on EKS. Test that the frontend is public and the backend and database are not.
6. Install `kube-prometheus-stack`: one dashboard and one alert.
7. Add an **HPA**, run a load test, and watch the pods scale up.
8. `terraform destroy`.

### Done when

- You can explain, without notes: how you created the cluster, how you connected to it, and what's public vs private and why.

### Stand out

- Kubernetes **NetworkPolicies**: only the frontend can talk to the backend — like firewall rules inside the cluster.
- A rolling update and a rollback with zero downtime.
- Have the Project 1 pipeline deploy here with `helm upgrade`.

### ⚠️ Cost

EKS, NAT gateways, and RDS are billed by the hour, even when idle. Build it over 2–3 days and run `terraform destroy` at the end of every day.

### CV line

> Provisioned an AWS EKS cluster and RDS with Terraform; deployed a 3-tier app with Helm, private backend and database, autoscaling under load (HPA), and Prometheus/Grafana monitoring.

---

## Project 3 — AI Gateway with LiteLLM

**The idea:** one gateway in front of many AI models (OpenAI, Anthropic, Gemini, and others), with an API key and a budget for each user — the kind of platform DevOps and MLOps teams run for their companies.

**Why it's strong:** few juniors have built one, and it connects DevOps to AI — where a lot of new DevOps work is.

### Skills

| Area | Tools |
|---|---|
| Infrastructure as Code | Terraform |
| Configuration management | Ansible (playbooks, roles) |
| Platform | LiteLLM proxy, Docker |
| Cloud | AWS EC2, GCP Cloud Run (serverless) |
| Observability | Grafana |

### Steps

1. **Terraform:** a VPC and an EC2 instance.
2. **Ansible:** a role that installs Docker and runs the LiteLLM proxy on that EC2.
3. Connect one or two model providers (some have a free tier).
4. Create a **virtual key per user**, each with its own budget.
5. Show usage and cost per key in **Grafana**.
6. Deploy the same gateway to **Cloud Run** and compare cost and setup with EC2.

### Done when

- A request over a user's budget is rejected.
- The dashboard shows usage per key.

### Stand out

- No SSH: the EC2 is in a private subnet and you reach it through AWS Systems Manager.
- Provider API keys live in a secrets manager, never in Git.

### CV line

> Deployed an LLM gateway (LiteLLM) with per-user API keys and budgets; infrastructure with Terraform and Ansible, usage dashboards in Grafana, and a serverless version on Cloud Run.

---

## Timeline

| Pace | Project 1 | Project 2 | Project 3 |
|---|---|---|---|
| Intensive (4–5 h/day) | Week 1 | Week 2 | Week 3 |
| Part-time (2–3 h/day) | After roadmap stages 1–5 and 10 | After stages 6, 7, 9 | After stages 8 and 11 |
