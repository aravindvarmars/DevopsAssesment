# 🚀 Linq DevOps Assessment – Monitoring & Alerting Stack

This project implements a containerized monitoring, alerting, and visualization solution using Docker, Prometheus, Node Exporter, Grafana, and Alertmanager.

---

## 📊 Monitoring Design

The system is designed to monitor key system-level metrics using the following components:

- **Metrics Monitored:** CPU usage, Memory usage, Disk space, Network I/O
- **Metric Collection Tool:** Node Exporter is used to expose system-level metrics in a format consumable by Prometheus.
- **Backend Storage:** Prometheus is used to scrape, store, and expose metrics to Grafana.

The architecture supports extensibility for additional exporters or multiple host nodes.

---

## 🚨 Alerting Strategy

Prometheus alerting rules are configured to detect common resource bottlenecks:

- **High CPU Usage:** Triggers when CPU usage > 85% for 2 minutes
- **High Memory Usage:** Triggers when memory usage > 90% for 2 minutes

### Delivery Method

Alerts are routed to **Alertmanager**, which can be configured to send notifications via email, Slack, PagerDuty, etc. (for demo purposes, Alertmanager UI is used).

---

## 📈 Grafana Dashboard

A Grafana dashboard has been set up to visualize:
- CPU Usage (%)
- Memory Usage (%)
- (Optional) Disk and Network metrics

**Access Grafana at:** http://localhost:3000  
**Login:** `admin` / `admin`

## 🔧 How to Run

Ensure Docker is installed, then run:

```bash
docker compose up -d
```

**Services exposed:**  
- Prometheus: [http://localhost:9090](http://localhost:9090)  
- Grafana: [http://localhost:3000](http://localhost:3000)  
- Alertmanager: [http://localhost:9093](http://localhost:9093)

---

## 🔄 Scalability Consideration

This architecture is modular and can be scaled by:
- Adding Prometheus federation for multi-node scalability
- Running multiple exporters across environments
- Routing alerts to multiple receivers via Alertmanager

---

## 📁 Project Structure

```
Linq-devops-assessment/
├── docker-compose.yml
├── prometheus/
│   ├── prometheus.yml
│   └── alert.rules.yml
├── alertmanager/
│   └── config.yml
├── grafana/
│   └── dashboards/
│       └── system_metrics.json
├── screenshots/
│   └── dashboard.png
└── README.md
```

---

## 🙌 Author

**Aravind Varma**  
Email: aravindvarmars@gmail.com  
LinkedIn: [linkedin.com/in/aravindvarma](#)# DevopsAssesment
# DevopsAssesment
