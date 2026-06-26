# gobble

A small deployment repo for running LLM/SLM services on a MicroK8s cluster.

## What this repo contains

- Kubernetes manifests for a self-hosted inference service
- A GitHub Actions workflow for deploying to your cluster
- A simple layout for adding models, APIs, and sidecar services later

## Suggested stack

This repo is designed to host services such as:
- Ollama-style local inference
- text-generation APIs
- lightweight model serving
- agent or tool wrappers

## Structure

```text
gobble/
├── .github/
│   └── workflows/
│       └── deploy.yaml
├── k8s/
│   ├── namespace.yaml
│   ├── storageclass.yaml
│   ├── ollama.yaml
│   └── README.md
└── README.md
```

## Deployment flow

1. Push to the main branch.
2. GitHub Actions applies the Kubernetes manifests to your MicroK8s cluster.
3. Your service becomes available through the configured LoadBalancer or ingress.
