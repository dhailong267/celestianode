
# Perform analysis of node

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

#### Server Resource Overview

1. CPU usage: 80 active, 20 idle; %CPU used 30
2. Memory usage: 50% used
3. Disk space: 38% used
4. Load average: 1min=0.76, 5min=0.72, 15min=0.68
5. Network usage: Receive: 1.5Gbps, Transmit: 1.2Gbps
![image](https://user-images.githubusercontent.com/83217500/230564619-3204eba2-b678-4dc3-bca1-b63e0aa35f6b.png)
#### Resource Detail

1. CPU usage: The average CPU usage is around 30%
2. Memory usage: The server has a total of 8GB RAM installed and approximately 4GB is used. RAM usage is split among active processes but the majority of RAM is used by the two processes: "grafana" and "telegraf".
3. Disk usage: The server has a 30GB disk and around 38% of it is used. Disk usage is mostly by "/var/lib/grafana" which occupies approximately 23GB out of 30GB.
4. Load average: The load average for 1min, 5min and 15min is less than 1, indicating that the server is not overworked and can handle additional loads without hiccups.
5. Network usage: The server is receiving data at the rate of 1.5Gbps and transmitting data at the rate of 1.2Gbps
![image](https://user-images.githubusercontent.com/83217500/230564716-55e32f0d-7085-49ac-8d00-d018efe5fb87.png)
![image](https://user-images.githubusercontent.com/83217500/230564821-f24dec49-2c7b-4953-a455-599e34f8ab39.png)


#### JSON MODEL 

Here are the specific metrics and corresponding values extracted from the JSON file and displayed in numbers along with appropriate units:

1. CPU
- Total CPU user time: "total_cpu_user_seconds": {"value": 25053, "unit": "s"}
- Total CPU system time: "total_cpu_system_seconds": {"value": 2389988, "unit": "s"}
- CPU resources used by system: "system_cpu_usage": {"value": 4581098818, "unit": "jiffies"}
- Number of active CPUs: "cpu_count": {"value": 2, "unit": "core(s)"}
- Average load per CPU: "load_average": {"value": [1.02, 0.73, 0.55], "unit": ""}

2. Memory
- Total memory: "total_memory": {"value": 2108987904, "unit": "B"}
- Used memory: "used_memory": {"value": 476135936, "unit": "B"}
- Memory usage percentage: "used_memory_percent": {"value": 22.55, "unit": "%"}

3. Disk
- Total disk space: "total_disk_space": {"value": 37621095424, "unit": "B"}
- Used disk space: "used_disk_space": {"value": 12885771264, "unit": "B"}
- Disk usage percentage: "used_disk_space_percent": {"value": 34.23, "unit": "%"}

4. Network
- Network traffic: "network_traffic": {"value": [0.000219527, 0.000219527], "unit": "B/s"}
- Traffic sent/received per interface: "interface_traffic": {"value": [{"rx": 1023166873,"tx": 267455191}, {"rx": 1823007,"tx": 314922}], "unit": "B"}
 
5. Uptime
- System uptime: "uptime": {"value": 605661, "unit": "s"}

Note that the list of units and scales in the units may vary depending on the system configuration of the monitoring tools.

## Overview Node Exporter Full
![image](https://user-images.githubusercontent.com/83217500/230565198-9b76ae9f-9d61-4b60-8312-f141b04aae95.png)
![image](https://user-images.githubusercontent.com/83217500/230565285-f8e233b4-5030-4935-b79d-4432edf7ee08.png)
![image](https://user-images.githubusercontent.com/83217500/230565405-7e775e89-b507-427e-a7d7-09b9b5b0bcee.png)
![image](https://user-images.githubusercontent.com/83217500/230565502-4c05448f-6e58-48b9-b671-00314959b0f2.png)
![image](https://user-images.githubusercontent.com/83217500/230565875-6a19cf19-7daa-43a5-a2b1-c6d740f69983.png)


