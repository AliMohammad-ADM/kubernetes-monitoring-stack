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
- [ ] Alertmanager
- [ ] Demo Applications
- [ ] Ansible Automation
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

Future enhancement:

- Extend the existing Alloy DaemonSet to collect Prometheus metrics and replace Node Exporter.

## Author

Ali Mohammad
