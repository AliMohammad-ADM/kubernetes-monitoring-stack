# Kubernetes Monitoring Stack

## Project Goal

This project demonstrates how to deploy a production-inspired monitoring and logging platform on Kubernetes using:

- Loki
- Promtail
- Grafana
- Prometheus
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
- [x] Promtail
- [x] Grafana
- [ ] Prometheus
- [ ] Alertmanager
- [ ] Demo Applications
- [ ] Ansible Automation
- [ ] Documentation
- [ ] Architecture Diagram
- [ ] PowerPoint
- [ ] Final Testing

---

## Current Status

Grafana, Loki, and Promtail have been deployed manually.

The Promtail deployment was successfully created and verified, including:

- Kubernetes API access
- RBAC configuration
- Filesystem permissions
- Loki connectivity

Despite successful deployment and validation, Promtail discovers zero Kubernetes log targets.

The next project milestone is migrating the logging pipeline to **Grafana Alloy**, the actively maintained successor to the deprecated Promtail project.

## Author

Ali Mohammad
