# OpenClaw Local AI Stack

A production-ready self-hosted AI infrastructure built around **Ollama + OpenClaw + Monitoring + Reverse Proxy**.

This project provides a complete local AI environment including:

- Local LLM inference powered by Ollama (GPU accelerated)
- OpenClaw Gateway & CLI integration
- Full monitoring stack (Prometheus + Grafana)
- Reverse proxy routing (Traefik)
- Fully containerized Docker architecture
- Designed for secure, self-hosted deployments

The stack is optimized for local GPU environments and suitable for:
- AI automation projects
- DevOps AI experimentation
- Portfolio / freelance demonstrations
- Production-ready local LLM setups

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

---

## 💡 Use Case

This stack demonstrates how to:

- Deploy a GPU-backed local LLM
- Expose AI services behind a reverse proxy
- Collect inference metrics
- Visualize performance in Grafana
- Structure a modular AI infrastructure using Docker Compose

---

## 👤 Author

Hossam El Bassuiony  
DevOps Engineer | Infrastructure & Automation