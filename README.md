# Log Every Session and Monitor Every Sudo

A comprehensive Linux monitoring system that logs user sessions and sudo activities, with a terminal-based interface for viewing logs.

## Features

- **Session Logging**:
  - Tracks login and logout events
  - Records all commands executed in the terminal
  - Timestamps each command

- **Sudo Monitoring**:
  - Logs who ran sudo commands
  - Records what command was executed with sudo
  - Captures when the command was executed
  - Tracks failed sudo attempts

- **Terminal-Based Interface**:
  - Blue-themed dialog interface similar to classic system tools
  - Numbered menu options for easy navigation
  - Select user and date from menus
  - View session and sudo logs
  - Search within logs
  - Export logs to external files
  - Delete old logs

### Terminal Interface

Run the terminal interface with:

\`\`\`
session-monitor-gui
\`\`\`

This will open a dialog-based interface where you can:
- Select a user
- Choose a date
- View session or sudo logs
- Search within logs
- Export logs to external files
- Delete old logs

### Log Files

Logs are stored in:
- Session logs: `/var/log/session_monitor/sessions/username_YYYYMMDD.log`
- Sudo logs: `/var/log/session_monitor/sudo/username_YYYYMMDD.log`

### Configuration

The main configuration file is located at:
\`\`\`
/opt/session_monitor/config/monitor.conf
\`\`\`

You can modify:
- Log directories
- Log retention period (default: 30 days)

## Security

- Log files are restricted with appropriate permissions (640)
- Only root can access the log directories
- The interface requires elevation to sudo when accessing logs

## Uninstallation

To remove the system:

\`\`\`
sudo ./uninstall.sh
\`\`\`

This will:
- Stop and disable services
- Remove all installed files
- Optionally keep or remove log files

## Requirements

- Bash
- Dialog (for terminal interface)
- Systemd
- Logger utility

