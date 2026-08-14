# Grafana Ansible Role

This Ansible role deploys Grafana on the Kubernetes cluster.

The role automates the creation of Grafana manifests and applies them to the cluster using Ansible.

## Features

- Deploys Grafana using a Deployment
- Configures persistent storage using a PVC
- Creates a Grafana Service
- Applies Grafana Kubernetes manifests automatically
- Supports manifest deployment using Ansible variables

## Variables

```yaml
grafana_image: grafana/grafana:12.1.1
grafana_storage: 1Gi
```

## Notes

This role currently deploys Grafana with persistent storage and exposes it through a Kubernetes Service.

Additional Grafana configuration and dashboards can be added in future versions.
