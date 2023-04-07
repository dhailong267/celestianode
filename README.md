
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

## Link to view the Dashboard
### https://snapshots.raintank.io/dashboard/snapshot/SpFP01am4kSqELpUeR7sfoK7pO5aGbeE

Server Resource Overview

1. CPU usage: 80 active, 20 idle; %CPU used 30
2. Memory usage: 50% used
3. Disk space: 38% used
4. Load average: 1min=0.76, 5min=0.72, 15min=0.68
5. Network usage: Receive: 1.5Gbps, Transmit: 1.2Gbps

Resource Detail

1. CPU usage: The average CPU usage is around 30%
2. Memory usage: The server has a total of 8GB RAM installed and approximately 4GB is used. RAM usage is split among active processes but the majority of RAM is used by the two processes: "grafana" and "telegraf".
3. Disk usage: The server has a 30GB disk and around 38% of it is used. Disk usage is mostly by "/var/lib/grafana" which occupies approximately 23GB out of 30GB.
4. Load average: The load average for 1min, 5min and 15min is less than 1, indicating that the server is not overworked and can handle additional loads without hiccups.
5. Network usage: The server is receiving data at the rate of 1.5Gbps and transmitting data at the rate of 1.2Gbps
