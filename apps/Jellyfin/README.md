# Jellyfin

Self-hosted media streaming server for movies, TV shows, music, and more.

## Services

| Service | Image |
|---------|-------|
| jellyfin | `jellyfin/jellyfin` |

## Ports

| Host | Container | Protocol | Description |
|------|-----------|----------|-------------|
| 8096 | 8096 | TCP | Web UI / API |
| 7359 | 7359 | UDP | Local network autodiscovery |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `${APPDATA_PATH}/jellyfin/config` | `/config` | Configuration files |
| `${APPDATA_PATH}/jellyfin/cache` | `/cache` | Transcode cache |
| `${APPDATA_PATH}/jellyfin/media` | `/media` | Primary media library |
| `${APPDATA_PATH}/jellyfin/media2` | `/media2` | Secondary media library (read-only) |
| `${APPDATA_PATH}/jellyfin/fonts` | `/usr/local/share/fonts/custom` | Custom fonts for subtitle burn-in (read-only) |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `APPDATA_PATH` | Yes | Base path for application data |
| `JELLYFIN_PUBLISHED_SERVER_URL` | No | Public server URL for autodiscovery (e.g., `https://jellyfin.example.com`) |

## Networks

- `cn1` (external) - Shared Docker network

## Notes

- The `user: uid:gid` line in the compose file should be updated to match your system user.
- The `host.docker.internal` extra host entry may be needed for health checks in host network mode.

## Links

- [Jellyfin](https://jellyfin.org/)
- [GitHub](https://github.com/jellyfin/jellyfin)
