# Home Network Monitoring with Grafana + Prometheus + Node Exporter

This project sets up a monitoring stack to visualize system and network metrics from a Proxmox host using **Prometheus**, **node_exporter**, and **Grafana**, all running on LXC containers and host systems.

---

## Components

| Component     | Location        | Description |
|---------------|-----------------|-------------|
| **Prometheus** | LXC container   | Collects metrics from the host |
| **node_exporter** | Proxmox Host | Exposes system/network metrics |
| **Grafana**    | LXC container   | Visualizes metrics from Prometheus |

---
## Visual Dashboard
![imagen](https://github.com/user-attachments/assets/09993990-e517-49bd-b055-b0cf02911a8e)

---

## Installation Steps

### 1. Install `node_exporter` on the Proxmox Host

```bash
cd ~
wget https://github.com/prometheus/node_exporter/releases/download/v1.9.1/node_exporter-1.9.1.linux-amd64.tar.gz
tar xvf node_exporter-1.9.1.linux-amd64.tar.gz
cd node_exporter-1.9.1.linux-amd64
./node_exporter &
```

Optional: run as a service

```bash
sudo tee /etc/systemd/system/node_exporter.service > /dev/null <<EOF
[Unit]
Description=Node Exporter
After=network.target

[Service]
User=root
ExecStart=/root/node_exporter-1.9.1.linux-amd64/node_exporter

[Install]
WantedBy=default.target
EOF

sudo systemctl daemon-reload
sudo systemctl enable node_exporter
sudo systemctl start node_exporter
```

---

### 2. Install Prometheus in an LXC Container

```bash
apt update && apt install prometheus -y
nano /etc/prometheus/prometheus.yml
```

Add your host IP as a target:

```yaml
scrape_configs:
  - job_name: 'proxmox'
    static_configs:
      - targets: ['192.168.0.100:9100']
```

Restart Prometheus:
```bash
systemctl restart prometheus
```

---

### 3. Install Grafana in Another LXC Container

```bash
apt install -y software-properties-common
wget -q -O - https://packages.grafana.com/gpg.key | apt-key add -
add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
apt update && apt install grafana -y
systemctl enable grafana-server
systemctl start grafana-server
```

---

## Configure Grafana

- Access: `http://<grafana-IP>:3000`
- Login: `admin / admin`

### Add Prometheus as a Data Source

1. Go to **Settings → Data Sources → Add data source**
2. Select **Prometheus**
3. URL: `http://<prometheus-IP>:9090`
4. Save & Test

### Import a Dashboard

1. Go to **+ Create → Import**
2. Enter ID `1860` (Node Exporter Full)
3. Select your Prometheus data source
4. Click **Import**

---

## Verify

- `curl http://<PVE-IP>:9100/metrics` (Node Exporter)
- `http://<prometheus-IP>:9090` (Prometheus UI)
- `http://<grafana-IP>:3000` (Grafana)

---
