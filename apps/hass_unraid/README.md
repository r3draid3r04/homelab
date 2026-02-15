# HASS Unraid

Custom Home Assistant integration for monitoring and controlling Unraid servers.

## Services

| Service | Image |
|---------|-------|
| hass-unraid | `registry.kylerockwell.dev/docker/hass-unraid:latest` |

## Ports

No ports exposed. Runs as a background service.

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/unraid/data` | `/data` | Application data |

## Environment Variables

No configurable environment variables. TZ is hardcoded to `America/Chicago`.

## Networks

- Bridge network mode
