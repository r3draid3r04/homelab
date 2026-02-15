# What's Up Docker

Docker container update notifier with MQTT and Home Assistant integration.

## Services

| Service | Image |
|---------|-------|
| whatsupdocker | `getwud/wud` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 3007 | 3000 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/var/run/docker.sock` | `/var/run/docker.sock` | Docker socket |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `MQTT_BROKER_URL` | Yes | MQTT broker URL |
| `MQTT_BROKER_USER` | Yes | MQTT username |
| `MQTT_BROKER_PASSWORD` | Yes | MQTT password |
| `WUD_REGISTRY_URL` | Yes | Private Docker registry URL |
| `WUD_REGISTRY_USER` | Yes | Registry username |
| `WUD_REGISTRY_PASSWORD` | Yes | Registry password |

## Networks

- `cn1` (external) - Shared Docker network

## Links

- [What's Up Docker](https://getwud.github.io/wud/)
- [GitHub](https://github.com/getwud/wud)
