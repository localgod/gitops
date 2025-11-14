---
layout: image-background
background: https://images.unsplash.com/photo-1556075798-4825dfaaf498?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-sm">

# What is GitOps?

**The Simple Version:**

GitOps uses Git as the single source of truth for declarative infrastructure and application configurations. If it's not in Git, it doesn't exist.

<div class="mt-8" />

**Core Principles:**

- **Declarative:** Define what you want, not how to get there. Terraform configs, YAML manifests, Helm charts — declare your desired state.
- **Versioned & Immutable:** Every change lives in Git history. Need to audit who changed what? Git log. Need to rollback? Git revert.
- **Automatically Applied:** Push to Git, and automation takes over. No manual kubectl commands in production.
- **Continuously Reconciled:** The system constantly checks: "Does reality match what's in Git?" If not, it fixes it.

<div class="mt-6 text-sm opacity-75">

*Think of it as infrastructure on autopilot—you set the destination, Git is the map, and the GitOps controller is the driver.*

</div>

</div>
