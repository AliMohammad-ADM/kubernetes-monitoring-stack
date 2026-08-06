# Loki Ansible Role

This Ansible role deploys Grafana Loki on the Kubernetes cluster.

The role automates the creation of Loki manifests and applies them to the cluster using Ansible.

## Features

- Creates Loki namespace
- Deploys Loki StatefulSet
- Creates Loki Services
- Configures Loki storage
- Applies Loki Kubernetes manifests automatically
- Supports manifest deployment using Ansible variables

## Variables

```yaml
loki_image: grafana/loki:3.6.8
loki_storage_size: 10Gi
```

## Notes

This role currently deploys Loki in a single instance configuration.

High availability and scalable Loki deployment can be added in future versions.
