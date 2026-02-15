# Kometa GUI

Web-based GUI for Kometa (formerly Plex Meta Manager) with Mediux integration for managing Plex metadata and collections.

## Services

| Service | Image | Description |
|---------|-------|-------------|
| kometagui | `registry.kylerockwell.dev/docker/kometagui:0.9.16` | Web GUI for Kometa |
| kometa | `kometateam/kometa:nightly` | Kometa metadata manager |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| 3005 | 3000 | kometagui | Frontend UI |
| 3001 | 3001 | kometagui | Backend API |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/kometa/configs` | `/config` | Kometa configuration |
| `/home/kyle/appdata/kometagui/cache` | `/cache` | GUI cache |
| `/home/kyle/appdata/kometagui/data` | `/data` | GUI database |
| `/home/kyle/appdata/kometa/logs` | `/logs` | Kometa logs |
| `/var/run/docker.sock` | `/var/run/docker.sock` | Docker socket (read-only) |

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `NODE_ENV` | No | `development` | Node environment |
| `PORT` | No | `3001` | Backend API port |
| `CONFIG_DIR` | No | `/config` | Config directory |
| `LOGS_DIR` | No | `/logs` | Logs directory |
| `LOG_LEVEL` | No | `info` | Log verbosity |
| `KOMETA_CONTAINER_NAME` | No | `kometa` | Docker container name to manage |
| `FRONTEND_URL` | No | `http://localhost:3000` | Frontend URL |
| `NEXT_PUBLIC_API_URL` | No | `http://localhost:3001` | Public API URL |
| `NEXT_PUBLIC_WS_URL` | No | `http://localhost:3001` | WebSocket URL |
| `MEDIUX_API_URL` | No | `https://staged.mediux.io/graphql` | Mediux GraphQL endpoint |
| `MEDIUX_API_TOKEN` | Yes | - | Mediux API token |
| `MEDIUX_ASSET_URL` | No | `https://staged.mediux.io/assets` | Mediux asset URL |
| `MEDIUX_CACHE_DIR` | No | `/cache/mediux` | Mediux cache directory |
| `MEDIUX_SYNC_INTERVAL` | No | `0 0 * * *` | Cron schedule for syncing |
| `DATABASE_URL` | No | `file:/data/dev.db` | SQLite database path |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Kometa](https://kometa.wiki/)
- [Mediux](https://mediux.io/)
