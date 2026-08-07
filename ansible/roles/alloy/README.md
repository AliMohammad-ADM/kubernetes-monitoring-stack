# Grafana Alloy Ansible Role

This Ansible role deploys Grafana Alloy on the Kubernetes cluster.

The role automates the creation of Alloy manifests and applies them to the cluster using Ansible.

## Features

- Creates Alloy ServiceAccount
- Configures Alloy RBAC permissions
- Deploys Alloy as a DaemonSet
- Configures Kubernetes pod log discovery
- Sends collected logs to Loki
- Applies Alloy Kubernetes manifests automatically
- Supports manifest deployment using Ansible variables

## Variables

```yaml
alloy_image: grafana/alloy:v1.17.1
```

## Notes

This role currently configures Alloy for Kubernetes pod log collection and forwards the logs to Loki.

Additional Alloy functionality can be added in future versions.


