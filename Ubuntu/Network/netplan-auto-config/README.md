NetPlan Auto-Configuration Script
Overview
A Bash script that automatically generates NetPlan configuration based on current network settings. This tool simplifies network configuration on modern Linux systems using NetPlan, eliminating manual YAML file editing.

Features
🔍 Automatic Interface Detection: Scans all network interfaces (excluding loopback)

📊 IP Address Detection: Captures current IPv4 addresses with CIDR notation

🚪 Gateway Detection: Identifies default gateway interface and IP

🌐 DNS Discovery: Extracts nameservers from /etc/resolv.conf

🛣️ Route Management: Captures additional static routes

🔄 Smart Configuration:

Maintains existing static IP configurations

Enables DHCP on first connected interface if no static IP exists

Preserves gateway and DNS settings

💾 Automatic Backup: Creates timestamped backups of existing configurations

📋 Configuration Summary: Displays comprehensive network status after generation

Requirements
Linux distribution using NetPlan (Ubuntu 18.04+, Debian 10+, etc.)

Root privileges

ip command from iproute2 package

Networkd renderer (default for server installations)

Installation
bash
# Clone or download the script
wget https://raw.githubusercontent.com/hamidrezakr/Linux/refs/heads/main/Ubuntu/Network/netplan-auto-config/Script.sh

# Make executable
chmod +x netplan-auto-config.sh
Usage
bash
# Run with root privileges
sudo ./netplan-auto-config.sh
What It Does
Security Check: Verifies root privileges

Data Collection: Gathers current network configuration

Configuration Generation: Creates /etc/netplan/01-auto-config.yaml

Backup Creation: Backs up existing NetPlan config with timestamp

Summary Display: Shows network status and generated configuration

Generated Configuration Structure
yaml
network:
  version: 2
  renderer: networkd
  ethernets:
    eth0:
      dhcp4: false
      optional: true
      addresses:
        - 192.168.1.100/24
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses: [8.8.8.8, 8.8.4.4]
Apply Configuration
After running the script:

bash
# Apply the new configuration
sudo netplan apply

# Verify the configuration
sudo netplan try --timeout=30
Safety Features
✅ Non-destructive: Creates backups before overwriting

✅ Validation: Only modifies NetPlan files

✅ Permission Protection: Sets secure file permissions (600)

✅ Temporary Files: Uses secure temp files that are properly cleaned

Use Cases
System Migration: Quickly replicate network settings

Disaster Recovery: Restore network configuration

Documentation: Generate human-readable network configs

Testing: Create consistent network environments

Automation: Integrate into provisioning scripts

Output Examples
The script provides:

Backup location (if applicable)

Generated file path

Current network configuration summary

Routing table

Complete generated YAML configuration

Troubleshooting
bash
# Check current NetPlan configuration
sudo netplan get

# Debug network interface status
ip addr show
ip route show

# Test configuration without applying
sudo netplan try
Notes
Script prioritizes existing static configurations

Only processes IPv4 addresses (IPv6 support can be added)

Assumes networkd renderer (modify for NetworkManager if needed)

First connected interface gets DHCP if no static IP is configured

Warning
⚠️ Always test in a safe environment first
⚠️ Internet connection may be interrupted during netplan apply
⚠️ Review generated configuration before applying

Contributing
Feel free to submit issues or pull requests for:

IPv6 support

Additional network managers

Enhanced error handling

More configuration options

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

Maintainer: HamidrezaKR
Last Updated: 2025-12-04
Tested On: Ubuntu 24.04
