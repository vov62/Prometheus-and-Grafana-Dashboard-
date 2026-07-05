# Monitoring Stack with Prometheus, Grafana & MongoDB

A hands-on monitoring project built to learn how modern observability stacks work.

The project demonstrates how to collect metrics from both a MongoDB database and a Windows machine using Prometheus exporters, and visualize them with Grafana dashboards.

---

## Dashboard Preview

![Grafana Dashboard](images/dashboard.png)

---

## Technologies

- Docker & Docker Compose
- Prometheus
- Grafana
- MongoDB
- MongoDB Exporter
- Windows Exporter
---

## Architecture

```text
                    ┌──────────────┐
                    │   MongoDB    │
                    └──────┬───────┘
                           │
                           │
                    Database Metrics
                           │
                           ▼
                 ┌──────────────────┐
                 │ MongoDB Exporter │
                 └────────┬─────────┘
                          │
                    HTTP /metrics
                          │
                          │
┌─────────────────────┐   │
│ Windows Exporter    │───┘
│ CPU / RAM / Disk    │
│ Network Metrics      │
└──────────┬──────────┘
           │
     HTTP /metrics
           │
           ▼
   ┌───────────────────┐
   │    Prometheus     │
   │  Metrics Storage  │
   └─────────┬─────────┘
             │
      PromQL Queries
             │
             ▼
      ┌──────────────┐
      │   Grafana    │
      │ Dashboards   │
      └──────────────┘
```

---

## Dashboards

### MongoDB Dashboard

Displays metrics such as:

- MongoDB Status
- Active Connections
- Resident Memory
- Virtual Memory
- Network Traffic

---

### Windows Dashboard

Monitors the host machine using Windows Exporter.

Metrics include:

- CPU Usage
- CPU Load
- Memory
- Disk Usage
- Network Traffic
- Bandwidth

---

## Project Structure

```
monitoring-stack/
│
├── docker-compose.yml
├── prometheus/
│   └── prometheus.yml
├── mongodb/
├── images/
│   └── dashboard.png
└── README.md
```

---

## How To Run

Clone the repository

```bash
git clone https://github.com/vov62/Prometheus-and-Grafana-Dashboard-.git
```

Go into the project

```bash
cd prometheus and grafana
```

Start the containers

```bash
docker compose up -d
```

Open Grafana

```
http://localhost:3000
```

Default credentials

```
Username: admin
Password: admin
```

---

## What I Learned

During this project I learned how to:

- Deploy a monitoring stack using Docker Compose
- Configure Prometheus scrape targets
- Collect metrics using Exporters
- Monitor MongoDB
- Monitor Windows host resources
- Build Grafana dashboards
- Create PromQL queries
- Visualize system metrics in real time

---

## Future Improvements

- [ ] Alertmanager integration
- [ ] Kubernetes monitoring
- [ ] Node Exporter on Linux

