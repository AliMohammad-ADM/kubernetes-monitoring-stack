# Prometheus Ansible Role

This Ansible role deploys Prometheus on the Kubernetes cluster.

The role automates the creation of Prometheus manifests and applies them to the cluster using Ansible.

## Features

- Deploys Prometheus
- Configures Kubernetes service discovery
- Scrapes Node Exporter metrics
- Loads Prometheus configuration automatically
- Applies Prometheus Kubernetes manifests automatically
- Supports manifest deployment using Ansible variables

## Variables

```yaml
prometheus_image: prom/prometheus:v3.5.0
prometheus_storage: 5Gi
```

## Notes

This role currently deploys Prometheus with persistent storage and configures it to discover and scrape Node Exporter pods.

Alerting rules and additional scrape targets can be added in future versions.
