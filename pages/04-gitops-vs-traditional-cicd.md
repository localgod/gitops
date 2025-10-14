# GitOps vs Traditional CI/CD

| Aspect | Traditional CI/CD | GitOps |
|--------|-------------------|--------|
| **Trigger** | Push-based (CI pipeline triggers deployment) | Pull-based (runtime pulls desired state from Git) |
| **Source of Truth** | CI/CD pipeline config (e.g., Jenkinsfile) | Git repository |
| **Deployment Logic** | Embedded in pipeline scripts | External controller reconciles state |
| **Rollback** | Manual or scripted | Git revert triggers automatic rollback |
| **Observability** | Pipeline-centric | State-centric (actual vs desired state) |

<div class="mt-8" />

**Key Differentiator:**

GitOps decouples deployment logic from CI pipelines and shifts control to the runtime environment.
