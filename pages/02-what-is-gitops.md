# What is GitOps?

**Definition:**

GitOps is a set of practices that uses Git as the single source of truth for declarative infrastructure and application configurations.

<div class="mt-8" />

**Core Principles:**

- **Declarative:** Desired system state is defined in code (e.g., YAML, Helm).
- **Versioned & Immutable:** Git tracks changes, enabling auditability and rollback.
- **Automatically Applied:** Changes in Git trigger automated reconciliation in the runtime environment.
- **Continuously Reconciled:** The system ensures the actual state matches the desired state.
