# opencode-launchd

LaunchAgent config for running OpenCode server on macOS.

## Prereqs
- OpenCode installed (binary: /opt/homebrew/bin/opencode)
- Tailscale optional for remote access

## Install
1) Copy plist:
   ```sh
   cp launchd/com.opencode.server.plist ~/Library/LaunchAgents/
   ```

2) Load:
   ```sh
   launchctl load -w ~/Library/LaunchAgents/com.opencode.server.plist
   ```

## Uninstall / Stop
```sh
launchctl unload -w ~/Library/LaunchAgents/com.opencode.server.plist
```

## Restart
```sh
launchctl kickstart -k gui/$(id -u)/com.opencode.server
```

## Logs
- ~/Library/Logs/opencode.log
- ~/Library/Logs/opencode.err.log

## Access
Local access is available at http://127.0.0.1:4096. For external access, set up Tailscale and use your tailnet IP or MagicDNS hostname.
