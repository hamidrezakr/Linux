# Essential Linux Tools Installer
Overview
A comprehensive Bash script for installing essential Linux tools across multiple categories: security, monitoring, networking, system management, and more. Designed for Debian-based distributions (Ubuntu, Debian, etc.).

Features
🛡️ Security & Protection: Fail2ban, UFW, AIDE, Lynis, and more

📊 Monitoring & Observability: Real-time system monitoring tools

🌐 Networking: Network analysis, diagnostics, and testing tools

💾 File & Disk Management: Disk utilities and file management tools

🔧 Development Tools: Essential development packages and utilities

🖥️ System Management: Advanced system administration tools

📦 Package Management: Enhanced package management utilities

⏱️ Time Synchronization: Accurate timekeeping with Chrony

☁️ Virtualization: VMware/Open virtualization tools

Prerequisites
Debian-based Linux distribution (Ubuntu, Debian, etc.)

Root or sudo privileges

Active internet connection

Installation & Usage
1. Download the Script
bash
wget https://raw.githubusercontent.com/hamidrezakr/Linux/refs/heads/main/Ubuntu/Essential%20Linux%20Tools%20for%20System%20Administration/install-essential-tools.sh
2. Make Executable
bash
chmod +x install-essential-tools.sh
3. Run the Script
bash
## Run with sudo
sudo ./install-essential-tools.sh

## Or if you're already root
./install-essential-tools.sh
Installation Options
Install All Categories (Default)
bash
sudo ./install-essential-tools.sh --all
Install Specific Categories
bash
## Security tools only
sudo ./install-essential-tools.sh --security

## Monitoring tools only
sudo ./install-essential-tools.sh --monitoring

## Networking tools only
sudo ./install-essential-tools.sh --networking

## Multiple categories
sudo ./install-essential-tools.sh --security --networking --monitoring
Other Options
bash
## Show help
sudo ./install-essential-tools.sh --help

## Dry run (show what would be installed)
sudo ./install-essential-tools.sh --dry-run

## Skip apt update
sudo ./install-essential-tools.sh --no-update
Categories & Tools
🛡️ Security & Protection Tools
fail2ban: Intrusion prevention software

ufw: Uncomplicated Firewall

iptables-persistent: Firewall rule persistence

rkhunter: Rootkit hunter

auditd: Linux audit daemon

aide: Advanced Intrusion Detection Environment

lynis: Security auditing tool

nmap: Network discovery and security auditing

ssh-import-id: Import SSH keys from Launchpad/GitHub

📊 Monitoring & Observability Tools
atop: Advanced system and process monitor

htop: Interactive process viewer

iotop: I/O monitoring tool

sysstat: Performance monitoring tools (sar, iostat)

glances: Cross-platform monitoring tool

nmon: AIX & Linux performance monitor

multitail: Monitor multiple log files

logwatch: Log analyzer and reporter

🌐 Networking & Communication Tools
arping: Send ARP requests to a neighbor host

dnsutils: DNS utilities (dig, nslookup)

ethtool: Display or change Ethernet settings

iftop: Display bandwidth usage

iptraf: IP network monitoring tool

mtr: Network diagnostic tool

tcpdump: Command-line packet analyzer

traceroute: Print network route packets take

iperf3: Network bandwidth measurement

netcat-openbsd: TCP/IP swiss army knife

speedtest-cli: Internet bandwidth tester

bridge-utils: Ethernet bridge configuration

💾 File & Disk Management Tools
gdisk: GPT partition table manipulator

ncdu: Disk usage analyzer with ncurses interface

xfsprogs: XFS filesystem utilities

mlocate: Quickly find files on the filesystem

rsync: Fast, versatile file copying tool

tree: Display directory tree structure

🔧 Development & System Tools
build-essential: Essential packages for compiling software

curl: Command-line tool for transferring data with URLs

wget: Non-interactive network downloader

vim: Advanced text editor

tmux: Terminal multiplexer

screen: Full-screen window manager

less: Better file pager

🖥️ System Management Tools
lsof: List open files

lsb-release: Linux Standard Base version reporting

dlocate: Fast alternative to dpkg -L and dpkg -S

net-tools: NET-3 networking toolkit (ifconfig, netstat)

iproute2: Advanced IP routing and network configuration

whois: Client for the whois directory service

📦 Package & Repository Management
apt-transport-https: APT transport for downloading via HTTPS

dirmngr: GNU privacy guard - certificate management

apt-file: APT package searching utility

debian-goodies: Small toolbox-style utilities

⏱️ Time Synchronization
chrony: Versatile implementation of NTP

☁️ Virtualization Tools
open-vm-tools: Open VMware tools for guest operating systems

👁️‍🗨️ Browsing & Access
links: Text-mode WWW browser

Customization
Edit the Script
You can modify the script to:

Add additional tools

Remove tools you don't need

Change installation parameters

Add custom repositories

Create a Custom Configuration File
bash
## Create a custom tools list
cat > my-tools.conf << EOF
## My custom tool selection
htop
vim
curl
wget
nmap
EOF

## Run with custom configuration
sudo ./install-essential-tools.sh --config my-tools.conf
Verification
After installation, verify some key tools:

bash
## Check fail2ban status
sudo systemctl status fail2ban

## Test nmap
nmap --version

## Verify htop installation
htop --version

## Check UFW status
sudo ufw status
Troubleshooting
Common Issues
Package not found errors:

bash
sudo apt update
sudo apt install --fix-missing
Permission errors:
Ensure you're running with sudo or as root

Network issues:
Check your internet connection and DNS settings

Disk space issues:

bash
df -h
sudo apt clean
Logs
Check installation logs:

bash
## View apt history
cat /var/log/apt/history.log

## Check system logs
journalctl -xe
Script Maintenance
Update the Script
bash
## Fetch latest version
wget -O install-essential-tools.sh https://raw.githubusercontent.com/HamidrezaKR/linux-tools-installer/main/install-essential-tools.sh
chmod +x install-essential-tools.sh
## Remove Tools
To remove specific tools:

bash
sudo apt remove --purge <package-name>
Security Considerations
⚠️ Important Security Notes:

Review all security tools configurations after installation

Configure UFW rules appropriately for your environment

Set up fail2ban jail configurations

Update AIDE database after installation: sudo aideinit

Run Lynis audit: sudo lynis audit system

## Contributing
Feel free to:

Fork the repository

Create a feature branch

Submit a pull request

Report issues or suggest improvements

## License
Apache License 2.0

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

### Author
HamidrezaKR

GitHub: @HamidrezaKR

Created: November 2025

### Support
If you find this script useful:

⭐ Star the repository

🐛 Report issues

🔄 Share with others

💡 Suggest improvements

