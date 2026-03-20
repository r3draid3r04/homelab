# Kometa GUI

Web-based GUI for managing Kometa (formerly Plex Meta Manager) metadata and collections, with ImageMaid for cleaning up unused artwork.

## Services

| Service | Image |
|---------|-------|
| kometawebui | `registry.kylerockwell.dev/docker/kometawebui:latest` |
| kometa | `kometateam/kometa:nightly` |
| imagemaid | `kometateam/imagemaid` |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| 3333 | 3000 | kometawebui | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `${APPDATA_PATH}/kometawebui` | `/app/data` | GUI database and state |
| `${APPDATA_PATH}/kometa/configs` | `/app/data/configs` (kometawebui) | Kometa config files |
| `${APPDATA_PATH}/kometa/configs` | `/config` (kometa) | Kometa config files |
| `${APPDATA_PATH}/kometa/logs` | `/logs` | Kometa logs |
| `${APPDATA_PATH}/kometa/cache` | `/cache` | Kometa cache |
| `${APPDATA_PATH}/config` | `/config` (imagemaid) | ImageMaid configuration |
| `${APPDATA_PATH}/plex` | `/plex` | Plex library config for ImageMaid |

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `APPDATA_PATH` | Yes | — | Base path for application data |
| `DB_PATH` | No | `/app/data/kometa.db` | SQLite database path for GUI |
| `TZ` | No | — | Timezone (e.g., `America/Chicago`) |
| `KOMETA_CONFIG` | No | `/config/config.yml` | Path to Kometa config file |
| `KOMETA_TIME` | No | `06:00` | Daily run time for Kometa |
| `KOMETA_RUN` | No | `false` | Run Kometa on container start |
| `KOMETA_NO_MISSING` | No | `false` | Skip missing items processing |
| `KOMETA_NO_REPORT` | No | `false` | Skip report generation |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Kometa](https://kometa.wiki/)
- [ImageMaid](https://github.com/Kometa-Team/ImageMaid)
