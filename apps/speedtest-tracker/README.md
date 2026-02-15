# Speedtest Tracker

Automated internet speed test tracker with historical data and graphs.

## Services

| Service | Image |
|---------|-------|
| speedtest-tracker | `lscr.io/linuxserver/speedtest-tracker:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 8187 | 80 | Web UI (HTTP) |
| 8447 | 443 | Web UI (HTTPS) |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/speedtest/data` | `/config` | Application data |
| `/home/kyle/appdata/speedtest/keys` | `/config/keys` | SSL keys |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `SPEEDTEST_APP_KEY` | Yes | Laravel application key |

## Networks

No custom networks configured.

## Links

- [Speedtest Tracker](https://github.com/alexjustesen/speedtest-tracker)
- [Docker Image](https://docs.linuxserver.io/images/docker-speedtest-tracker)
