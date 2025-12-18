---
layout: image-background
background: https://images.unsplash.com/photo-1563013544-824ae1b704d3?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-xs">

# Security Considerations

**Key Points:**

- **Secret management required** – Use encryption or external secret stores
- **Password expiry can break the pipeline** – Secrets expire; manage rotation proactively
- **Git access controls deployment** – RBAC in Git = RBAC in production
- **Audit trail built-in** – Git history tracks all changes
- **Git access = production access** – Protect branches and require PR reviews
- **SCM is critical infrastructure** – If Git is down, you can't deploy. 
- **Branch vs folder wars** – Model your enviornments, don't deploy prematurely to production. 

<div class="mt-4 text-xs opacity-75">

*GitOps provides good auditability. Handle sensitive data appropriately.*

</div>

</div>
