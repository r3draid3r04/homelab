# AssetFlow

Custom artwork management tool for Plex media libraries with TMDB and TVDB integration.

## Services

| Service | Image |
|---------|-------|
| assetflow | `registry.kylerockwell.dev/docker/assetflow:0.9.6` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 3032 | 3000 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `synology-plex-artwork` (external) | `/app/downloads` | Plex artwork storage |
| `/home/kyle/appdata/assetflow/uploads` | `/app/public/uploads` | User uploads |
| `/home/kyle/appdata/assetflow/prisma` | `/app/prisma` | SQLite database |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `TMDB_API_KEY` | Yes | TMDB API key for fetching artwork |
| `TVDB_API_KEY` | Yes | TVDB API key |
| `TVDB_PIN` | Yes | TVDB subscriber PIN |
| `PLEX_BASE_URL` | Yes | Plex server URL |
| `PLEX_TOKEN` | Yes | Plex authentication token |
| `HOSTNAME` | Yes | Traefik hostname |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [TMDB API](https://developer.themoviedb.org/)
- [TVDB API](https://thetvdb.com/api-information)
