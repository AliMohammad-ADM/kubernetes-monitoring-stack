
### Alertmanager

```markdown
# Alertmanager Ansible Role

This Ansible role deploys Alertmanager on the Kubernetes cluster.

The role automates the creation of Alertmanager manifests and applies them to the cluster using Ansible.

## Features

- Deploys Alertmanager using a StatefulSet
- Configures alert routing
- Groups and manages alerts
- Configures Telegram notifications
- Supports resolved alert notifications
- Applies Alertmanager Kubernetes manifests automatically
- Supports manifest deployment using Ansible variables

## Variables

```yaml
alert_manager_image: ghcr.io/prometheus/alertmanager:latest
#alert_manager_image: quay.io/prometheus/alertmanager:v0.33.1
alert_manager_storage_size: 2Gi
telegram_bot_token:
telegram_chat_id:
```

## Notes

This role currently configures Alertmanager to route alerts to Telegram.

Additional notification receivers and advanced routing can be added in future versions.
