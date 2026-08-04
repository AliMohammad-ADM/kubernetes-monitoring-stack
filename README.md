# Kubernetes Monitoring Stack

## Project Goal

This project demonstrates how to deploy a production-inspired monitoring and logging platform on Kubernetes using:

- Loki
- Grafana Alloy
- Grafana
- Prometheus
- Node Exporter
- Alertmanager
- Ansible

The objective is to automate deployment, monitor workloads, collect logs, visualize metrics, and document the entire process as a portfolio project.

---

## Progress

- [x] Git & GitHub Setup
- [x] Repository Initialization
- [x] k3s Cluster
- [x] Monitoring Namespace
- [x] Storage Foundation
- [ ] NFS Storage
- [x] Loki
- [x] Grafana Alloy
- [x] Grafana
- [x] Prometheus
- [x] Node Exporter
- [x] Alertmanager
- [x] Demo Applications
- [x] Ansible Project Structure
- [x] Namespace Automation
- [ ] Documentation
- [ ] Architecture Diagram
- [ ] PowerPoint
- [ ] Final Testing

---

## Current Status

Grafana, Loki, and Grafana Alloy have been deployed manually.

The logging pipeline has been successfully migrated from Promtail to Grafana Alloy, the actively maintained successor to the deprecated Promtail project.

The Alloy deployment has been successfully created and verified, including:

- Kubernetes API discovery
- RBAC configuration
- Pod log collection
- Log processing pipeline
- Loki connectivity
- Grafana log visualization

Kubernetes logs are now successfully collected by Grafana Alloy, stored in Loki, and visualized through Grafana Explore and Loki dashboards.

Prometheus and Node Exporter have been successfully deployed and integrated with Grafana. Prometheus is scraping metrics through Kubernetes service discovery with relabeling, and metrics are available in Grafana Explore for visualization.

Diagnosed and resolved a cross-node Flannel networking issue caused by firewalld zone configuration on Rocky Linux.

Successfully deployed Alertmanager and configured to route alerts into telegram reciever.

Initialized the Ansible automation framework.

Designed a reusable role structure following production-oriented practices.

Implemented the first idempotent automation role for Kubernetes namespace creation.

Introduced a shared `common` role to centralize deployment logic for future components.

Future enhancement:

- Extend the existing Alloy DaemonSet to collect Prometheus metrics and replace Node Exporter.
- Automate Setting up the monitoring platform using ansible

---

## Features

- Manual Kubernetes deployment (no Helm)
- Centralized log aggregation with Loki
- Log collection using Grafana Alloy
- Metrics collection with Prometheus
- Node monitoring using Node Exporter
- Visualization with Grafana
- Telegram alert notifications
- Persistent storage using PVCs

---

## Challenges Solved

- Kubernetes Service discovery
- Pod-to-Pod networking debugging
- firewalld and Flannel VXLAN troubleshooting
- Node Exporter connectivity issues
- Alertmanager configuration using Secrets
- Dynamic configuration generation with initContainers
- Telegram integration and Markdown parsing issues

---

## Architecture

### Monitoring Pipeline

Application Logs
        │
        ▼
Grafana Alloy
        │
        ▼
Loki
        │
        ▼
Grafana

----------------------------

### Metrics Pipeline

Node Exporter
        │
        ▼
Prometheus
        │
        ▼
Alertmanager
        │
        ▼
Telegram

---

## Author

Ali Mohammad
