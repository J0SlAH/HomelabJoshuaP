# Day 1 — Install & Network Config

- Enabled VT-x/VT-d in BIOS
- Built installer USB (Rufus, DD mode — required for Proxmox's 
  ISOHybrid image)
- Installed Proxmox VE 9.2 (238GB SSD, ext4, full disk)
- **Issue:** installer auto-filled an unreachable static IP (no 
  cable connected during setup). Fixed by switching `vmbr0` to DHCP 
  in `/etc/network/interfaces`, confirmed lease via 
  `journalctl -u networking`.
- **Issue:** `apt full-upgrade` silently failed — pve-enterprise 
  and ceph-squid repos both needed disabling (missed the second on 
  first pass). Added pve-no-subscription, upgrade completed clean.
- Created `vmbr1`: isolated bridge, no physical NIC, for lab VMs.
