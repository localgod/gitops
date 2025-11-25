---
layout: image-background
background: https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-xs">

# How GitOps Actually Works (Day-to-Day)

**1. Developer Workflow (What You Do):**
- Update manifests or application configuration files (application changes). Infrastructure changes are managed separately via your IaC tooling.
- Commit and push to Git
- Open a PR, get it reviewed, merge it
- *That's it. No kubectl apply, no manual infra apply in production, no manual deployments.*

<div class="mt-3" />

**2. GitOps Controller (What Happens Automatically):**
- Watches your Git repo like a hawk
- Detects changes and applies them to the cluster
- Continuously monitors for drift (manual changes get reverted)
- *A robot that enforces "Git is the truth"*

<div class="mt-3" />

**3. Feedback Loop (How You Know It Worked):**
- Status updates in Git (commit status, PR comments)
- Dashboards showing actual vs desired state
- Alerts when something diverges or fails
- *No more guessing if your deploy succeeded*

</div>
