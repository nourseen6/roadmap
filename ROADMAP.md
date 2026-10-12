# Roadmap

Check a box only when the **Done when** line is true and a log file links the proof.

Legend: `[ ]` not done · `[x]` done, with a log.

---

## Now — close the open work (through 31 Oct 2026)

### Apertus result

- [ ] **P0-apertus** — Finish the Hack Apertus submission.
  - **Why:** This is the secure-AI evidence. A finished measurement beats another model tutorial.
  - **Done when:** The report states one behavior, the paired control, the sample size, and the rate. You can explain the result without opening the raw outputs.
  - **Start here:**
    - Your repo: [nourseen6/hack-apertus-redteam](https://github.com/nourseen6/hack-apertus-redteam)
    - [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) — use the names only to label the finding, after the measurement exists
  - **CV line, after it is true:** target model, the behavior you measured, the control, and the rate.
  - **Interview sentence:** "I tested one unmeasured path in a published model, against a control, and I can show the rate."

### Make GitHub match the work

- [ ] **P0-story** — Incident Commander readme and your CV name the security behavior, not "contributed to the codebase."
  - **Why:** The public repo already describes policy-as-code, fail-closed behavior, auto-revert, and a signed trail. The CV hides that.
  - **Done when:** You can point to the commits that are yours, and the CV bullet matches only those commits. You can walk through any number you leave on the page (including the trial harness, if you claim it).
  - **Start here:**
    - [nourseen6/incident-commander](https://github.com/nourseen6/incident-commander)
    - [Open Policy Agent docs](https://www.openpolicyagent.org/docs/latest/)
  - **Interview sentence:** "The agent does not get to decide that an action is allowed. An external policy does, and the trail can be checked offline."

---

## Phase 1 — Linux and Git (Nov 2026)

You already use GitHub. This phase is daily fluency: read a system, make a clean commit, undo a mistake on purpose.

- [ ] **P1-linux** — Live in a Linux shell for real labs (WSL or a small VM).
  - **Done when:** You can explain users, permissions, processes, SSH keys, and where logs are, on a machine you set up. You can find why a service you started is not listening.
  - **Start here:**
    - [The Linux command line for beginners (Ubuntu)](https://ubuntu.com/tutorials/command-line-for-beginners)
    - [Linux Journey](https://linuxjourney.com/) — paths, permissions, processes, packages
    - [Bandit](https://overthewire.org/wargames/bandit/) — levels 0–15 only, as shell practice. Log the command you learned, not a walkthrough of later levels.
- [ ] **P1-git** — History you are willing to show an interviewer.
  - **Done when:** You can branch, commit, revert, and read `git log` / `git diff` on Incident Commander without breaking the main branch. A stranger can see what each of your commits changed.
  - **Start here:**
    - [Pro Git, chapters 1–3](https://git-scm.com/book/en/v2)
    - [GitHub — about Git](https://docs.github.com/en/get-started/using-git/about-git)

**Phase proof:** one log that shows a Linux task you diagnosed, plus three real commits with messages that say why.

---

## Phase 2 — Secure pipeline (Dec 2026 – Jan 2027)

Build this on Incident Commander. Do not start a new demo app.

- [ ] **P2-docker** — You can build and run the existing stack from the docs, and explain image vs container, ports, and why the policy engine is a separate container.
  - **Done when:** You start the project from a clean clone and say what fails closed if OPA is down.
  - **Start here:**
    - [Docker — get started](https://docs.docker.com/get-started/)
    - Incident Commander quickstart in that repo
- [ ] **P2-actions** — GitHub Actions runs the tests on every push and pull request.
  - **Done when:** A pull request shows a green test check, and you can point at the workflow file.
  - **Start here:**
    - [Understanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)
- [ ] **P2-scan** — The same workflow fails on a secret and on a known-bad dependency or image, then passes after you remove it.
  - **Done when:** You have two links: a red run and the green run after the fix. The planted secret never lands on the default branch.
  - **Start here:**
    - [gitleaks](https://github.com/gitleaks/gitleaks)
    - [Trivy](https://trivy.dev/latest/docs/)
    - [Bandit](https://bandit.readthedocs.io/en/latest/) for the Python you already have, or [Semgrep](https://semgrep.dev/docs/getting-started/)
    - [About secret scanning](https://docs.github.com/en/code-security/secret-scanning/introduction/about-secret-scanning)
- [ ] **P2-name** — You can draw the pipeline from commit to deploy and name where each control sits.
  - **Start here:**
    - [OWASP DevSecOps Guideline](https://owasp.org/www-project-devsecops-guideline/) — read the pipeline stages. Map them onto your workflow in a log. Skip any section you cannot connect to your repo.

**Phase proof:** the red run and the green run. That is the DevSecOps line on the CV.

**Interview sentence:** "A push runs tests, secret detection, and a dependency scan. I have a run that failed for a real finding and a run that passed after the fix."

---

## Phase 3 — Secure AI, written down (Jan – Feb 2027)

- [ ] **P3-llm-map** — Map your Apertus result to one OWASP LLM risk, in your own words.
  - **Done when:** A short note names the risk, why your test matches it, and what you did not claim.
  - **Start here:** [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/)
- [ ] **P3-sentrix** — One security page for SentriX. No new model work in this phase.
  - **Done when:** The page states the assets, the trust boundaries (device, phone, cellular, cloud), what is authenticated, and what still leaves the device. You can defend every sentence from the current build.
  - **Start here:**
    - Your graduation-project notes
    - [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) — use Govern / Map / Measure / Manage as headings only if they fit the page
- [ ] **P3-otel** — Connect observability to the automation story.
  - **Done when:** You can trace one incident in Incident Commander from a signal to a policy decision, and you can say what you did with Splunk or Dynatrace at EJADA in the same words: signal, question, action.
  - **Start here:** [What is OpenTelemetry?](https://opentelemetry.io/docs/what-is-opentelemetry/)

**Interview sentence:** "On the device, the model runs locally and I can say what data leaves. On the agent, an action needs a policy allow and a check after the change."

---

## Phase 4 — One cloud, IAM only (Feb – Mar 2027)

Pick **one** of AWS or Azure and stay there until the proof exists. Egypt teams ask for this early. A second cloud can wait until after graduation.

- [ ] **P4-iam** — A personal account with a budget alarm, MFA on the root or tenant admin, and a user or role that can do one small thing and nothing else.
  - **Done when:** You show a policy that was too wide, the narrower policy you replaced it with, and that no long-lived key is stored in git.
  - **Start here (choose one):**
    - AWS: [IAM best practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) and [AWS Cloud Practitioner Essentials](https://aws.amazon.com/training/digital/aws-cloud-practitioner-essentials/) (the free course, not the exam yet)
    - Azure: [Azure Fundamentals — cloud concepts](https://learn.microsoft.com/en-us/training/paths/microsoft-azure-fundamentals-describe-cloud-concepts/) and [Azure RBAC best practices](https://learn.microsoft.com/en-us/azure/role-based-access-control/best-practices)
- [ ] **P4-exam** — Optional. Sit a practitioner exam only after P4-iam is done and logged.
  - **Done when:** The badge matches the account you can log into and explain.

**Interview sentence:** "The role I created can do this one action. Root stays locked, and the repo has no cloud keys."

---

## Phase 5 — Same policy, on Kubernetes (Apr – May 2027)

This is the adapter already named on the Incident Commander roadmap. It is not a separate cluster tutorial you abandon.

- [ ] **P5-k8s** — Run a local cluster and deploy one service from a manifest you wrote.
  - **Done when:** You can explain Pod, Deployment, Service, and what a probe does, on that cluster.
  - **Start here:** [Kubernetes basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [ ] **P5-gate** — One state-changing cluster action is denied or allowed by a policy outside the caller, with a log of the decision.
  - **Done when:** You can show an allow, a deny, and what happens when the policy service is unreachable (fail closed).
  - **Start here:**
    - [OPA](https://www.openpolicyagent.org/docs/latest/)
    - Your existing Rego policies in Incident Commander — extend that idea, do not start from zero

**Interview sentence:** "I reused the same rule: irreversible or out-of-policy changes do not run, including against the cluster."

---

## Before applications (May – Jun 2027)

- [ ] **P6-cv** — CV, LinkedIn, and this roadmap agree.
  - **Done when:** Each strong line has a repo, a log, or a write-up behind it. Titles match what you actually did (Observability Intern stays an internship).
- [ ] **P6-stories** — Three stories you can tell in under two minutes: the pipeline, the policy gate, the AI measurement or SentriX boundaries.

---

## Keep as foundation — do not expand this block

Already done. Log something here only if you go deeper for a real reason.

- FortiGate 7.6 policies, IPS, NAT, VPN, VLANs, FortiManager (DEPI / NTI, 120+ hours) — [lab repo](https://github.com/nourseen6/Fortinet-Device-Management-with-FortiManager)
- Cisco CCNA curriculum completed. That is not a CCNA certification. Do not write it as one.
- EJADA, July 2026: Splunk, Dynatrace, alerting, container monitoring
- Python IDS pipeline and the Packet Tracer enterprise lab — one CV line each, no follow-up project unless a job asks

## Not now

These do not get a phase before June 2027:

- Another Packet Tracer topology
- Another generic intrusion-detection classifier
- A second cloud
- A stack of certificates before the IAM lab exists
- Listing Kubernetes, Terraform, or "LLM security" on the CV before the matching proof above is logged
