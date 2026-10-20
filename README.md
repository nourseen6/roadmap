# DevOps Roadmap

My plan to become job-ready as a DevOps engineer , Computer science student, graduating June 2027.
*The learning journey never really ends. There’s always something new to learn, another skill to build, and another way to grow. 🚀✨*

**Goal:** learn the core tools hands-on, build three real projects on GitHub, put them on my CV with the right keywords, in about 3 weeks (19 Oct 2026 → 19 Jan 2027), at 4–5 hours a day.

**Rule:** an item is done only when there is proof — a repo, a pipeline run, or a screenshot — and I can explain it without notes.

## Where to look

| File | What's in it |
|---|---|
| [ROADMAP.md](ROADMAP.md) | The week-by-week plan: checklists, resources, and the "done when" test for each item |
| [NOTES.md](NOTES.md) | What each tool is for, concepts I must not mix up, CV rules, interview questions |
| [log/](log/) | One note per study session, with the proof |

## Priorities

1. **Must have:** Linux + Git, Docker, **Kubernetes** (he said "very, very, very important"), Terraform, Jenkins, Cloud (AWS first, then GCP)
2. **Important:** GitHub Actions, Ansible, Serverless (Cloud Run / Lambda)
3. **What makes me stand out:** DevSecOps (Trivy, Dependabot), Monitoring (Prometheus + Grafana), MLOps / LiteLLM (the work his team actually does)

Plus, always: **write code** (Python and Bash, using AI to go faster), and **draw the architecture before building anything** — where traffic comes from, where it goes, what is public and what is private.

## The 12 weeks at a glance

| Week | Dates | Focus | Output |
|---|---|---|---|
| 1 | 19 – 25 Oct | Linux, networking, YAML, Git | Daily Linux labs, a clean GitHub repo |
| 2 | 26 Oct – 1 Nov | Bash + basic Python | 3 small scripts |
| 3 | 2 – 8 Nov | Docker | Multi-stage Dockerfile + docker-compose app |
| 4 | 9 – 15 Nov | CI/CD: Jenkins + GitHub Actions | Pipeline that builds and pushes an image |
| 5–6 | 16 – 29 Nov | **Kubernetes** | App running on a local cluster |
| 7 | 30 Nov – 6 Dec | AWS + GCP basics | VM, bucket, and a Cloud Run service |
| 8 | 7 – 13 Dec | Terraform | VPC + EC2 + S3 as code, remote state |
| 9 | 14 – 20 Dec | **Project 1:** 3-tier app on AWS EKS | Repo with README + diagram |
| 10 | 21 – 27 Dec | Ansible + **Project 2:** DevSecOps pipeline | Pipeline with Trivy + Dependabot |
| 11 | 28 Dec – 3 Jan | Prometheus + Grafana + **Project 3:** LiteLLM gateway | Dashboard + LLM gateway |
| 12 | 4 – 10 Jan | CV + interview prep | New CV sent to the engineer |

More time some weeks? Merge two weeks into one — the whole plan fits in 6 weeks at full speed.

## The three projects

| # | Project | Why |
|---|---|---|
| 1 | **3-tier app on AWS EKS** — frontend, backend, RDS, Terraform | The project he built himself; covers Kubernetes, AWS, and IaC |
| 2 | **DevSecOps pipeline** — Jenkins/Actions, Docker, Trivy, Dependabot | Builds on my network-security background |
| 3 | **LLM gateway with LiteLLM** — virtual keys, budgets, Grafana | Exactly what his team does; the strongest CV line for this role |

## Every week, alongside the courses

- [ ] One task a day from the free [KodeKloud 100 Days of DevOps](https://kodekloud.com/100-days-of-devops) challenge
- [ ] Every error I hit and how I fixed it goes into [log/](log/) — this is what interviews ask about
- [ ] A short update to the engineer every two weeks: "I finished X, here's the repo"

## Already in place

- [Incident Commander](https://github.com/nourseen6/incident-commander) — incident response with an external policy check, auto-revert, and a signed trail (a good app to run Project 2's pipeline on)
- [Hack Apertus red team](https://github.com/nourseen6/hack-apertus-redteam) — controlled test of one published model
- SentriX — graduation project, on-device risk detection and secure alerts
- EJADA, July 2026 — Splunk, Dynatrace, alerting, container monitoring
- DEPI / NTI — FortiGate, FortiManager, and the CCNA curriculum ([lab notes](https://github.com/nourseen6/Fortinet-Device-Management-with-FortiManager))
