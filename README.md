Monitoring & Alerting Stack

This project sets up a complete monitoring and alerting system using Docker Compose.
It includes Prometheus, Grafana, Alertmanager, Node Exporter, cAdvisor, and MailHog for testing alerts.


---

Features

Prometheus → Collects and stores metrics.

Grafana → Beautiful dashboards for visualization.

Alertmanager → Routes alerts to email.

Node Exporter → Monitors system metrics like CPU, memory, and disk.

cAdvisor → Tracks container metrics.

MailHog → Local SMTP server to capture alert emails.



---

Prerequisites

Docker installed

Docker Compose installed



---

How to Run

1. Clone the project and move into the directory:

git clone <your-repo-link>
cd monitoring-stack


2. Start the services:

docker-compose up -d


3. Check running containers:

docker ps




---

Access the Services

Prometheus → http://localhost:9090

Alertmanager → http://localhost:9093

Grafana → http://localhost:3000

Node Exporter → http://localhost:9100/metrics

cAdvisor → http://localhost:8080

MailHog → http://localhost:8025



---

Grafana Login

Username: admin

Password: admin



---

Setup Grafana

1. Go to Configuration → Data Sources → Add data source.


2. Select Prometheus and set the URL to:

http://prometheus:9090


3. Save & Test → should say ✅ working.


4. Import dashboards (from Grafana.com):

1860 → Node Exporter Full

193 → Docker / cAdvisor Monitoring

14282 → Prometheus Overview





---

Alerts

Prometheus rules trigger alerts (high memory, high CPU, etc.).

Alerts are sent to Alertmanager.

Alertmanager delivers them to MailHog (check http://localhost:8025).



---

Stop the Project

docker-compose down

To also remove data:

docker-compose down -v


---

That’s it ✅ — you now have a full monitoring and alerting stack running with Docker.
