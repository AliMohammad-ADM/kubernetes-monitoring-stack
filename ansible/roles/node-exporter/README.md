# Node Exporter Ansible Role

This Ansible role deploys Prometheus Node Exporter on the Kubernetes cluster.

The role automates the creation of Node Exporter manifests and applies them to the cluster using Ansible.

## Features

- Deploys Node Exporter as a DaemonSet
- Collects node-level system metrics
- Exposes metrics for Prometheus to scrape
- Runs one Node Exporter pod on each Kubernetes node
- Applies Node Exporter Kubernetes manifests automatically
- Supports manifest deployment using Ansible variables

## Variables

```yaml
node_exporter_image: ghcr.io/prometheus/node_exporter:v1.12.1
```

## Notes

This role currently deploys Node Exporter on every Kubernetes node to expose node-level metrics to Prometheus.

Additional exporters and metric configuration can be added in future versions.
