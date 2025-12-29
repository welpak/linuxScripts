# Linux Scripts

A collection of useful Linux system administration and maintenance scripts.

## Overview

This repository contains various bash scripts designed to automate and simplify common Linux system administration tasks.

## Scripts

### System Maintenance

- **updatesystem** - Comprehensive system maintenance script with modern terminal UI
  - Automatically updates APT, Snap, and Flatpak packages
  - Performs drive maintenance (SSD TRIM, HDD defragmentation)
  - Checks hardware health and firmware updates
  - Optimizes system settings
  - Generates detailed maintenance reports
  - Includes interactive post-scan actions for optional improvements

## Installation

### Quick Install (System-wide)

To install the updatesystem script system-wide:

```bash
sudo cp scripts/updatesystem /usr/local/bin/updatesystem
sudo chmod +x /usr/local/bin/updatesystem
```

### Usage

Run the system maintenance script:

```bash
# Interactive mode (with optional post-scan actions)
sudo updatesystem

# Non-interactive mode (skip optional actions)
sudo updatesystem --skip
```

## Features

- **Modern Terminal UI** - Beautiful progress bars, color-coded status indicators, and real-time feedback
- **Comprehensive Maintenance** - Updates packages, cleans caches, optimizes system settings
- **Hardware Monitoring** - Checks CPU, drives, sensors, and firmware status
- **Smart Drive Care** - Automatic SSD TRIM and HDD defragmentation when needed
- **Detailed Reports** - Color-coded summary of all maintenance actions performed
- **Safety First** - Non-destructive operations with clear status reporting

## Requirements

- Root/sudo privileges
- Debian/Ubuntu-based Linux distribution
- Bash 4.0 or higher

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## License

This project is provided as-is for system administration purposes.
