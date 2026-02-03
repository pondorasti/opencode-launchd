# opencode-launchd

LaunchAgent config for running OpenCode server on macOS.

## Prereqs
- OpenCode installed (binary: /opt/homebrew/bin/opencode)
- Tailscale optional for remote access

## Install
1) Copy plist:
   cp launchd/com.opencode.server.plist ~/Library/LaunchAgents/

2) Load:
   launchctl load -w ~/Library/LaunchAgents/com.opencode.server.plist

## Uninstall / Stop
launchctl unload -w ~/Library/LaunchAgents/com.opencode.server.plist

## Logs
- ~/Library/Logs/opencode.log
- ~/Library/Logs/opencode.err.log

## Access
- Local: http://127.0.0.1:4096
- Tailscale: http://<tailscale-ip>:4096
