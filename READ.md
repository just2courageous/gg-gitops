# gg-gitops

**Goal:** Prove real GitOps using Argo CD on EKS.

**What this repo contains:**
- Argo CD application definitions (`argocd/`)
- A demo app (`apps/demo/`) that gets auto-deployed to the cluster
- Screenshot evidence (`docs/screenshots/`) that Git controls production

**Story for recruiters:**
- I deploy Argo CD in-cluster
- Argo CD watches this repo
- When I change Kubernetes YAML in Git, Argo CD auto-syncs the cluster
- No kubectl apply in prod. Git is the source of truth.
