# 0x09. Web Infrastructure Design

This project contains diagrams and explanations of different web infrastructure setups.  
Each task builds on the previous one to introduce concepts of scalability, redundancy, security, and monitoring.

---

## Task 0: Simple Web Stack

**Objective:** Design a one-server web infrastructure that hosts the website `www.foobar.com`.

**Components:**
- 1 Server (IP: `8.8.8.8`)
- 1 Web Server (Nginx)
- 1 Application Server
- 1 Application Files (Code Base)
- 1 Database (MySQL)
- 1 Domain Name (`foobar.com`) with `www` A record pointing to server IP

**Key Concepts:**
- Role of server, domain name, DNS record
- Functions of web server, application server, and database
- Communication over HTTP/HTTPS
- **Issues:** Single Point of Failure (SPOF), downtime during maintenance, no scalability

---

## Task 1: Distributed Web Infrastructure

**Objective:** Design a three-server web infrastructure with load balancing.

**Components:**
- 2 Servers (Nginx + App Server + App Files)
- 1 Load Balancer (HAProxy)
- 1 Primary Database (MySQL)
- 1 Replica Database (MySQL)

**Key Concepts:**
- Load balancing with **Round Robin** algorithm
- **Active–Active** vs **Active–Passive** load balancer setups
- Primary–Replica database clustering for high availability
- **Issues:** Load balancer as SPOF, no firewall, no monitoring

---

## Task 2: Secured and Monitored Web Infrastructure

**Objective:** Design a secured and monitored version of the distributed infrastructure.

**Additional Components:**
- 3 Firewalls
- 1 SSL Certificate (HTTPS)
- 3 Monitoring Clients (e.g., Sumo Logic, Datadog)

**Key Concepts:**
- Firewalls for network access control
- HTTPS for encrypted communication
- Monitoring agents for logs, metrics, and alerts
- How to monitor web server QPS
- **Issues:** SSL termination at LB is insecure for internal traffic, single write-enabled DB node, identical servers can share vulnerabilities

---

## Directory Structure

