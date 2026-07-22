Author: Selim Ege Okumuş

Homelab Telemetry & System Infrastructure Stack

Project Type: Infrastructure as Code (IaC) & Telemetry

Core Stack: Docker Compose | Prometheus | Grafana | Node Exporter


Project Overview
This project is a containerized, real-time system telemetry and infrastructure monitoring stack built with Docker Compose, Prometheus, and Grafana.

Designed as a personal homelab monitoring solution, it automatically scrapes system-level metrics (CPU utilization, RAM allocation, network traffic patterns, and process states) and visualizes them on a custom-configured analytical dashboard.

Dashboard Overview
Figure 1: Real-time Grafana dashboard visualizing live system metrics and hardware resource consumption.

Architecture & Data Pipeline
The infrastructure operates via a three-tier decoupled architecture:

Metrics Export Layer: Node Exporter interface extracts hardware and OS-level metrics directly from the host machine.

Time-Series Database (TSDB): Prometheus periodically scrapes metrics from the exporter at configured time intervals.

Visualization Layer: Grafana queries Prometheus to generate real-time visual analytics.

[ Node Exporter (Port: 9100) ] ---> [ Prometheus (Port: 9090) ] ---> [ Grafana (Port: 3000) ]

Deployment & Operations
Prerequisites
Docker Desktop (with WSL2 backend enabled)

Docker Compose CLI

Running the Stack
Clone the repository:
git clone https://github.com/selimegeokumus/homelab-telemetry-stack.git
cd homelab-telemetry-stack

Spin up the container environment:
docker compose up -d

Access the Monitoring UI:

Grafana Web Dashboard: http://localhost:3000 (Default Login: admin / admin)

Prometheus Metrics Explorer: http://localhost:9090

Node Exporter Raw Data: http://localhost:9100/metrics

Key Technical Competencies Demonstrated
Infrastructure as Code (IaC): Declarative container stack orchestration using Docker Compose YAML syntax.

Observability & Telemetry: Hands-on understanding of time-series data collection, scraping targets, and metrics visualization.

Linux System Administration: Container-host volume binding, networking isolation, and WSL2 integration.

