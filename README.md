
# Perform analysis of node


![Celestia Analyst Screenshot](/images/Analyst%20screenshot.jpg "Celestia Analyst Screenshot")

## Quick Start
Scripts that I use to build a dashboard
### monitoring-tool

> A powerful and easy-to-use monitoring tool for server hardware and validator nodes with alerts via telegram bot and grafana dashboards

##### Includes

### Containers
- [grafana sever](https://hub.docker.com/r/grafana/grafana)
- [node_exporter](https://hub.docker.com/r/prom/node-exporter)
- [prometheus](https://hub.docker.com/r/prom/prometheus)
- [alertmanager](https://hub.docker.com/r/prom/alertmanager)

### Dashboards
- [Node Exporter Full dashboard](https://github.com/rfrail3/grafana-dashboards)
- [Node Exporter for Prometheus Dashboard EN](https://github.com/starsliao/Prometheus/tree/master/node_exporter)
- Cosmos-based Chain Validator Dashboard (my own dashboard)

## How to run
### Automatic installation
```
bash <(curl -s https://raw.githubusercontent.com/nodejumper-org/monitoring-tool/main/utils/install.sh)
```

### Manual installation
1. Install docker
```
bash <(curl -s https://raw.githubusercontent.com/nodejumper-org/monitoring-tool/main/utils/install_docker.sh)
```

2. Clone the repo
```
cd ~
git clone https://github.com/nodejumper-org/monitoring-tool.git 
```

3. Create configuration files from examples
```
cd monitoring-tool
cp docker-compose.yml.example docker-compose.yml
cp prometheus/prometheus.yml.example prometheus/prometheus.yml
cp alertmanager/config.yml.example alertmanager/config.yml
cp Caddyfile.example Caddyfile
```

4. Start containers
```
sudo docker compose up -d
```

4. Open in browser http://<your_server_ip>:3000 <br>
default credentials: admin/admin
