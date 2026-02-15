# Nexus

Sonatype Nexus Repository Manager for hosting Docker images and other artifacts.

## Services

| Service | Image |
|---------|-------|
| nexus3 | `sonatype/nexus3` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 8481 | 8081 | Nexus Web UI |
| 8089 | 8089 | Docker Registry |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/home/kyle/appdata/nexus/nexus_data` | `/nexus-data` | Repository data |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME_NEXUS` | Yes | Traefik hostname for Nexus UI |
| `HOSTNAME_NEXUS_REGISTRY` | Yes | Traefik hostname for Docker registry |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Sonatype Nexus](https://www.sonatype.com/products/sonatype-nexus-repository)
- [Docker Image](https://hub.docker.com/r/sonatype/nexus3)
