# Krokiet

Cross-platform file manager with a web-based UI for browsing and managing remote storage.

## Services

| Service | Image |
|---------|-------|
| krokiet | `jlesage/krokiet` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 5808 | 5800 | Web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `${APPDATA_PATH}/krokiet` | `/config` | Configuration files |
| `synology-private` (external volume) | `/storage` | Remote storage to browse |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `APPDATA_PATH` | Yes | Base path for application data |

## Notes

- The `synology-private` volume must be created externally before starting (e.g., an NFS or CIFS mount defined as a Docker volume).
- Access the web UI at `http://<host-ip>:5808`.

## Links

- [jlesage Docker Images](https://github.com/jlesage/docker-baseimage-gui)
