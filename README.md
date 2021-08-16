# Ansible project - ArgoCD

Ansible project to manage ArgoCD.

## Inventory setup

This project requires a host group named `argocd_cluster` to hold ArgoCD variables and clusters hosts list (usually the K8S master node / VIP).

## Playbooks

| Playbook                       | Description                             | Ready for AWX |
|--------------------------------|-----------------------------------------|---------------|
| `playbooks/backup_restore.yml` | Backup and restore ArgoCD configuration | Yes           |

### Playbook - `playbooks/backup_restore.yml`

Backup and restore ArgoCD.

| Tag             | Description                                          |
|-----------------|------------------------------------------------------|
| `backup-local`  | Backup ArgoCD into a local file                      |
| `backup-remote` | Backup ArgoCD onto the remove `ict-backup-01` server |
