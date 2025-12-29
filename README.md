# Linux Scripts

A collection of powerful Linux system administration and maintenance scripts with modern, futuristic UI.

## Overview

This repository contains various bash scripts designed to automate and simplify common Linux system administration tasks. The flagship script features a beautiful cyberpunk-inspired terminal interface with comprehensive system maintenance and auto-repair capabilities.

## Scripts

### 🚀 System Maintenance & Optimization Tool - Futuristic Edition

The **updatesystem** script is a comprehensive system maintenance tool with a stunning terminal UI and extensive auto-fix capabilities.

#### ✨ Key Features

**🎨 Futuristic Interface**
- ASCII art logo with gradient effects
- Neon cyberpunk color palette (cyan, purple, pink, green)
- Animated progress bars with Unicode spinners
- Beautiful box-drawing characters
- Real-time operation feedback

**🔧 Auto-Fix Capabilities**
- ✓ Repairs broken package dependencies automatically
- ✓ Removes stale package manager locks
- ✓ Cleans old snap revisions
- ✓ Removes unused flatpak runtimes
- ✓ Clears thumbnail and system caches
- ✓ Trims journal logs to optimal size
- ✓ Removes old compressed log files
- ✓ Cleans temporary directories
- ✓ Removes crash reports
- ✓ Deletes broken symlinks system-wide
- ✓ Purges orphaned configuration files
- ✓ Restarts failed systemd services
- ✓ Fixes DNS configuration issues
- ✓ Enables preload for faster app startup

**⚡ Performance Optimizations**
- ✓ Optimizes swappiness for better responsiveness
- ✓ Configures dirty page writeback for SSDs
- ✓ Sets optimal I/O schedulers (none/noop for SSD, deadline for HDD)
- ✓ Enables automatic weekly SSD TRIM
- ✓ Clears system memory caches
- ✓ Analyzes and reports slow startup services

**💾 Drive Maintenance**
- ✓ Automatic SSD TRIM operations
- ✓ HDD defragmentation when needed (>15% fragmentation)
- ✓ SMART disk health monitoring
- ✓ I/O scheduler optimization per drive type

**📦 Package Management**
- ✓ Updates APT, Snap, and Flatpak packages
- ✓ Removes unnecessary packages automatically
- ✓ Cleans package caches
- ✓ Tracks and reports space freed

**🔍 Hardware Health Checks**
- ✓ SMART disk health status
- ✓ Firmware update availability
- ✓ System sensor monitoring
- ✓ Failed service detection and restart

**🧹 Deep System Cleanup**
- ✓ Thumbnail cache cleaning
- ✓ Old journal log removal
- ✓ Compressed log file cleanup
- ✓ Temporary file purging
- ✓ Crash report removal
- ✓ Broken symlink detection and removal

**📊 Detailed Reporting**
- ✓ Fixes applied counter
- ✓ Space freed tracker
- ✓ Issues found summary
- ✓ System health overview

**🛠️ Essential Utilities Installation**

The script automatically checks for and installs these essential tools if missing:
- `btop` - Modern resource monitor
- `htop` - Interactive process viewer
- `iotop` - I/O monitoring
- `ncdu` - Disk usage analyzer
- `smartmontools` - Disk health monitoring
- `lm-sensors` - Hardware sensors
- `powertop` - Power consumption analyzer
- `preload` - Application preloader
- `fwupd` - Firmware update manager
- `e2fsprogs` - Filesystem utilities
- `cpufrequtils` - CPU frequency tools
- `net-tools` - Network utilities

## Installation

### Quick Install (System-wide)

Install the script to your system:

```bash
# Clone the repository
git clone https://github.com/welpak/linuxScripts.git
cd linuxScripts

# Install system-wide
sudo cp scripts/updatesystem /usr/local/bin/updatesystem
sudo chmod +x /usr/local/bin/updatesystem
```

### Usage

Run the maintenance script:

```bash
# Interactive mode (default)
# Performs all maintenance + offers optional improvements
sudo updatesystem

# Non-interactive mode
# Skips optional post-scan prompts (great for automation)
sudo updatesystem --skip
# or
sudo updatesystem -s
```

### What to Expect

When you run the script, you'll see:

