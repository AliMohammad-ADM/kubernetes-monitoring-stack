# Common Role

## Purpose

The **common** role prepares the target system before any Kubernetes component is deployed.

This role provides the shared deployment logic used by all other roles and avoids duplicating common tasks throughout the project.

## Responsibilities

Current:

- Create the temporary manifest workspace:
  - `/tmp/k8s-monitoring`

Planned:

- Verify that `kubectl` is installed and available.
- Verify that the Kubernetes configuration (`KUBECONFIG`) is present and accessible.
- Prepare the temporary workspace used for generated manifests.
- Install or verify any deployment dependencies required by the automation framework.
- Provide reusable tasks for deploying Kubernetes manifests.
- Centralize deployment logic so component roles only describe the resources they manage.
