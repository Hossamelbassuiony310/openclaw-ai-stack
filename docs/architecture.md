# Architecture Overview

## Core Components

- **Telegram Bot** – Remote chat interface for AI interaction  
- **Traefik Reverse Proxy** – HTTP routing layer  
- **OpenClaw Gateway** – AI orchestration layer  
- **Ollama Exporter** – Metrics wrapper around Ollama  
- **Ollama (GPU Inference Engine)** – Local LLM runtime  
- **Prometheus** – Metrics collection & storage  
- **Grafana** – Metrics visualization & dashboards  

---

## System Flow

### AI Request Flow

```text
User (Telegram)
        ↓
Telegram Bot
        ↓
Traefik (Reverse Proxy)
        ↓
OpenClaw Gateway
        ↓
Ollama Exporter
        ↓
Ollama (GPU Inference - GPU Accelerated)
```

The AI response flows back through the same path:  
```text
Ollama → Exporter → OpenClaw → Traefik → Telegram Bot → User
```

---

## Monitoring Flow

```text
Ollama Exporter
     ↓
Prometheus
     ↓
Grafana Dashboards
```


---

## Network Design

All services run inside a shared Docker bridge network:

- Internal communication between containers
- Ollama GPU runtime enabled via NVIDIA Docker
- Reverse proxy handles external HTTP access
- Telegram Bot acts as secure remote interface

---

## Design Principles

- Modular service separation
- GPU-accelerated inference
- Observable AI workload (metrics-driven)
- Secure remote interaction via Telegram
- Production-ready containerized architecture
