# Roadmap

A box is checked only when the **Done when** line is true and a file in [log/](log/) links the proof.

---

## Now — through 31 Oct 2026

### Apertus result

- [ ] **P0-apertus** — Finish the Hack Apertus submission.
  - **Why:** This is the secure-AI evidence.
  - **Done when:** The report states one behavior, the paired control, the sample size, and the rate. I can explain the result without opening the raw outputs.
  - **Resources:**
    - [nourseen6/hack-apertus-redteam](https://github.com/nourseen6/hack-apertus-redteam)
    - [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) — labels for the finding, after the measurement exists
  - **CV line, after it is true:** target model, the behavior measured, the control, and the rate.

### Incident Commander on the CV

- [ ] **P0-story** — The CV names the security behavior, and matches the commits that are mine.
  - **Why:** The public repo already describes policy-as-code, fail-closed behavior, auto-revert, and a signed trail.
  - **Done when:** The CV bullet matches those commits only. Any number on the page is one I can walk through.
  - **Resources:**
    - [nourseen6/incident-commander](https://github.com/nourseen6/incident-commander)
    - [Open Policy Agent docs](https://www.openpolicyagent.org/docs/latest/)

---

## Phase 1 — Linux and Git (Nov 2026)

- [ ] **P1-linux** — Use a Linux shell for labs (WSL or a small VM).
  - **Done when:** I can explain users, permissions, processes, SSH keys, and where logs are, on a machine I set up. I can find why a service I started is not listening.
  - **Resources:**
    - [The Linux command line for beginners (Ubuntu)](https://ubuntu.com/tutorials/command-line-for-beginners)
    - [Linux Journey](https://linuxjourney.com/) — paths, permissions, processes, packages
    - [Bandit, levels 0–15](https://overthewire.org/wargames/bandit/) — shell practice. The log records the command I learned.
- [ ] **P1-git** — History I am willing to show.
  - **Done when:** I can branch, commit, revert, and read `git log` / `git diff` on Incident Commander. Each of my commits says what changed.
  - **Resources:**
    - [Pro Git, chapters 1–3](https://git-scm.com/book/en/v2)
    - [GitHub — about Git](https://docs.github.com/en/get-started/using-git/about-git)

**Phase proof:** one log of a Linux problem I diagnosed, plus three commits whose messages say why.

---

## Phase 2 — Secure pipeline (Dec 2026 – Jan 2027)

This lands on Incident Commander, not a new demo app.

- [ ] **P2-docker** — Build and run the existing stack, and explain image vs container, ports, and why the policy engine is a separate container.
  - **Done when:** A clean clone starts, and I can say what fails closed if OPA is down.
  - **Resources:**
    - [Docker — get started](https://docs.docker.com/get-started/)
    - Incident Commander quickstart
- [ ] **P2-actions** — GitHub Actions runs the tests on every push and pull request.
  - **Done when:** A pull request shows a green test check, and the workflow file is in the repo.
  - **Resources:**
    - [Understanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)
- [ ] **P2-scan** — The same workflow fails on a secret and on a known-bad dependency or image, then passes after the fix.
  - **Done when:** There is a red run and a green run. The planted secret never lands on the default branch.
  - **Resources:**
    - [gitleaks](https://github.com/gitleaks/gitleaks)
    - [Trivy](https://trivy.dev/latest/docs/)
    - [Bandit](https://bandit.readthedocs.io/en/latest/) or [Semgrep](https://semgrep.dev/docs/getting-started/)
    - [About secret scanning](https://docs.github.com/en/code-security/secret-scanning/introduction/about-secret-scanning)
- [ ] **P2-name** — Draw the pipeline from commit to deploy and name where each control sits.
  - **Resources:**
    - [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/) — map the stages onto the workflow in a log

**Phase proof:** the red run and the green run.

---

## Phase 3 — Secure AI, written down (Jan – Feb 2027)

- [ ] **P3-llm-map** — Map the Apertus result to one OWASP LLM risk.
  - **Done when:** A short note names the risk, why the test matches it, and what it does not claim.
  - **Resources:** [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/)
- [ ] **P3-sentrix** — One security page for SentriX.
  - **Done when:** The page states the assets, the trust boundaries (device, phone, cellular, cloud), what is authenticated, and what still leaves the device. Every sentence matches the current build.
  - **Resources:**
    - SentriX graduation-project notes
    - [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [ ] **P3-otel** — Connect observability to the automation story.
  - **Done when:** I can trace one Incident Commander incident from a signal to a policy decision, and describe the EJADA Splunk / Dynatrace work in the same terms: signal, question, action.
  - **Resources:** [What is OpenTelemetry?](https://opentelemetry.io/docs/what-is-opentelemetry/)

---

## Phase 4 — One cloud, IAM only (Feb – Mar 2027)

One of AWS or Azure. The second cloud waits until after graduation.

- [ ] **P4-iam** — A personal account with a budget alarm, MFA on the admin identity, and a role that can do one thing.
  - **Done when:** I can show a policy that was too wide, the narrower policy that replaced it, and that no long-lived key is in git.
  - **Resources:**
    - AWS: [IAM best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) and [AWS Cloud Practitioner Essentials](https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/)
    - Azure: [Azure Fundamentals — cloud concepts](https://learn.microsoft.com/en-us/training/paths/microsoft-azure-fundamentals-describe-cloud-concepts/) and [Azure RBAC best practices](https://learn.microsoft.com/en-us/azure/role-based-access-control/best-practices)
- [ ] **P4-exam** — Optional. A practitioner exam only after P4-iam is logged.
  - **Done when:** The badge matches an account I can open and explain.

---

## Phase 5 — Same policy, on Kubernetes (Apr – May 2027)

The cluster adapter already named on Incident Commander. Not a separate tutorial cluster.

- [ ] **P5-k8s** — Run a local cluster and deploy one service from a manifest I wrote.
  - **Done when:** I can explain Pod, Deployment, Service, and what a probe does, on that cluster.
  - **Resources:** [Kubernetes basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [ ] **P5-gate** — One state-changing cluster action is allowed or denied by a policy outside the caller.
  - **Done when:** I can show an allow, a deny, and fail-closed behavior when the policy service is unreachable.
  - **Resources:**
    - [OPA](https://www.openpolicyagent.org/docs/latest/)
    - Existing Rego policies in Incident Commander

---

## Before applications (May – Jun 2027)

- [ ] **P6-cv** — CV, LinkedIn, and this roadmap agree.
  - **Done when:** Each strong line has a repo, a log, or a write-up behind it.
- [ ] **P6-stories** — Three stories, under two minutes each: the pipeline, the policy gate, and the AI measurement or SentriX boundaries.

---

## Foundation

Already done. I log something here only when I go deeper for a real reason.

- FortiGate 7.6 policies, IPS, NAT, VPN, VLANs, FortiManager (DEPI / NTI, 120+ hours) — [lab repo](https://github.com/nourseen6/Fortinet-Device-Management-with-FortiManager)
- Cisco CCNA curriculum completed. Not a CCNA certification.
- EJADA, July 2026: Splunk, Dynatrace, alerting, container monitoring
- Python IDS pipeline and the Packet Tracer enterprise lab — one CV line each

## Later

Not a phase before June 2027:

- Another Packet Tracer topology
- Another generic intrusion-detection classifier
- A second cloud
- A certificate before the IAM lab exists
- Kubernetes, Terraform, or LLM security on the CV before the matching proof above is logged
