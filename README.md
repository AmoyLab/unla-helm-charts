# MCP Gateway Helm Charts

This repository contains Helm charts for deploying the MCP Gateway in Kubernetes clusters.

## Overview

The MCP Gateway Helm chart provides a way to deploy and manage the MCP Gateway service in Kubernetes environments. The chart includes all necessary components and configurations for running the gateway service.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+

## Quick Start

Add the MCP Gateway Helm repository:

```bash
helm repo add mcp-gateway https://mcp-ecosystem.github.io/mcp-gateway-helm-charts
helm repo update
```

Install the chart:

```bash
helm install mcp-gateway mcp-gateway/mcp-gateway
```

## Chart Versions

The following versions are available:
- 0.6.3 (Latest)
- 0.1.0

## Configuration

The following table lists the configurable parameters of the MCP Gateway chart and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of MCP Gateway replicas | `1` |
| `image.repository` | Container image repository | `mcp-gateway` |
| `image.tag` | Container image tag | `1.16.0` |
| `image.pullPolicy` | Container image pull policy | `IfNotPresent` |

For more configuration options, please refer to the [values.yaml](mcp-gateway/values.yaml) file.

## Installation

### Using Helm

```bash
# Install with default values
helm install mcp-gateway mcp-gateway/mcp-gateway

# Install with custom values
helm install mcp-gateway mcp-gateway/mcp-gateway --values custom-values.yaml
```

### Using Helmfile

```yaml
repositories:
  - name: mcp-gateway
    url: https://mcp-ecosystem.github.io/mcp-gateway-helm-charts

releases:
  - name: mcp-gateway
    namespace: default
    chart: mcp-gateway/mcp-gateway
    version: 0.6.3
```

## Upgrading

To upgrade the MCP Gateway deployment:

```bash
helm upgrade mcp-gateway mcp-gateway/mcp-gateway
```

## Uninstalling

To uninstall/delete the MCP Gateway deployment:

```bash
helm uninstall mcp-gateway
```
