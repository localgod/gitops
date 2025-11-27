---
layout: image-background
background: https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-xs">

# Popular GitOps Tools

**The Main Players:**

| Tool | Type | What We Know | Best For |
|------|------|-------------|----------|
| **Argo CD** | Pull-based GitOps | *Kubernetes-native, great UI, active community* | Teams wanting visibility & control |
| **Flux CD** | Pull-based GitOps | *Lightweight, CNCF graduated, GitOps Toolkit approach* | Cloud-native purists |
| **Jenkins X** | CI/CD + GitOps | *Opinionated, batteries-included, heavy* | Teams wanting full automation |
| **Rancher Fleet** | Multi-cluster GitOps | *Manages thousands of clusters, edge-focused* | Large-scale deployments |

<div class="mt-4" />

**Supporting Tools:**

- **Helm / Kustomize** – Configuration management for applications (infrastructure is handled with separate IaC tooling)
- **Crossplane** – Kubernetes-native infrastructure provisioning

<div class="mt-4 text-xs opacity-75">

*We're exploring Argo CD alongside existing IaC tooling. Argo CD focuses on application delivery while IaC tools manage infrastructure.*

</div>

</div>
