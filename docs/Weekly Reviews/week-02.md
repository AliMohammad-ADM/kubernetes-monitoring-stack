# Week 02 Review (16 Jul - 24 Jul 2026)

## Overview

This week focused on completing the monitoring pipeline by deploying the remaining components, validating end-to-end communication, troubleshooting Kubernetes networking issues, and implementing a complete alerting workflow from Prometheus to Telegram.

## Accomplishments

- Deployed Grafana Alloy manually using a DaemonSet.
- Configured Alloy to collect Kubernetes logs.
- Verified successful log ingestion into Loki.
- Deployed Prometheus manually using a StatefulSet.
- Configured Prometheus to scrape:
  - Itself
  - Node Exporter
- Deployed Node Exporter manually using a DaemonSet.
- Configured Prometheus alert rules.
- Deployed Alertmanager manually using a StatefulSet.
- Configured Alertmanager using ConfigMaps and Kubernetes Secrets.
- Generated the final Alertmanager configuration using an initContainer.
- Connected Prometheus to Alertmanager.
- Configured Telegram notifications.
- Successfully received alert notifications on Telegram.
- Verified the complete monitoring and alerting pipeline.

## Kubernetes Networking Investigation

While validating Prometheus and Alloy, pod-to-pod communication worked only for workloads running on the control-plane node.

The following were investigated during troubleshooting:


- Prometheus scrape configuration
- Kubernetes Services
- Pod networking
- Flannel VXLAN overlay networking
- firewalld configuration
- VXLAN interfaces
- Kubernetes DNS
- Cross-node communication

The root cause was identified as an incomplete **firewalld** configuration.

The following fixes were implemented:

- Allowed Kubernetes control-plane and VXLAN ports.
- Enabled forwarding and masquerading.
- Assigned both **flannel.1** and **cni0** interfaces to the **trusted** firewall zone.

After applying the correct firewall configuration

- Prometheus successfully scraped Node Exporter on every node.
- Alloy successfully forwarded logs from every worker node.
- Cross-node Kubernetes networking functioned correctly.

## Alertmanager Investigation

Several deployment challenges were encountered while configuring Alertmanager.

The following issues were resolved:

- Read-only ConfigMap mount preventing configuration generation.
- Dynamic configuration generation using an initContainer.
- Secret substitution using `envsubst`.
- Shared EmptyDir volume between initContainer and main container.
- Telegram message formatting errors caused by MarkdownV2 parsing

After correcting the configuration

- Alertmanager successfully loaded the generated configuration.
- Prometheus alerts were received correctly.
- Telegram notifications were delivered successfully.

## Key Lessons

- Understanding Kubernetes overlay networking with Flannel VXLAN.
- Debugging pod-to-pod communication across multiple nodes.
- Using Linux networking tools such as `ip route`, `ip link`, and `firewall-cmd`.
- Understanding firewalld zones and interface assignments.
- Using initContainers to generate runtime configuration.
- Separating sensitive information using Kubernetes Secrets.
- Understanding the complete Prometheus → Alertmanager alert lifecycle.
- Following a structured debugging methodology instead of changing multiple variables at once.

## Next Week

- Review the completed monitoring stack.
- Create the architecture diagram.
- Begin planning Version 2 improvements, including Ansible automation and production refinements
