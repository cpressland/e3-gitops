# e3-gitops

This repository is managed using GitOps principles.

## What is GitOps?

GitOps is a way of implementing Continuous Deployment for cloud native applications. It uses Git as a single source of truth for declarative infrastructure and applications.

## Use Cases

1. **Configuration Management**: GitOps allows you to manage system and application configurations through Git repositories.
2. **Continuous Deployment**: GitOps can automate deployments by monitoring the Git repository and applying changes when the main branch is updated.
3. **Disaster Recovery**: In case of a system failure, GitOps can help restore the system to the last known state stored in the Git repository.
4. **Rollbacks**: If a deployment fails or causes issues, GitOps allows you to easily rollback to a previous state using Git's history.
5. **Audit Logs**: Since all changes are tracked in Git, you have a complete audit trail of what changes were made, when, and by whom.

## Repo Structure

```
├── README.md           # This file
├── automation          # Configures ImageRepository and ImagePolicy resources
├── bases               # Configures Kustomizations, HelmRepository, and HelmRelease resources
    ├── cert-manager    # Installs cert-manager:   https://github.com/cert-manager/cert-manager
    ├── e3              # Installs e3-api:         https://github.com/cpressland/e3-go-test-api
    ├── sealed-secrets  # Installs sealed-secrets: https://github.com/bitnami-labs/sealed-secrets
    └── traefik         # Installs traefik:        https://github.com/traefik/traefik
└── clusters            # Configures the desired state of the cluster
    └── flux-system     # Ensures Flux is updated and configured correctly.
```
