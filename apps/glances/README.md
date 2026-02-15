# Glances

Real-time system monitoring tool with a web UI for CPU, memory, disk, and network stats.

## Services

| Service | Image |
|---------|-------|
| glances | `nicolargo/glances:latest-full` |

## Ports

Uses host network mode. Web UI available on port 61208 by default.

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/var/run/docker.sock` | `/var/run/docker.sock` | Docker socket (read-only) |
| `/etc/os-release` | `/etc/os-release` | OS info (read-only) |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `TZ` | Yes | Timezone |

## Networks

- Host network mode

## Links

- [Glances](https://nicolargo.github.io/glances/)
- [GitHub](https://github.com/nicolargo/glances)
