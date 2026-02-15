# FileBot

Media file organizer and renamer with a web-based UI.

## Services

| Service | Image |
|---------|-------|
| filebot | `jlesage/filebot` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 5801 | 5800 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/filebot/config` | `/config` | Configuration files |
| `media_share` (external) | `/storage` | Media storage |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [FileBot](https://www.filebot.net/)
- [Docker Image](https://hub.docker.com/r/jlesage/filebot)
