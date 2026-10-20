# Study guide — the KodeKloud path, for free

The [KodeKloud DevOps Learning Path](https://kodekloud.com/learning-path/devops) shows the course order and the topics of each course for free; only the videos and labs need a subscription. This file follows the same map, topic by topic, with a free place to learn each one and a free place to practice.

## How to use it

For each course:

1. Copy its topic list (below) into a log note as a checklist.
2. Learn each topic from the free source — read or watch for ~45 minutes.
3. Practice it with your own hands for 1–1.5 hours: a lab, Killercoda, or your own machine. This is the part that matters.
4. Tick the topic only when you can explain it out loud and you did it in a terminal.

**Free practice environments**
- [Killercoda](https://killercoda.com/) — real terminals in the browser: Linux, Docker, Kubernetes, Ansible, Terraform. Closest thing to the KodeKloud labs.
- [Play with Docker](https://labs.play-with-docker.com/) — Docker in the browser.
- [KodeKloud free account](https://kodekloud.com/) — some free courses, some labs and playgrounds, and [100 Days of DevOps](https://kodekloud.com/100-days-of-devops).
- Your own laptop: WSL (Ubuntu) + Docker Desktop + kind or minikube.

**Same teachers, free or cheap:** several KodeKloud instructors post full beginner courses on YouTube (search the course name + "KodeKloud" or "freeCodeCamp"), and some KodeKloud courses are also sold on Udemy, often for a few dollars during sales.

---

## 1. DevOps Prerequisite course — 6h 30m

| Topic | Learn (free) | Practice |
|---|---|---|
| Linux basics | [Linux Journey](https://linuxjourney.com/), [Ubuntu command line tutorial](https://ubuntu.com/tutorials/command-line-for-beginners) | [Bandit 0–15](https://overthewire.org/wargames/bandit/) |
| VirtualBox networking, Vagrant | [Vagrant getting started](https://developer.hashicorp.com/vagrant/tutorials/getting-started) | Bring up 2 VMs that ping each other |
| Networking basics, IPs and ports | You know this from CCNA — just review subnets, DNS, ports | `ip a`, `ss -tulpn`, `curl`, `dig` on Linux |
| Programming basics | [Python tutorial](https://docs.python.org/3/tutorial/) | Small scripts in WSL |
| Database basics | [SQLBolt](https://sqlbolt.com/) | Run PostgreSQL in Docker and query it |
| Git | See course 6 | — |
| Apache web server | [Apache getting started](https://httpd.apache.org/docs/2.4/getting-started.html) | Install Apache, serve a page, read its logs |
| SSL & TLS basics | [Cloudflare — what is TLS](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/) | `openssl s_client -connect google.com:443` |
| YAML | [Learn YAML in Y minutes](https://learnxinyminutes.com/yaml/) | Write a YAML file and validate it |

## 2. Fundamentals of DevOps — 2h 30m

Topics: culture, values, crossing team functions, lean, collaboration and information radiation, technology patterns, value of DevOps.

- Learn: [Atlassian — DevOps guides](https://www.atlassian.com/devops), [DORA research](https://dora.dev/)
- No lab — this is theory. Read it once and write a half-page note: "What is DevOps, in my words?"

## 3–5. Programming and scripting

- **Golang — skip** (optional). Python first.
- **Python (recommended):** [Python tutorial](https://docs.python.org/3/tutorial/), [Automate the Boring Stuff](https://automatetheboringstuff.com/)
- **Shell scripts:** [The Linux Command Line](https://linuxcommand.org/tlcl.php) (free book, part 4 is scripting)
- Practice: the 3 scripts in [ROADMAP.md](ROADMAP.md) Week 2.

## 6. Git for Beginners — 1h 15m

| Topic | Learn (free) | Practice |
|---|---|---|
| Fetching and pulling, fork, merge conflicts | [Atlassian Git tutorials](https://www.atlassian.com/git/tutorials), [Pro Git ch. 2–3](https://git-scm.com/book/en/v2) | Fork a repo on GitHub, create a conflict on purpose and fix it |
| Rebasing, interactive rebasing, cherry picking | [Learn Git Branching](https://learngitbranching.js.org/) (all levels) | Same site — it's interactive |
| Resetting and reverting, stashing, reflog | [Pro Git ch. 7](https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection) (Stashing, Reset Demystified) | Break your repo, then recover it with `reflog` |

## 7. Jenkins For Beginners — 4h 20m

| Topic | Learn (free) | Practice |
|---|---|---|
| Basics, setup and interface | [Jenkins — install with Docker](https://www.jenkins.io/doc/book/installing/docker/) | Run Jenkins in Docker on your laptop |
| Extending Jenkins (plugins) | [Managing plugins](https://www.jenkins.io/doc/book/managing/plugins/) | Install the Git and Docker Pipeline plugins |
| Pipelines | [Pipeline docs](https://www.jenkins.io/doc/book/pipeline/), [Jenkins tutorials](https://www.jenkins.io/doc/tutorials/) | A `Jenkinsfile`: build → test → docker build → push |
| Automation and security | [Securing Jenkins](https://www.jenkins.io/doc/book/security/) | Credentials store for your Docker Hub token — never in the Jenkinsfile |

## 8. Docker for Absolute Beginners — 4h

| Topic | Learn (free) | Practice |
|---|---|---|
| Containers, images | [Docker get started](https://docs.docker.com/get-started/), [Docker Curriculum](https://docker-curriculum.com/) | [Play with Docker](https://labs.play-with-docker.com/) |
| Networking | [Docker networking](https://docs.docker.com/engine/network/) | Two containers talking by name on a user network |
| Volumes | [Docker volumes](https://docs.docker.com/engine/storage/volumes/) | A Postgres container whose data survives a restart |
| Container orchestration | [Docker Compose](https://docs.docker.com/compose/) | `docker compose up` for frontend + backend + DB |

## 9. Kubernetes for Beginners — 6h

| Topic | Learn (free) | Practice |
|---|---|---|
| Setting up a local environment | [kind](https://kind.sigs.k8s.io/docs/user/quick-start/) or [minikube](https://minikube.sigs.k8s.io/docs/start/) | Cluster on your laptop |
| Pods, ReplicaSets, Deployments | [Kubernetes basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/), [Workloads](https://kubernetes.io/docs/concepts/workloads/) | [Killercoda Kubernetes](https://killercoda.com/) — delete a pod, watch it come back |
| Services | [Services](https://kubernetes.io/docs/concepts/services-networking/service/) | Expose a Deployment with ClusterIP, then NodePort |

Kubernetes is the most important part — spend the most lab time here.

## 10. Ansible for Beginners — 2h 45m

Topics: setup, inventory, playbooks, modules, variables, conditionals, loops, roles.

- Learn: [Ansible getting started](https://docs.ansible.com/ansible/latest/getting_started/), Jeff Geerling's free *Ansible 101* series on YouTube
- Practice: Killercoda Ansible scenarios, or 2 Vagrant VMs. Build one playbook that uses every topic in the list, then split it into a role.

## 11. Terraform for Beginners — 4h 45m

Topics: basics, state, Terraform with AWS, remote state, provisioners, import, tainting and debugging, modules, functions and conditional expressions.

- Learn: [HashiCorp Terraform tutorials](https://developer.hashicorp.com/terraform/tutorials) — start with *Get Started – AWS*, then *State*, *Modules*, and *Configuration Language*
- Practice: Killercoda Terraform first (free, no AWS bill), then AWS with a $10 budget alert. Always `terraform destroy` at the end.

## 12. Prometheus Certified Associate — 6h 45m (first part only)

Topics: observability fundamentals, Prometheus fundamentals, PromQL, dashboards, application instrumentation, service discovery, push gateway, alerting, monitoring Kubernetes.

- Learn: [Prometheus overview](https://prometheus.io/docs/introduction/overview/), [PromQL basics](https://prometheus.io/docs/prometheus/latest/querying/basics/), [Alerting](https://prometheus.io/docs/alerting/latest/overview/)
- Practice: install the `kube-prometheus-stack` Helm chart on your kind cluster; write 3 PromQL queries and one alert. Skip the mock exam unless you go for the cert.

## 13. Grafana Loki — 55m

Topics: Loki architecture, Promtail, LogQL, Loki in Kubernetes, viewing Kubernetes and app logs, Promtail pipelines.

- Learn: [Grafana Loki docs](https://grafana.com/docs/loki/latest/)
- Note: Promtail has been replaced by **Grafana Alloy** as the log collector. Learn the idea from Promtail, but use Alloy in your own projects.

## 14. DevOps Interview Preparation — 5h 30m

Topics: Linux, Git, Docker, Kubernetes, Helm, HashiCorp, Ansible, Jenkins and CI/CD, AWS, programming, DevOps.

- [devops-exercises](https://github.com/bregman-arie/devops-exercises) — a big free bank of DevOps interview questions on all of these
- The questions in [NOTES.md](NOTES.md#interview-questions)
- Your own [log/](log/) — the errors you fixed are your best interview stories

---

**Not on the KodeKloud map but in my plan:** AWS basics ([AWS Skill Builder](https://skillbuilder.aws/), free), GCP Cloud Run ([Google Cloud Skills Boost](https://www.cloudskillsboost.google/)), Helm ([helm.sh](https://helm.sh/docs/)), Trivy, Dependabot, and LiteLLM — see [ROADMAP.md](ROADMAP.md).
