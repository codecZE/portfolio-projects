# Network Defense & Prevention Matrix

| Attack Vector | Detection Tool | Defensive Mechanism | Action Plan |
| :--- | :--- | :--- | :--- |
| **Port Scanning (SYN Scan)** | Snort NIDS (SID 1000001) | Firewall Rate Limiting | Dynamic drop rule execution via IPS inline hook |
| **C2 Beaconing (HTTP)** | Zeek Log Extraction | Web Proxy & Egress Filter | Block remote domain/IP at perimeter proxy |
| **Unauthorized Protocol Usage** | Zeek `conn.log` | Network Segmentation | Isolate internal vLANs & restrict non-standard outbound ports |