1. **🎨 Futuristic ASCII header** with gradient colors
2. **📊 Real-time progress bar** showing current operation
3. **🔧 Live operation feedback** as tasks complete
4. **✓ Success/warning/error indicators** for each action
5. **📈 Final summary report** with:
   - Number of fixes applied
   - Total space freed
   - Issues requiring attention
   - System health overview

## Features in Detail

### Automatic Fixes

The script automatically fixes common issues without user intervention:

- **Package System**: Repairs broken dependencies, removes locks
- **Storage**: Cleans caches, removes old logs, purges orphaned configs
- **Performance**: Optimizes kernel parameters, I/O schedulers
- **Services**: Restarts failed services, enables performance helpers
- **Network**: Fixes DNS configuration issues
- **Drives**: Optimizes schedulers, enables automatic TRIM

### Interactive Improvements

After the main scan, the script may offer optional improvements:

- Install Flatpak for additional application sources
- Enable UFW firewall for better security
- Other system-specific enhancements

### Safety Features

- ✓ Requires root privileges for system changes
- ✓ Non-destructive operations only
- ✓ Clear status reporting for all actions
- ✓ Automatic detection of file system types
- ✓ Safe handling of package manager locks

## Requirements

- **OS**: Debian/Ubuntu-based Linux distribution
- **Privileges**: Root/sudo access required
- **Shell**: Bash 4.0 or higher
- **Terminal**: 256-color support recommended for best visuals

## Advanced Usage

### Automation with Cron

Run maintenance automatically every week:

```bash
# Edit root's crontab
sudo crontab -e

# Add this line to run every Sunday at 3 AM
0 3 * * 0 /usr/local/bin/updatesystem --skip > /var/log/system-maintenance.log 2>&1
```

### Create an Alias

Add to your `~/.bashrc` or `~/.zsh rc`:

```bash
alias maintenance='sudo /usr/local/bin/updatesystem'
alias quickmaint='sudo /usr/local/bin/updatesystem --skip'
```

## Monitoring

Check what was done during last run:

```bash
# If you logged to a file
sudo tail -100 /var/log/system-maintenance.log

# Or just run the script - it shows real-time output
sudo updatesystem
```

## Troubleshooting

**Script fails to start:**
- Ensure you're using `sudo`
- Check bash version: `bash --version` (needs 4.0+)

**Colors not displaying correctly:**
- Ensure your terminal supports 256 colors
- Try a modern terminal: GNOME Terminal, Konsole, Alacritty, kitty

**Package operations fail:**
- The script will attempt to fix lock files automatically
- If issues persist, manually check: `sudo dpkg --configure -a`

## What Gets Optimized

### System Performance
- Swappiness set to 10 (desktop optimal)
- Dirty page ratio optimized for SSDs
- Memory caches cleared
- Preload enabled for faster app launches

### Storage Health
- SSDs: TRIM operations performed
- HDDs: Defragmentation if >15% fragmented
- I/O schedulers optimized per drive type
- Automatic weekly TRIM enabled

### Package System
- All package managers updated (APT/Snap/Flatpak)
- Unnecessary packages removed
- Orphaned configs purged
- Broken dependencies fixed
- Old snap revisions cleaned

### System Cleanliness
- Thumbnail caches cleared
- Old logs removed (>7 days)
- Journal logs trimmed (kept to 7 days/500MB)
- Crash reports removed
- Temporary files cleaned
- Broken symlinks deleted

## Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Ideas for Contributions
- Additional system checks
- More auto-fix capabilities
- Support for other package managers (DNF, Pacman, etc.)
- Backup functionality before major changes
- Email notifications for issues found

## License

This project is provided as-is for system administration purposes. Feel free to modify and distribute.

## Changelog

### v2.0 - Futuristic Edition
- 🎨 Complete UI redesign with cyberpunk aesthetics
- 🔧 Added 25+ automatic fix capabilities
- ⚡ Enhanced performance optimizations
- 🧹 Deep system cleanup features
- 📊 Comprehensive tracking (fixes applied, space freed, issues found)
- 🛠️ Auto-installation of essential utilities
- 🎯 Better progress visualization
- ✨ Gradient colors and modern Unicode graphics

### v1.0 - Initial Release
- Basic APT package updates
- Simple drive maintenance
- Hardware checks
- System optimization

---

**Made with ❤️ for the Linux community**

*Keep your system running smooth and fast! 🚀*
