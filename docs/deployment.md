# Deployment & Usage Guide

## Requirements
- Docker 29+
- NVIDIA Drivers installed
- NVIDIA Container Toolkit
- GPU available (tested on RTX 3060)

## Start Services (Step by Step)

### 1. Start Ollama (GPU Inference Engine)

```bash
docker compose -f ./docker/ollama/docker-compose-ollama.yml up -d
```

### 2. Start Monitoring Stack (Prometheus + Grafana + Exporter)

```bash
docker compose -f ./docker/monitoring/docker-compose-monitoring.yml up -d
```

### 3. Start OpenClaw

```bash
docker compose -f ./docker/openclaw/openclaw/docker-compose.yml up -d
```

**Apply configuration:**  

```bash
docker cp ./docker/openclaw/openclaw_temp.json openclaw-gateway:/home/node/.openclaw/openclaw.json
```

**Restart OpenClaw:**  

```bash
docker compose -f ./docker/openclaw/openclaw/docker-compose.yml down
docker compose -f ./docker/openclaw/openclaw/docker-compose.yml up -d
```

### 4. Start Reverse Proxy (Traefik)
```bash
docker compose -f ./docker/traefik/docker-compose-traefik.yml up -d
```

## Ollama Model Management

**List Installed Models**  

```bash
docker exec -it ollama ollama list
```

**Run a Model**  

```bash
docker exec -it ollama ollama run <model_name>
```
**Example:**  
```bash
docker exec -it ollama ollama run llama3.2:3b
```

**Remove a Model**

```bash
docker exec -it ollama ollama rm <model_name>
```

## GPU & Runtime Verification

**Check if Ollama is using NVIDIA runtime**  

```bash
docker inspect ollama | grep -i runtime
```
**Expected output:**  
```bash
"Runtime": "nvidia"
```

**Monitor GPU Usage Live**  
```bash
watch -n 1 nvidia-smi
```
You should see memory and compute utilization when model is running.

## OpenClaw Dashboard

```bash
docker compose run --rm openclaw-cli dashboard
```

## Useful Debug Commands

**View Logs**  

```bash
docker logs -f ollama
docker logs -f openclaw-gateway
docker logs -f ollama-exporter
docker logs -f prometheus
docker logs -f grafana
docker logs -f traefik
```