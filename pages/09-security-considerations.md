---
layout: image-background
background: https://images.unsplash.com/photo-1563013544-824ae1b704d3?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-xs">

# Security Considerations

**Key Points:**

- **Don't commit secrets in plaintext** – Use encryption or external secret stores
- **Git access controls deployment** – RBAC in Git = RBAC in production
- **Audit trail built-in** – Git history tracks all changes

- **Git access implies production access (system)** – In a GitOps model, the ability to update the repo (especially write access to protected branches) effectively lets you change production state. This is system-level access (not direct access to production data), so treat Git permissions as production permissions: use least-privilege, enforce branch protections, and require PR reviews for changes that affect production.
- **SCM is a production dependency** – Your source control service (GitHub/GitLab/Bitbucket/etc.) becomes part of your production control plane. If the SCM is unavailable or compromised, you may be unable to update or roll back production. Plan for availability, backups, audit logging, and an emergency runbook for out-of-band changes.

<div class="mt-4 text-xs opacity-75">

*GitOps provides good auditability. Handle sensitive data appropriately.*

</div>

</div>
