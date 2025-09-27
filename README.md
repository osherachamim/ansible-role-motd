# ansible-role-motd
An Ansible role that renders a friendly, informative **MOTD** (`/etc/motd`) on Linux servers.
Shows hostname, IP, OS, kernel, CPU, RAM, disk usage and **last reboot** time. Idempotent by design.

## Features
- Dynamic MOTD via Jinja2 template
- Host/IP/OS/Kernel/Uptime/CPU/RAM
- Disk usage (common mounts only)
- Last reboot time (`who -b`)
- Safe to run multiple times

## Requirements
- Ansible control node with SSH access to targets
- Python 3 on targets (Ansible requirement)
- `become` (sudo) permissions to write `/etc/motd`

## Inventory example
```ini
[k8s_workers]
k8s-worker1 ansible_host=<ipv4> ansible_user=osboxes ansible_ssh_private_key_file=<path_to_ssh_key>
k8s-worker2 ansible_host=<ipv4> ansible_user=osboxes ansible_ssh_private_key_file=<path_to_ssh_key>
