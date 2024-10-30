# LFCS Complete Exam Preparation Guide

## Missing Critical Topics

### 1. Advanced Storage Management
- RAID Configuration
```bash
# Software RAID
mdadm --create /dev/md0 --level=5 --raid-devices=3 /dev/sd[bcd]1
mdadm --detail /dev/md0
```
- Encrypted Volumes
```bash
# LUKS Encryption
cryptsetup luksFormat /dev/sdb1
cryptsetup luksOpen /dev/sdb1 encrypted_volume
```
- Quota Management
```bash
# User/Group Quotas
quotacheck -ugm /home
edquota -u username
```

### 2. Network Security
- Firewall Configuration
```bash
# UFW Management
ufw default deny incoming
ufw allow ssh
ufw enable
```
- SSH Hardening
```bash
# SSH Security
vi /etc/ssh/sshd_config
PermitRootLogin no
PasswordAuthentication no
```

### 3. Container Management
```bash
# LXC/LXD
lxc launch ubuntu:20.04 container1
lxc exec container1 bash
lxc list
```

### 4. System Monitoring
```bash
# Performance Tools
sar -u 1 10
iostat -xz 1
vmstat 1
```

### 5. Task Automation
```bash
# Systemd Timers
systemctl list-timers
systemd-run --on-calendar="*:0/15" command
```

### 6. Backup Solutions
```bash
# Rsync Backups
rsync -avz --progress /source /destination
rsync -e ssh /data user@remote:/backup
```

### 7. Network Troubleshooting
```bash
# Advanced Tools
tcpdump -i any port 80
netstat -tupln
ss -tulpn
```

## Updated Directory Structure
```
/
├── storage/
│   ├── raid_setup/
│   ├── encryption/
│   └── quotas/
├── security/
│   ├── firewall/
│   ├── ssh/
│   └── audit/
├── containers/
│   ├── lxc/
│   └── docker/
├── monitoring/
│   ├── performance/
│   └── logging/
└── automation/
    ├── systemd/
    └── cron/
```

## Additional Lab Requirements
- Third VM for clustering exercises
- Minimum 30GB storage for container practice
- Multiple network interfaces
- External storage for backup practice

## Updated Assessment Methods
- Real-time troubleshooting scenarios
- System recovery exercises
- Performance optimization tasks
- Security audit practice
- Network debugging challenges

## Exam Tips
- Time management (2 hours total)
- Read all tasks before starting
- Verify all changes persist after reboot
- Document important commands
- Practice without GUI tools
