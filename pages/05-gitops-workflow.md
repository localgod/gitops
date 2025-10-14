# GitOps Workflow Overview

**1. Developer Workflow:**
- Commit desired state to Git (e.g., Kubernetes manifests)
- Merge triggers GitOps controller

<div class="mt-4" />

**2. GitOps Controller:**
- Continuously watches Git
- Applies changes to the cluster
- Monitors drift and reconciles

<div class="mt-4" />

**3. Feedback Loop:**
- Status reported back to Git or dashboard
- Alerts on divergence or failure
