# Scrypted

Home video integration platform with hardware acceleration and automatic updates via Watchtower.

## Services

| Service | Image | Description |
|---------|-------|-------------|
| scrypted | `ghcr.io/koush/scrypted` | Video integration platform |
| watchtower | `containrrr/watchtower` | Automatic container updates |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| (host network) | - | scrypted | Uses host network mode |
| 10444 | 8080 | watchtower | Update API |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `./volume` | `/server/volume` | Scrypted data |
| `/var/run/docker.sock` | `/var/run/docker.sock` | Docker socket for Watchtower |

## Devices

- `/dev/dri` - GPU passthrough for hardware acceleration

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `WATCHTOWER_HTTP_API_TOKEN` | Yes | - | Watchtower API authentication token |
| `WATCHTOWER_HTTP_API_PERIODIC_POLLS` | No | `true` | Enable periodic update polling |

## Networks

- Scrypted uses host network mode
- Watchtower uses default bridge

## Links

- [Scrypted](https://www.scrypted.app/)
- [GitHub](https://github.com/koush/scrypted)
