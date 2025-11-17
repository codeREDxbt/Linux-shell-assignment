# Linux Shell Scripting Assignment

## Student Information

- **Name:** Vinayak
- **Roll Number:** 2501730150
- **Section:** C
- **Program:** B.Tech AI & ML
- **Course:** Computer Science Fundamentals & Career Pathways (ETCCCP105)
- **Submission Date:** November 2025

## Project Overview

This project demonstrates practical Linux command-line skills and shell scripting automation for system administration and DevOps workflows. It includes comprehensive documentation of essential Linux commands and three production-ready shell scripts that solve real-world problems in backup management, system monitoring, and automated file downloads.

**Key Learning Outcomes:**
- Mastered 25+ essential Linux commands across file management, permissions, process monitoring, and networking
- Developed three robust shell scripts with error handling and validation
- Applied automation techniques used in professional AI/ML and cloud computing environments
- Gained hands-on experience with WSL2 (Windows Subsystem for Linux)

## Repository Contents

### Documentation

- `Linux Assignment Report.docx` - Detailed report (4-6 pages) with real-world applications

### Shell Scripts

The three scripts below are included in the documentation with full source code.

## Script Descriptions

### 1. Directory Backup Script (`backup_directory.sh`)

**Purpose:** Creates timestamped backups of directories for version control and disaster recovery.

**Features:**
- Validates source directory existence before backup
- Creates backup destination automatically if it doesn't exist
- Generates timestamps in format: `backup_YYYY-MM-DD_HH-MM-SS`
- Reports backup size and success/failure status
- Includes comprehensive error handling with exit codes

**Real-World Use Case:** Daily backups of project files (like Blockademia blockchain platform) before deploying updates, preventing data loss from accidental deletions or failed deployments.

**How to Run:**
```bash
# Make script executable (first time only)
chmod +x backup_directory.sh

# Run the backup
./backup_directory.sh /path/to/source /path/to/backup/location

# Example
./backup_directory.sh ~/projects ~/backups
```

**Expected Output:**
```
✓ Backup successful: /home/user/backups/backup_2025-11-17_22-30-15 (125M)
```

---

### 2. System Resource Monitor (`monitor_resources.sh`)

**Purpose:** Continuously monitors and logs CPU usage, memory consumption, and process counts at regular intervals.

**Features:**
- Configurable log file name (default: `system.log`)
- Adjustable monitoring interval in seconds (default: 10 seconds)
- Logs timestamped snapshots with CPU percentage, memory details, and active processes
- Runs continuously until stopped with Ctrl+C
- Useful for tracking performance during intensive operations

**Real-World Use Case:** Monitoring server resources during machine learning model training to identify bottlenecks, detect memory leaks, or optimize resource allocation.

**How to Run:**
```bash
# Make script executable (first time only)
chmod +x monitor_resources.sh

# Run with defaults (system.log, 10-second intervals)
./monitor_resources.sh

# Run with custom log file and 5-second intervals
./monitor_resources.sh performance.log 5

# Stop monitoring with Ctrl+C
```

**Expected Output (in log file):**
```
[2025-11-17 22:30:15]
CPU: 15.2%
Memory: Used: 5.2G / Total: 8.0G
Processes: 247
---
```

---

### 3. Automated Download Script (`automated_download.sh`)

**Purpose:** Downloads files from the internet with automatic retry logic and integrity verification.

**Features:**
- Validates URL format (must start with http:// or https://)
- Creates destination directory automatically
- Implements retry mechanism (3 attempts with 5-second delays)
- Includes 10-second timeout protection per attempt
- Verifies downloaded file exists and isn't empty (0 bytes)
- Reports file size on successful download

**Real-World Use Case:** Automated downloading of datasets, blockchain libraries, or model weights for AI/ML projects with reliability during unstable network connections.

**How to Run:**
```bash
# Make script executable (first time only)
chmod +x automated_download.sh

# Download a file
./automated_download.sh https://example.com/dataset.zip ./downloads/

# Example with real URL
./automated_download.sh https://github.com/user/repo/archive/main.zip ./projects/
```

**Expected Output:**
```
Attempt 1/3: Downloading main.zip...
✓ Download successful: ./projects/main.zip (2.3M)
```

**Error Handling:**
```
Attempt 1/3: Downloading file.zip...
Retrying in 5 seconds...
Attempt 2/3: Downloading file.zip...
✗ Download failed after 3 attempts
```

## Prerequisites

**Linux Environment:**
- Ubuntu 22.04 LTS (WSL2 on Windows) or any Linux distribution
- Bash shell (version 4.0+)

**Required Tools:**
- `wget` - for downloading files
- `top` - for CPU monitoring
- `free` - for memory monitoring
- `du` - for disk usage reporting

**Install missing tools (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install wget procps coreutils
```

## General Instructions

### Making Scripts Executable

Before running any script for the first time:
```bash
chmod +x script_name.sh
```

### Script Location

Place scripts in a directory included in your PATH, or run them with `./` prefix from their current directory.

### Stopping Long-Running Scripts

- **Monitor script:** Press `Ctrl+C` to stop logging
- **Download script:** Press `Ctrl+C` to cancel (will attempt to retry if not all attempts exhausted)

### Viewing Logs

```bash
# View monitoring logs in real-time
tail -f system.log

# View entire log file
cat system.log
```

## Skills Demonstrated

- **Linux Command Mastery:** File navigation, permissions, process management, networking
- **Shell Scripting:** Variable handling, conditionals, loops, error handling
- **Automation:** Replacing manual tasks with reliable scripts
- **Error Handling:** Input validation, exit codes, retry logic
- **Real-World Application:** Solutions for backup, monitoring, and data pipeline automation


