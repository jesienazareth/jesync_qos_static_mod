# Jesync-LibreQoS-UpdateCSV

Welcome to the Jesync-LibreQoS-UpdateCSV repository. This Python script synchronizes MikroTik router data—specifically PPP secrets (PPPoE users) and active hotspot users—with a LibreQoS-compatible CSV file (`ShapedDevices.csv`). The script continuously monitors your routers for changes and automatically updates your network configuration, ensuring your bandwidth plans are kept up to date.

## Features

### Dynamic Device Synchronization:
- Fetches device information from MikroTik routers via API and updates the `ShapedDevices.csv` file accordingly.

### Bandwidth Override:
- With the new global option `UseProfileBandwidth` set in `jesync_static_device.json`, the script can override default profile-derived bandwidth settings by using a valid bandwidth value from the active connection’s comment (e.g., “20m/20m”).

### Custom Parent Nodes for Static Devices:
- Static device entries (configured in `jesync_static_device.json`) can now specify a custom "Parent Node", which allows you to group devices (e.g., "CoreDevices", "BackupDevices") in the LibreQoS network configuration.

### Automated Service:
- The script runs as a background service using systemd, ensuring continuous operation and automatic restarts if necessary.

## Requirements
- Linux-based system (Ubuntu, Debian, etc.)
- Python 3.6+
- pipx (for isolated installation of Python packages)
- routeros_api Python library (installed via pipx)
- Access to one or more MikroTik routers with API enabled
- LibreQoS installation that utilizes the `ShapedDevices.csv` file
- Basic familiarity with Linux command line and systemd

## Installation

### 1. Clone the Repository
Clone the repository to your local machine:

```bash
git clone https://github.com/jesienazareth/Jesync-LibreQoS-UpdateCSV.git
cd Jesync-LibreQoS-UpdateCSV
