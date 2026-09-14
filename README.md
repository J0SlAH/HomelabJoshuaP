# Cybersecurity Homelab

Self-hosted lab for hands-on cybersecurity practice — offensive 
(exploitation, pentesting) and defensive (detection, forensics, 
blue team) work, built from bare-metal hardware with Proxmox VE 
as the hypervisor.

## Hardware
- Dell OptiPlex 7040 (SFF)
- 238GB SSD (Micron MTFDDAK256TBN-1A)

## Software
- Proxmox VE 9.2 (bare-metal hypervisor)

## Network Design
- vmbr0: management network, DHCP — Proxmox web UI access
- vmbr1: isolated lab network, no physical NIC attached — all 
  project VMs (offensive and defensive) live here, cut off from 
  the home network

## Planned Projects
- Offensive: Kali attacker VM, Metasploitable2/Juice Shop targets, 
  AD lab (GOAD)
- Defensive: Wazuh or Security Onion for detection, pfSense/OPNsense 
  + Suricata for network defense, honeypot (Cowrie)
