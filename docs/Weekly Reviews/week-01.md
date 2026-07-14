# Week 01 Review (07 Jul - 13 Jul 2026)

## Overview

This week focused on building the foundation of the Kubernetes monitoring and logging platform by manually deploying and understanding each component.

## Accomplishments

- Built and verified the K3s cluster.
- Learned the purpose and behavior of:
  - Deployments
  - StatefulSets
  - DaemonSets
  - Services
  - ConfigMaps
  - Persistent Volumes and Persistent Volume Claims
  - StorageClasses
- Deployed Loki manually using a StatefulSet.
- Configured persistent storage for Loki.
- Deployed Promtail manually using a DaemonSet.
- Deployed Grafana manually.
- Configured Grafana persistence using a PVC.
- Connected Grafana to Loki successfully.
- Verified Grafana access using port-forwarding.
- Imported and tested a Loki dashboard.

## Promtail Investigation

Promtail deployed successfully, but discovered zero Kubernetes targets.

The following were verified during troubleshooting:

- RBAC permissions
- ServiceAccount configuration
- ClusterRole and ClusterRoleBinding
- Kubernetes API access
- Mounted log paths
- Loki connectivity
- Promtail configuration
- Official configuration comparison

After extensive debugging, the decision was made to migrate to **Grafana Alloy**, the recommended successor to Promtail.

## Key Lessons

- Choosing the correct Kubernetes workload for each application.
- Understanding persistent storage and StorageClasses.
- Learning a structured Kubernetes debugging workflow instead of guessing.
- Building every component manually before introducing Helm.

## Next Week

- Deploy Grafana Alloy.
- Replace Promtail.
- Verify Kubernetes log collection.
- Continue building the monitoring stack.