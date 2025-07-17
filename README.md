#Purple Hat Project — Home Lab Exploitation & Monitoring

This is a hands-on cybersecurity project simulating real-world red team tactics and defensive monitoring in a controlled lab environment. It was designed to improve offensive security skills and build out a full kill chain with detection and logging.

---

## Lab Setup

| Role     | OS             | Tools                            |
|----------|----------------|----------------------------------|
| Attacker | Kali Linux     | Nmap, Netcat, Python, Reverse Shell |
| Victim   | Ubuntu Server  | OpenSSH, Filebeat                |
| Monitor  | Same as victim or separate VM | Elasticsearch + Filebeat |

---

## 🧠 Project Objectives

- Set up a vulnerable Linux environment
- Simulate attacks from a custom Linux attacker
- Gain reverse shell access through bash payload
- Stabilize the shell with Python
- Attempt privilege escalation without known credentials
- Set up Filebeat and Elasticsearch to capture logs
- Analyze logs for intrusion activity (e.g. `sshd`, `Failed password`)

---

## 💣 Attack Flow Summary

1. Nmap used to discover victim machine services
2. Bash reverse shell payload executed from victim
3. Connection caught by Kali using `nc -lvnp`
4. Shell stabilized using Python TTY spawn + terminal reset
5. Attempted `sudo -l` to check for privilege escalation
6. All activity logged through Filebeat ➝ Elasticsearch

---

## 📦 Tools Used

- Netcat
- Bash
- Python (for pty shell)
- Filebeat
- Elasticsearch
- curl (for log queries)
