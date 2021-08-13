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

By default, the dump file will be write and read to/from `./argocd.yaml`; You can customize the path by setting the variable `argocd_dump`.

Usage:

* Backup: `ansible-playbook -i <path to inventory> playbooks/backup_restore.yml --tags backup`
* Restore: `ansible-playbook -i <path to inventory> playbooks/backup_restore.yml --tags restore`
