# GG GitOps (Argo CD on EKS)

## What this repo does (plain English)
- **Argo CD** watches this Git repo and **keeps the cluster in sync** with whatever is committed here.
- We have two environments:
  - **staging** → `environments/staging/base`
  - **prod** → `environments/prod/base`
- The app is a simple **Nginx "hello"** (Deployment + Service) managed by **Kustomize**.
- A **release/promotion** is just a **Git commit** that changes the image tag in the right folder.  
  Argo CD detects it and deploys automatically.
## Common tasks
..
### 1) Bump staging image (simulate new build)
```bash
cd environments/staging/base
# example: bump nginx to 1.27 (updates the kustomization image tag)
sed -i 's/newTag: ".*"/newTag: "1.27"/' kustomization.yaml
git add .
git commit -m "P11: staging -> nginx 1.27"
git push
