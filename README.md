# OpenClaw Local AI Stack

A production-ready self-hosted AI infrastructure built around **Ollama + OpenClaw + Monitoring + Reverse Proxy + Telegram Bot Integration.**

This project provides a complete local AI environment including:  
- Local LLM inference powered by Ollama (GPU accelerated)
- OpenClaw Gateway & CLI integration
- Telegram Bot integration for remote AI access
- Full monitoring stack (Prometheus + Grafana)
- Reverse proxy routing (Traefik)
- Fully containerized Docker architecture
- Designed for secure, self-hosted deployments

The stack is optimized for local GPU environments and suitable for:  
- AI automation projects
- DevOps AI experimentation
- Portfolio / freelance demonstrations
- Production-ready local LLM setups
- Chat-based AI assistants via Telegram


## Telegram Integration

The stack includes Telegram Bot integration that allows:  
- Sending prompts directly from Telegram
- Receiving AI responses powered by local Ollama models
- Remote interaction with your self-hosted LLM
- Secure token-based access control

This enables real-world chatbot automation scenarios without relying on external AI APIs.
---

## Project Documentation

If you'd like to explore the system design and deployment steps in detail:

| Document | Description |
|----------|------------|
| 🏗 Architecture | System design, services, and network topology. [Read more](./docs/architecture.md) |
| 🚀 Deployment | Installation steps and startup commands. [Read more](./docs/deployment.md) |

---

## 📡 Service Ports

| Service | Port |
|----------|------|
| Ollama | 11435 |
| Prometheus | 9090 |
| Grafana | 3000 |
| Traefik | 80 |
| Traefik Dashboard | 8080 |

---

## 🛠 Tech Stack

- Docker 29+
- NVIDIA Docker Runtime
- Ollama
- OpenClaw
- Prometheus
- Grafana
- Traefik
- Telegram Bot API

---

## 💡 Use Case

This stack demonstrates how to:

- Deploy a GPU-backed local LLM
- Expose AI services behind a reverse proxy
- Integrate a messaging bot (Telegram) with a local AI model
- Collect inference metrics
- Visualize performance in Grafana
- Structure a modular AI infrastructure using Docker Compose

---

## 👤 Author

Hossam El Bassuiony  
DevOps Engineer | Infrastructure & Automation
