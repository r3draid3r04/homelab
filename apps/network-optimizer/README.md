# Network Optimizer

Network performance monitoring and optimization tool with speed testing, path analysis, and agent-based device management.

## Services

| Service | Image |
|---------|-------|
| network-optimizer | `ghcr.io/ozark-connect/network-optimizer:latest` |
| network-optimizer-speedtest | `ghcr.io/ozark-connect/speedtest:latest` |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| 8042 | 8042 | network-optimizer | Web UI / API (host network) |
| `${OPENSPEEDTEST_PORT:-3005}` | 3000 | network-optimizer-speedtest | OpenSpeedTest UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `./data` | `/app/data` | SQLite database, configs, license |
| `./ssh-keys` | `/app/ssh-keys` | SSH keys for agent deployment (optional) |
| `./logs` | `/app/logs` | Application logs |

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `TZ` | No | `America/Chicago` | Timezone |
| `BIND_LOCALHOST_ONLY` | No | `false` | Bind to `127.0.0.1` only (for reverse proxy on same host) |
| `APP_PASSWORD` | No | auto-generated | Admin password (visible in logs on first run) |
| `HOST_IP` | No | — | Server IP for speed test path analysis and CORS |
| `HOST_NAME` | No | — | Server hostname for canonical URL enforcement |
| `REVERSE_PROXIED_HOST_NAME` | No | — | Hostname behind reverse proxy (e.g., `optimizer.example.com`) |
| `OPENSPEEDTEST_PORT` | No | `3005` | Port for the OpenSpeedTest container |
| `OPENSPEEDTEST_HOST` | No | `HOST_NAME` | Hostname for OpenSpeedTest if different from main app |
| `OPENSPEEDTEST_HTTPS` | No | `false` | Set to `true` when speedtest is behind a TLS proxy |
| `IPERF3_SERVER_ENABLED` | No | `false` | Enable iperf3 server on port 5201 |
| `LOG_LEVEL` | No | `Information` | Framework log level |
| `APP_LOG_LEVEL` | No | `Information` | Application log level |

## Notes

- Runs in `network_mode: host` for accurate path analysis and iperf3 binding.
- The speed test and main app **must** use separate reverse proxy hostnames if TLS is used — the speed test requires HTTP/1.1 while the main app requires HTTP/2+.
- On first run, the auto-generated admin password is printed to container logs.

## Links

- [Network Optimizer](https://github.com/ozark-connect/network-optimizer)
