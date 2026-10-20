# Roadmap

Every topic, in order. For each stage:

- ⭐ **KodeKloud** — the main course, from the [KodeKloud DevOps Learning Path](https://kodekloud.com/learning-path/devops). The topic lists below are the course's own topics. Videos and labs need a subscription; some courses are free with a free account.
- 🆓 **Free** — learn the same topics without a subscription.
- 🛠️ **Practice** — do it with your own hands. Don't skip this.

Tick a topic only when you've done it in a terminal and can explain it.

---

## 1. Basics: DevOps, networking, applications

⭐ **KodeKloud:** *DevOps Prerequisite Course* (6h 30m) + *Fundamentals of DevOps* (2h 30m)

**Topics**
- [ ] Linux basics
- [ ] VirtualBox networking, Vagrant
- [ ] Networking basics, IPs and ports
- [ ] Programming basics
- [ ] Database basics
- [ ] Apache web server
- [ ] SSL & TLS basics
- [ ] YAML
- [ ] DevOps culture, lean, collaboration, value of DevOps

🆓 **Free**
- [Linux Journey](https://linuxjourney.com/), [Ubuntu command line tutorial](https://ubuntu.com/tutorials/command-line-for-beginners)
- [Vagrant getting started](https://developer.hashicorp.com/vagrant/tutorials/getting-started)
- [SQLBolt](https://sqlbolt.com/) — databases
- [Apache getting started](https://httpd.apache.org/docs/2.4/getting-started.html)
- [Cloudflare — what is TLS](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/)
- [Learn YAML in Y minutes](https://learnxinyminutes.com/yaml/)
- [Atlassian — DevOps guides](https://www.atlassian.com/devops), [DORA research](https://dora.dev/)

🛠️ **Practice**
- [Bandit, levels 0–15](https://overthewire.org/wargames/bandit/)
- Install Apache, serve a page, read its logs, find why it isn't listening
- `ip a`, `ss -tulpn`, `curl`, `dig`, `openssl s_client -connect google.com:443`

---

## 2. Programming and scripting

⭐ **KodeKloud:** *Certified Python Entry-Level Programmer* (1h 30m, recommended) + *Shell Scripts for Beginners* (2h). *Golang* (4h 15m) is optional — start with Python.

**Topics**
- [ ] Python: variables, functions, files, JSON, HTTP requests
- [ ] Bash: variables, conditions, loops, functions, exit codes

🆓 **Free**
- [Python tutorial](https://docs.python.org/3/tutorial/), [Automate the Boring Stuff](https://automatetheboringstuff.com/)
- [The Linux Command Line](https://linuxcommand.org/tlcl.php) — free book, part 4 is scripting

🛠️ **Practice**
- Three small scripts: a backup, a health check, a log parser. Rewrite one in Python.

---

## 3. Version control

⭐ **KodeKloud:** *Git for Beginners* (1h 15m)

**Topics**
- [ ] Fetching and pulling, fork
- [ ] Merge conflicts
- [ ] Rebasing, interactive rebasing
- [ ] Cherry picking
- [ ] Resetting and reverting, stashing, reflog

🆓 **Free**
- [Atlassian Git tutorials](https://www.atlassian.com/git/tutorials)
- [Pro Git](https://git-scm.com/book/en/v2) — chapters 2, 3, and 7

🛠️ **Practice**
- [Learn Git Branching](https://learngitbranching.js.org/) — all levels
- Create a merge conflict on purpose and fix it. Break your repo and recover it with `git reflog`.

---

## 4. Containers

⭐ **KodeKloud:** *Docker for Absolute Beginners* (4h)

**Topics**
- [ ] Containers and images
- [ ] Dockerfile, multi-stage builds
- [ ] Networking
- [ ] Volumes
- [ ] Docker Compose
- [ ] Registries (Docker Hub, Amazon ECR)

🆓 **Free**
- [Docker — get started](https://docs.docker.com/get-started/), [Docker Curriculum](https://docker-curriculum.com/)
- [Docker networking](https://docs.docker.com/engine/network/), [Docker volumes](https://docs.docker.com/engine/storage/volumes/), [Docker Compose](https://docs.docker.com/compose/)

🛠️ **Practice**
- [Play with Docker](https://labs.play-with-docker.com/)
- A Postgres container whose data survives a restart
- `docker compose up` for a frontend + backend + database

---

## 5. CI/CD

⭐ **KodeKloud:** *Jenkins For Beginners* (4h 20m)

**Topics**
- [ ] Jenkins basics, setup and interface
- [ ] Extending Jenkins (plugins)
- [ ] Jenkins pipelines (`Jenkinsfile`)
- [ ] Automation and security (credentials)
- [ ] GitHub Actions: workflows, jobs, steps, secrets

🆓 **Free**
- [Jenkins — install with Docker](https://www.jenkins.io/doc/book/installing/docker/), [Pipeline docs](https://www.jenkins.io/doc/book/pipeline/), [Jenkins tutorials](https://www.jenkins.io/doc/tutorials/), [Securing Jenkins](https://www.jenkins.io/doc/book/security/)
- [Understanding GitHub Actions](https://docs.github.com/en/actions/about-github-actions/understanding-github-actions)

🛠️ **Practice**
- Run Jenkins in Docker. Write a pipeline: build → test → docker build → push.
- The same pipeline as a GitHub Actions workflow.

---

## 6. Container orchestration

⭐ **KodeKloud:** *Kubernetes for Beginners* (6h) — the most important stage. Spend the most lab time here.

**Topics**
- [ ] Setting up a local environment
- [ ] Pods, ReplicaSets, Deployments
- [ ] Services
- [ ] ConfigMaps and Secrets
- [ ] Ingress
- [ ] Probes and resource limits
- [ ] Autoscaling (HPA)
- [ ] Helm

🆓 **Free**
- [Kubernetes basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/), [Workloads](https://kubernetes.io/docs/concepts/workloads/), [Services](https://kubernetes.io/docs/concepts/services-networking/service/)
- [Helm docs](https://helm.sh/docs/)

🛠️ **Practice**
- A local cluster with [kind](https://kind.sigs.k8s.io/docs/user/quick-start/) or [minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Killercoda Kubernetes](https://killercoda.com/) scenarios
- Delete a pod and watch it come back. Expose a Deployment with a Service, then an Ingress.

---

## 7. Cloud

⭐ **KodeKloud:** AWS courses and playgrounds (not part of the DevOps path itself)

**Topics**
- [ ] Compute: EC2 and instance types
- [ ] Storage: S3; disk types (HDD, SSD, gp3)
- [ ] Networking: VPC, public and private subnets, NAT gateway, VPN, security groups
- [ ] Identity: IAM users, roles, least-privilege policies
- [ ] Databases: RDS
- [ ] Kubernetes: EKS
- [ ] Serverless: GCP Cloud Run or AWS Lambda — and when it's cheaper than a VM

🆓 **Free**
- [AWS Skill Builder](https://skillbuilder.aws/) — *AWS Cloud Practitioner Essentials*
- [IAM best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)
- [Google Cloud Skills Boost](https://www.cloudskillsboost.google/), [Cloud Run docs](https://cloud.google.com/run/docs)

🛠️ **Practice**
- **First:** a $10 [budget alert](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html) and MFA on your account
- Create a VM and a bucket by hand, then draw the VPC they live in
- Deploy one container to Cloud Run

---

## 8. Automation

⭐ **KodeKloud:** *Ansible for Beginners* (2h 45m)

**Topics**
- [ ] Setup, inventory
- [ ] Playbooks, modules
- [ ] Variables, conditionals, loops
- [ ] Roles

🆓 **Free**
- [Ansible getting started](https://docs.ansible.com/ansible/latest/getting_started/)
- Jeff Geerling's *Ansible 101* series on YouTube

🛠️ **Practice**
- Killercoda Ansible scenarios, or two Vagrant VMs
- One playbook that uses every topic above, then split it into a role

---

## 9. Infrastructure as Code

⭐ **KodeKloud:** *Terraform for Beginners* (4h 45m)

**Topics**
- [ ] Terraform basics: `init`, `plan`, `apply`, `destroy`
- [ ] Terraform state, remote state
- [ ] Terraform with AWS
- [ ] Provisioners
- [ ] Import
- [ ] Tainting resources and debugging
- [ ] Modules
- [ ] Functions and conditional expressions

🆓 **Free**
- [HashiCorp Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials) — *Get Started – AWS*, then *State*, *Modules*, and *Configuration Language*

🛠️ **Practice**
- Killercoda Terraform first (no cloud bill), then AWS
- VPC + EC2 + S3 in Terraform, with state in S3. `terraform destroy` at the end of every session.

---

## 10. DevSecOps

Not a separate KodeKloud course — learn it inside the pipeline.

**Topics**
- [ ] Secret scanning (gitleaks)
- [ ] Image scanning (Trivy) — fail the build on CRITICAL
- [ ] Dependency scanning (Dependabot)
- [ ] Least-privilege IAM, no secrets in Git

🆓 **Free**
- [gitleaks](https://github.com/gitleaks/gitleaks), [Trivy docs](https://trivy.dev/latest/docs/), [Dependabot](https://docs.github.com/en/code-security/dependabot)
- [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/)

🛠️ **Practice**
- Plant a fake secret and a vulnerable image, watch the pipeline go red, fix it, watch it go green.

---

## 11. Observability

⭐ **KodeKloud:** *Prometheus Certified Associate* (6h 45m — the first part is enough unless you want the cert) + *Grafana Loki* (55m)

**Topics**
- [ ] Observability fundamentals
- [ ] Prometheus fundamentals, PromQL
- [ ] Dashboards and visualization (Grafana)
- [ ] Application instrumentation
- [ ] Service discovery, push gateway
- [ ] Alerting
- [ ] Monitoring Kubernetes
- [ ] Loki: architecture, LogQL, viewing Kubernetes and app logs

🆓 **Free**
- [Prometheus overview](https://prometheus.io/docs/introduction/overview/), [PromQL basics](https://prometheus.io/docs/prometheus/latest/querying/basics/), [Alerting](https://prometheus.io/docs/alerting/latest/overview/)
- [Grafana docs](https://grafana.com/docs/grafana/latest/), [Grafana Loki docs](https://grafana.com/docs/loki/latest/)
- Note: Promtail (in the course) has been replaced by **Grafana Alloy** as the log collector. Learn the idea, use Alloy in your projects.

🛠️ **Practice**
- Install the `kube-prometheus-stack` Helm chart on a kind cluster. Write 3 PromQL queries and trigger one alert on purpose.

---

## 12. Interview preparation

⭐ **KodeKloud:** *DevOps Interview Preparation Course* (5h 30m) — Linux, Git, Docker, Kubernetes, Helm, HashiCorp, Ansible, Jenkins and CI/CD, AWS, programming

🆓 **Free**
- [devops-exercises](https://github.com/bregman-arie/devops-exercises) — a big free bank of DevOps interview questions
- The questions in [CONCEPTS.md](CONCEPTS.md#interview-questions)

🛠️ **Practice**
- Explain each of your projects in 2 minutes: the problem, the architecture, the tools, and the hardest error you hit.

---

## Later

- Golang
- A certification: AWS Cloud Practitioner, Terraform Associate, or CKA
- GitOps (Argo CD), service mesh, Kubernetes operators
