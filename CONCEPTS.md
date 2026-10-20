# Concepts

Quick reference: what each tool is for, the ideas beginners mix up, how to write your CV, and what interviews ask.

## What each tool is for

| Tool | What it is | In one line |
|---|---|---|
| **Git / GitHub** | Version control | Every change to code and infrastructure is tracked and reviewable |
| **Docker** | Containers | Packages an app and everything it needs so it runs the same everywhere |
| **Jenkins** | CI/CD server | Every push triggers build, test, and deploy automatically |
| **GitHub Actions** | CI/CD inside GitHub | The same idea as Jenkins, defined in a YAML file in the repo |
| **Kubernetes** | Container orchestration | Runs many containers across many servers: scheduling, traffic, scaling, self-healing |
| **Helm** | Kubernetes package manager | Installs a whole app on Kubernetes with one command |
| **Terraform** | Infrastructure as Code | Write the infrastructure as code instead of clicking in the console ("no ClickOps") |
| **Ansible** | Configuration management | Once a server exists, installs and configures software on it |
| **AWS / GCP** | Cloud | Compute, storage, networking, and managed services you rent by the hour |
| **Serverless** (Cloud Run, Lambda) | Run on demand | Starts when a request arrives and sleeps after — you pay only for execution |
| **Prometheus** | Metrics | Collects numbers like CPU and request counts |
| **Grafana** | Dashboards | Shows those metrics as graphs and sends alerts |
| **Loki** | Logs | Stores and searches logs, viewed in Grafana |
| **Trivy** | Image scanner | Finds known vulnerabilities in Docker images |
| **Dependabot** | Dependency scanner | Opens pull requests when a dependency is outdated or vulnerable |
| **gitleaks** | Secret scanner | Catches passwords and API keys before they reach Git |
| **LiteLLM** | AI gateway | Puts many AI providers behind one API, with keys, budgets, and logs per user |

## Concepts people mix up

**Docker vs Kubernetes vs Prometheus**
- **Docker** builds and runs *one* container.
- **Kubernetes** manages *hundreds* of containers across many servers: what runs where, where traffic goes, and replaces anything that fails.
- **Prometheus** only *watches*: it collects metrics. It doesn't run anything.

> Docker is the box. Kubernetes is the warehouse manager who places and runs the boxes. Prometheus is the security cameras.

**EC2 vs Serverless:** EC2 is like a laptop that's always on — you pay even when nothing is running. Cloud Run / Lambda starts when a request arrives and sleeps after, so you pay only for the time it runs.

**Terraform vs Ansible:** Terraform *creates* the infrastructure (the VPC, the VM). Ansible *configures* what's inside it (installs Docker, edits config files).

**Jenkins vs GitHub Actions:** the same job. Jenkins is a server you run and control; GitHub Actions runs inside GitHub with nothing to host.

**Image vs container:** an image is the template; a container is a running copy of it.

**Public vs private subnet:** a public subnet has a route to the internet; a private subnet doesn't, and reaches out only through a NAT gateway. Databases and backends belong in private subnets.

## How DevOps work is done

- **Draw before you build.** An architecture diagram first: where traffic comes from, where it goes, what's public, what's private.
- **Everything as code.** If you clicked it in a console, it doesn't exist.
- **Not everything is in a course.** Real tasks (say, setting up a new GPU server and loading AI models on it) have no tutorial. The skill is reading docs, thinking, and writing code.

## CV

**Skills section — group it:**
- **CI/CD:** Jenkins, GitHub Actions
- **Containers:** Docker, Kubernetes, Helm
- **IaC:** Terraform, Ansible
- **Cloud:** AWS (EC2, EKS, S3, RDS, IAM, VPC), GCP (Cloud Run)
- **Monitoring:** Prometheus, Grafana, Loki
- **Security:** Trivy, Dependabot, gitleaks
- **Scripting:** Bash, Python

**Projects section:** 2–3 projects, each with a working GitHub link and a README with a diagram.

**Every line = action + tool + result.** Numbers make it stronger:

> Reduced the Docker image from 900 MB to 120 MB with a multi-stage build; the pipeline blocks images with critical vulnerabilities.

**Never write something you didn't build.** Interviewers will ask: "How did you create the cluster? How did you connect to it?"

**Certifications are optional.** A working project beats a badge. If you have time: AWS Cloud Practitioner or Terraform Associate.

## Interview questions

- Docker vs Kubernetes — what does each do?
- EC2 vs Cloud Run / Lambda — when would you pick each?
- Why Terraform instead of clicking in the console?
- What is Terraform state, and why keep it remote?
- Terraform vs Ansible?
- How do you connect to an EKS cluster? (`aws eks update-kubeconfig`, then `kubectl`)
- What's a Pod, a Deployment, a Service, an Ingress?
- What's public and what's private in your architecture, and why?
- What happens in your pipeline when Trivy finds a critical vulnerability?
- How do you keep secrets out of Git?
- Walk me through the hardest error you hit and how you fixed it.

More: [devops-exercises](https://github.com/bregman-arie/devops-exercises).

## Learning with AI

Paste a tutorial or blog post into an AI assistant and say: *"I'm following this — teach me each step and explain it before I run it."* Ask it to **teach** you, not to do it for you.

When a new DevOps tool goes viral on GitHub, try it on your own cluster.
