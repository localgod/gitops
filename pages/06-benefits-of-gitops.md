---
layout: image-background
background: https://images.unsplash.com/photo-1450101499163-c8848c66ca85?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-xs">

# The Real Benefits (And Trade-offs)

<div grid="~ cols-2 gap-6">
<div>

**Why I Love GitOps:**
- **Auditability:** Every change in Git history. Compliance audits become trivial.
- **Rollback:** Git revert is your panic button. Works every time.
- **Developer Experience:** Developers use Git, not kubectl. Lower barrier.
- **Security:** Git RBAC = deployment RBAC. No cluster credentials on laptops.
- **Consistency:** Dev, staging, prod—all defined the same way.

</div>
<div>

**The Honest Downsides:**
- **Git Discipline Required:** Bad commits = bad deploys. No shortcuts.
- **Learning Curve:** Teams need to understand declarative thinking.
- **Tooling Complexity:** Setting up Argo CD or Flux isn't trivial. Secrets management is hard.
- **Imperative Workflows:** Sometimes you need a one-off command. GitOps fights you.

</div>
</div>

<div class="mt-4 text-xs opacity-75 text-center">

*Is it worth it? For production systems, absolutely. For quick prototypes? Maybe overkill.*

</div>

</div>
