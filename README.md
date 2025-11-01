# 🧠 Real-Time Log Management System

### 📂 Overview
This project implements a **Real-Time Log Management and Monitoring System** using **Fluentd**, **InfluxDB**, and **Grafana** on **Ubuntu (WSL)**.  
It provides a centralized platform for collecting, storing, and visualizing system and application logs — enabling continuous monitoring and performance tracking of Linux-based environments.

---

## 🎯 Objective
To design and deploy a **DevOps-based solution** that automates the **collection, storage, and visualization** of system and application logs in real time, improving **observability**, **reliability**, and **system performance**.

---

## ⚙️ Tech Stack

| Component | Purpose |
|------------|----------|
| 🟠 **Fluentd** | Log collection and unified data pipeline |
| 🟢 **InfluxDB** | Time-series database for structured log storage |
| 🔵 **Grafana** | Visualization and dashboarding tool |
| 🐧 **Ubuntu (WSL)** | Deployment and test environment |
| 🧰 **Shell/Python Scripts** | Automated system metric collection (CPU, Memory, Disk) |

---

## 🧩 System Architecture

+-----------------+ +--------------------+ +------------------+
| Data Sources | ---> | Fluentd | ---> | InfluxDB |
| (System Logs, | | (Collector + | | (Time-series DB)|
| App Logs) | | Aggregator) | | |
+-----------------+ +--------------------+ +------------------+
|
v
+------------------+
| Grafana |
| (Visualization) |
+------------------+


---

## 🔑 Key Features

✅ Real-time **log collection** from system and application sources  
✅ **Resource monitoring** for CPU, Memory, Disk, and MySQL logs  
✅ **Automated pipeline** — no manual intervention needed  
✅ Centralized **time-series database (InfluxDB)**  
✅ **Dynamic Grafana dashboards** for visualization and analysis  
✅ **DevOps simulation** for monitoring and deployment environments  

---

## 🚀 Installation & Setup

### **1️⃣ Install Fluentd**
```bash
gem install --user-install fluentd
fluentd --setup ./fluent
### **2️⃣ Configure Fluentd**

Create a file named fluent.conf:
<source>
  @type exec
  command /path/to/resource_monitor.sh
  tag system.metrics
  <parse>
    @type json
  </parse>
  interval 5s
</source>

<match **>
  @type influxdb
  host localhost
  port 8086
  database syslog
</match>
### **3️⃣ Start InfluxDB and Grafana

Launch InfluxDB and create a database named syslog

Open Grafana and add InfluxDB as a data source

### **4️⃣ Visualize

Create dashboards to visualize metrics like CPU, Memory, Disk, and MySQL usage

Set thresholds and alerts for proactive monitoring
📈 Sample Dashboard

In grafana dashboard:
Example panels:

System CPU Usage (%)

Memory Utilization (%)

Disk Consumption (GB)

MySQL Log Activity

### **🧠 DevOps Relevance
DevOps Concept	How This Project Demonstrates It
Continuous Monitoring	Real-time metrics and log visibility
Automation	Fluentd automates collection and forwarding
Deployment Integration	Multiple tools configured in production-like WSL environment
Observability	Grafana dashboards for deep performance insight
Scalability	Modular and expandable architecture for multi-source logging
### **💡 Skills Demonstrated

🔹 Log Aggregation & Centralized Management

🔹 Time-Series Data Storage

🔹 Data Visualization & Dashboard Creation

🔹 Linux Deployment & Configuration

🔹 Monitoring Automation

🔹 DevOps Toolchain Integration
