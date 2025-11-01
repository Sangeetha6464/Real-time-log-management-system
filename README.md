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
