# Task 1: Lab Environment Setup and Initial Recon

## What I did
Set up an isolated Ubuntu VM using Vagrant/VirtualBox and deployed OWASP Juice Shop via Docker. Performed an Nmap scan from the `greenleaf-attacker` machine to document open ports (22 and 3000).

## What was hard
The most challenging part was ensuring the Docker container was properly exposed on Port 3000 and accessible from the attacker machine, as the Ubuntu UFW firewall was initially blocking the connection. I resolved this by explicitly allowing the port and verifying Docker bindings.

## What I left out
I skipped WSL2 and used Vagrant instead, as it provided a more reproducible, snapshot-capable, and isolated VirtualBox environment specifically tailored for penetration testing practice.

## Nmap Scan Details

- **Attacker Machine (Scanner):** Kali Linux VM (`greenleaf-attacker`)
- **Target Machine (Scanned):** Ubuntu VM (`greenleaf-web` at `192.168.56.10`)

The Nmap scan was executed **from** the Kali Linux attacker machine **against** the Ubuntu target machine to identify open ports and service versions.

> **Note:** Port 3000 is running **OWASP Juice Shop over HTTP**. Nmap labeled it as `ppp?` because it could not match the service to its signature database, but the fingerprint below confirms it is an HTTP service (Node.js Express).

*Proof of SSH accessibility to the target VM is provided in the `ssh_login_proof.txt` file in this repository.*
