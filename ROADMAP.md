# Roadmap

A box is checked only when the **Done when** line is true and a note in [log/](log/) links the proof.

Main course source: the [KodeKloud DevOps Learning Path](https://kodekloud.com/learning-path/devops) — the path the engineer followed himself. Its best part is the labs: a real terminal, a task, and room to make mistakes. Don't memorize optional commands; understand the idea and finish the lab.

---

## Phase 1 — Foundations (Weeks 1–2, 19 Oct – 1 Nov)

### Week 1 — Linux, networking, YAML, Git

- [ ] **W1-linux** — Use a Linux shell every day (WSL, a VM, or KodeKloud labs).
  - **Done when:** I can explain users, permissions, processes, services, SSH keys, and where logs live — and find why a service I started isn't listening.
  - **Resources:**
    - KodeKloud: *DevOps Prerequisite Course* (6.5 h)
    - [Linux Journey](https://linuxjourney.com/)
    - [Bandit, levels 0–15](https://overthewire.org/wargames/bandit/) — shell practice
- [ ] **W1-git** — Branch, commit, merge, revert, and read history.
  - **Done when:** I can do a pull request flow on my own repo and every commit message says what changed and why.
  - **Resources:**
    - KodeKloud: *Git for Beginners* (1.25 h)
    - [Pro Git, chapters 1–3](https://git-scm.com/book/en/v2)

### Week 2 — Scripting

- [ ] **W2-bash** — Write three small scripts: a backup, a health check, and a log parser.
  - **Done when:** They're in a repo, each with a usage line, and I can explain every line.
  - **Resources:** KodeKloud: *Shell Scripts for Beginners* (2 h)
- [ ] **W2-python** — Basic Python for automation: files, JSON, HTTP requests, calling CLI tools.
  - **Done when:** One of the three scripts is rewritten in Python.

**Phase proof:** a repo with the scripts, plus one log note about a Linux problem I diagnosed.

---

## Phase 2 — Containers and CI/CD (Weeks 3–4, 2 – 15 Nov)

### Week 3 — Docker

- [ ] **W3-docker** — Containerize an app with a frontend, a backend, and a database.
  - **Done when:** A multi-stage Dockerfile builds a small image, `docker compose up` runs all three services, and the image is pushed to Docker Hub.
  - **Resources:**
    - KodeKloud: *Docker for Absolute Beginners* (4 h)
    - [Docker — get started](https://docs.docker.com/get-started/)

### Week 4 — Jenkins and GitHub Actions

- [ ] **W4-jenkins** — A declarative `Jenkinsfile` with stages: build → test → docker build → push.
  - **Done when:** A push to GitHub triggers the pipeline and a new image appears in the registry.
  - **Resources:**
    - KodeKloud: *Jenkins for Beginners* (4.3 h)
    - [Jenkins pipeline docs](https://www.jenkins.io/doc/book/pipeline/)
- [ ] **W4-actions** — The same pipeline as a GitHub Actions workflow.
  - **Done when:** A pull request shows a green check, and I can say when I'd pick Actions over Jenkins.
  - **Resources:** [Understanding GitHub Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)

**Phase proof:** a green pipeline run and the image in the registry.

---

## Phase 3 — Kubernetes (Weeks 5–6, 16 – 29 Nov) — the most important part

- [ ] **W5-k8s-core** — Pods, Deployments, ReplicaSets, Services, Namespaces.
  - **Done when:** I can deploy the Week 3 app to a local cluster ([kind](https://kind.sigs.k8s.io/) or [minikube](https://minikube.sigs.k8s.io/)), kill a pod, and watch it come back.
  - **Resources:**
    - KodeKloud: *Kubernetes for Beginners* (6 h) + lots of labs
    - [Kubernetes basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [ ] **W6-k8s-config** — ConfigMaps, Secrets, Ingress, probes, resource limits.
  - **Done when:** The frontend is reachable through an Ingress, the backend and DB are not reachable from outside, and config comes from a ConfigMap/Secret.
- [ ] **W6-helm** — Package the app as a Helm chart.
  - **Done when:** `helm install` deploys the whole app.
  - **Resources:** [Helm docs](https://helm.sh/docs/)

**Phase proof:** manifests + Helm chart in a repo, and a screenshot of `kubectl get all`.

---

## Phase 4 — Cloud and Infrastructure as Code (Weeks 7–8, 30 Nov – 13 Dec)

### Week 7 — AWS and GCP basics

**Before anything:** create a budget alert of $10 and turn on MFA. ([AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html))

- [ ] **W7-aws** — The basics he called "must know":
  - **Compute:** EC2 and instance types
  - **Storage:** S3 buckets; disk types (HDD, SSD, gp3)
  - **Networking:** VPC, public/private subnets, NAT gateway, VPN, security groups
  - **Identity:** IAM users, roles, least-privilege policies
  - **Database:** RDS
  - **Done when:** I've created a VM and a bucket by hand and can draw the VPC they sit in.
  - **Resources:** KodeKloud AWS playground; [AWS Cloud Practitioner Essentials](https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/)
- [ ] **W7-serverless** — Deploy a container to GCP Cloud Run (or AWS Lambda).
  - **Done when:** It answers a request from a public URL, and I can explain the cost difference vs. EC2.
  - **Resources:** [Cloud Run docs](https://cloud.google.com/run/docs)

### Week 8 — Terraform

- [ ] **W8-terraform** — VPC + EC2 + S3 written in Terraform. No ClickOps.
  - **Done when:** `terraform apply` builds it, `terraform destroy` removes it, state lives in a remote backend (S3), and I've used at least one module.
  - **Resources:**
    - KodeKloud: *Terraform for Beginners* (4.75 h)
    - [Terraform AWS tutorials](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)

**Phase proof:** the Terraform repo and a log note of the `plan` output.

---

## Phase 5 — The three projects (Weeks 9–11, 14 Dec – 3 Jan)

Every project repo needs: a README with an **architecture diagram**, steps to run it, screenshots, what I learned, and the problems I hit.

### Week 9 — Project 1: 3-tier app on AWS EKS

The project the engineer built himself.

- [ ] **P1-eks** — Architecture:
  - **Frontend:** 2 pods
  - **Backend:** 2 pods; the frontend calls it through an internal API
  - **Database:** AWS RDS (PostgreSQL); only the backend can reach it
  - **From outside:** a Load Balancer / Ingress reaches the frontend only. Backend and DB stay private.
  - **Steps:** create the cluster with Terraform → choose the node count → connect with `aws eks update-kubeconfig` and `kubectl` → create RDS → deploy frontend and backend → test the routing → destroy everything.
  - **Done when:** The repo is complete and I can answer "how did you create the cluster? how did you connect to it?"
  - **Cost warning:** EKS is billed by the hour even when idle. Build it over 2–3 days and run `terraform destroy` at the end of every day.

### Week 10 — Ansible + Project 2: DevSecOps pipeline

- [ ] **W10-ansible** — A playbook that installs Docker and Nginx on a VM created with Terraform.
  - **Resources:** KodeKloud: *Ansible for Beginners* (2.75 h); [Ansible docs](https://docs.ansible.com/)
- [ ] **P2-devsecops** — Pipeline:
  1. Jenkins (or GitHub Actions) pulls the code from GitHub
  2. Docker builds the image
  3. **Trivy** scans the image — the pipeline **fails on CRITICAL**
  4. Push the image to ECR or Docker Hub
  5. Deploy to the Project 1 cluster
  6. **Dependabot** is on and opens PRs for outdated dependencies
  - **Done when:** There is a red run (a planted vulnerable image) and a green run after the fix.
  - **Optional:** SonarQube for code analysis; gitleaks for secrets.
  - **Resources:** [Trivy](https://trivy.dev/latest/docs/), [Dependabot](https://docs.github.com/en/code-security/dependabot)

### Week 11 — Monitoring + Project 3: LLM gateway with LiteLLM

- [ ] **W11-monitoring** — Install Prometheus and Grafana on my cluster.
  - **Done when:** One dashboard and one alert that I triggered on purpose.
  - **Resources:** KodeKloud: *Prometheus Certified Associate* (first part only) + *Grafana Loki*; [Prometheus](https://prometheus.io/docs/introduction/overview/), [Grafana](https://grafana.com/docs/grafana/latest/)
- [ ] **P3-litellm** — An LLM gateway, like the one his team runs:
  - Deploy the LiteLLM proxy with Docker on a VM or Cloud Run
  - Connect one or two providers (some have a free tier)
  - Create a virtual key per "user", each with a budget
  - Turn on logging and show usage in Grafana
  - All infrastructure in Terraform
  - **Done when:** A request over budget is rejected, and the dashboard shows usage per key.
  - **Resources:** [LiteLLM docs](https://docs.litellm.ai/)

---

## Phase 6 — CV and referral (Week 12, 4 – 10 Jan)

- [ ] **W12-cv** — Update the CV using the rules in [NOTES.md](NOTES.md#cv).
- [ ] **W12-interview** — KodeKloud: *DevOps Interview Preparation* (5.5 h), plus the questions in [NOTES.md](NOTES.md#interview-questions).
- [ ] **W12-cert** — Optional, only if time allows: AWS Cloud Practitioner or Terraform Associate. Not required for the referral.

### Checklist before sending the CV

- [ ] Project 1 (EKS) on GitHub and working, with README and diagram
- [ ] Project 2 (DevSecOps) with Trivy and Dependabot
- [ ] Project 3 (LiteLLM), or at least a simple version of it
- [ ] I can explain each project in 2 minutes: the problem, the architecture, the tools, and the hardest error
- [ ] I can answer: Docker vs Kubernetes? EC2 vs Cloud Run? Why Terraform instead of the console? How do you connect to a cluster?
- [ ] The CV is one page, skills are grouped, every project has a link
- [ ] A short message to the engineer: thanks for the meeting, what I built from his advice, the project links, and whether there's an open position he could refer me to

---

## Later — not before the referral

- Golang (optional in the KodeKloud path — Python first)
- A second certification
- Advanced Kubernetes (operators, service mesh)
