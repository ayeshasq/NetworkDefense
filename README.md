# 🛡️ Network Defense with Splunk SIEM  

This project implements **Splunk Enterprise** as a **Security Information and Event Management (SIEM)** solution for *Luna Bags*, a small but growing e-commerce company. The goal is to **enhance network defense** by enabling **real-time monitoring, centralized logging, and proactive threat detection** while addressing **limited IT resources** typical of small organizations.  

---

## 📌 Project Overview  

- **Company:** *Luna Bags* – an eco-friendly handbag and backpack e-commerce startup.  
- **Problem:** Small IT team struggling to monitor network traffic and prevent cyber threats.  
- **Solution:** Deploy **Splunk Enterprise** on the router and **Splunk Universal Forwarder** on the DMZ web server.  
- **Objective:** Provide **end-to-end visibility, security monitoring, and compliance** (PCI-DSS) with minimal overhead.  

---

## 🎯 Key Objectives  

1. **Centralized Monitoring** – Aggregate logs from router & web server into Splunk.  
2. **Enhanced Security** – Detect & respond to threats like DoS, malware, phishing, and MITM.  
3. **Performance Optimization** – Identify bottlenecks and anomalous traffic.  
4. **Compliance Support** – Ensure PCI-DSS readiness with audit-friendly logging.  
5. **Scalability** – Enable future integration with SOAR, MITRE ATT&CK mapping, and cloud workloads.  

---

## 🏗️ Implementation Strategy  

### 🔹 Network Topology
- **Internal Network:** `192.168.60.0/24` (Finance, Marketing, HR, IT, Management).  
- **DMZ:** `10.9.0.0/24` hosting public web server (`10.9.0.5`).  
- **Router:** `10.9.0.11` connecting internal + DMZ + internet, hosting Splunk Enterprise.  

### 🔹 Splunk Deployment Steps  

#### 1. Splunk Enterprise (on Router)
```bash
# Download Splunk Enterprise
wget <splunk-enterprise-wget-link>
tar -xvf splunk-<version>.tgz -C /opt

# Start Splunk
/opt/splunk/bin/splunk start

# Configure
nano /opt/splunk/etc/system/local/inputs.conf
nano /opt/splunk/etc/system/local/outputs.conf

# Restart to apply changes
/opt/splunk/bin/splunk restart
