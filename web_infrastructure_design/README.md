# Web Infrastructure Design

This repository contains diagrams and explanations for different web infrastructure designs, as part of the **Holberton School System Engineering & DevOps** track.

---

## 📌 Project Requirements

* Each task requires a **diagram** (drawn on whiteboard, Draw.io, Figma, etc.).
* Upload a screenshot of the diagram to an image hosting service (e.g., Imgur).
* Insert the **link to the diagram** inside the corresponding answer file (`0-simple_web_stack`, `1-distributed_web_infrastructure`, etc.).
* Push everything to GitHub.

---

## 📝 Tasks

### 0. Simple web stack

* **Infrastructure:**
  * 1 server with:
    * Nginx (web server)
    * Application server
    * Application files (code base)
    * MySQL database
  * Domain name: `foobar.com` → `www` record pointing to server IP `8.8.8.8`.

* **Explanation:**
  * **Server**: physical or virtual machine that hosts resources.
  * **Domain name**: human-readable name mapped to an IP.
  * **DNS record (www)**: A record.
  * **Web server**: handles HTTP requests/responses.
  * **Application server**: executes app logic.
  * **Database**: stores data.
  * **Communication**: client ↔ server via HTTP.
  * **Issues**: SPOF, downtime during maintenance, no scaling.

* **Diagram:** [Imgur link here]

---

### 1. Distributed web infrastructure

* **Infrastructure:**
  * 1 Load Balancer (HAProxy)
  * 2 servers, each with:
    * Nginx (web server)
    * Application server
    * Application files
    * MySQL database (primary-replica)

* **Explanation:**
  * **Load balancer**: distributes traffic between servers.
  * **Distribution algorithm**: e.g., round robin.
  * **Active-Active vs Active-Passive**: both active vs one backup.
  * **Database Primary-Replica**: primary handles writes, replica handles reads.
  * **Issues**: SPOF (LB, DB primary), no firewall, no HTTPS, no monitoring.

* **Diagram:** [Imgur link here]

---

### 2. Secured and monitored web infrastructure

* **Infrastructure:**
  * 1 Load Balancer (HAProxy)
  * 2 servers with app + DB
  * 3 firewalls
  * SSL certificate (HTTPS)
  * 3 monitoring agents (e.g., Sumo Logic)

* **Explanation:**
  * **Firewalls**: protect servers by filtering traffic.
  * **HTTPS/SSL**: encrypts traffic between client and server.
  * **Monitoring**: tracks performance, errors, QPS (queries per second).
  * **Issues**: SSL termination at LB = weak point, single writable DB, all servers share same components.

* **Diagram:** [Imgur link here]

---

### 3. Scale up

* **Infrastructure:**
  * Add a 2nd load balancer (HAProxy cluster)
  * Add a new server for scaling
  * Split components:
    * Separate web server(s)
    * Separate application server(s)
    * Separate database server(s)

* **Explanation:**
  * **Why added**: improves redundancy, avoids SPOF, supports scaling.

* **Diagram:** [Imgur link here]

---

## 📂 Repository Structure
---

## 🚀 Notes

* All diagrams should be exported (PNG/JPEG) and uploaded to **Imgur**.
* Replace `[Imgur link here]` with your uploaded diagram links.
* Be ready to **whiteboard** these designs during review/interview sessions.
