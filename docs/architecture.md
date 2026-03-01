# Architecture Overview

## Components

- OpenClaw Gateway
- Ollama (GPU Inference)
- Ollama Exporter (Prometheus metrics)
- Prometheus
- Grafana
- Traefik Reverse Proxy

## Flow

User → Traefik → OpenClaw → Ollama Exporter → Ollama (GPU)
                                  ↓
                             Prometheus → Grafana