---
layout: image-background
background: https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=1920&q=80
class: text-white
---

<div class="backdrop-blur-sm bg-black/60 p-6 rounded-lg text-xs">

# Traditional CI/CD enhanced by GitOps

**How We Used to Deploy vs How We Deploy Now:**

| Aspect               | Traditional CI/CD   | GitOps              |
| -------------------- | ------------------- | ------------------- |
| **Trigger**          | Push-based          | Pull-based          |
| **Source of Truth**  | Pipeline scripts    | Git repository      |
| **Deployment Logic** | In pipeline scripts | External controller |
| **Rollback**         | Manual or scripted  | Git revert          |
| **Observability**    | Pipeline-centric    | State-centric       |

<div class="mt-4 text-xs opacity-75">

**The Big Shift:** GitOps decouples deployment logic from CI pipelines. Your CI builds and tests. Your GitOps controller deploys and maintains. Separation of concerns at its finest.

</div>

</div>
