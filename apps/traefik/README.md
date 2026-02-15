# Traefik

Reverse proxy and SSL termination with Let's Encrypt and Cloudflare DNS challenge support.

## Services

| Service | Image |
|---------|-------|
| traefik | `traefik:latest` |

## Ports

| Host | Container | Description |
|------|-----------|-------------|
| 80 | 80 | HTTP (redirects to HTTPS) |
| 443 | 443 | HTTPS |
| 9489 | 9489 | Metrics |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/etc/localtime` | `/etc/localtime` | System time (read-only) |
| `/var/run/docker.sock` | `/var/run/docker.sock` | Docker socket (read-only) |
| `/home/kyle/appdata/traefik/data/traefik.yml` | `/traefik.yml` | Main config (read-only) |
| `/home/kyle/appdata/traefik/data/acme.json` | `/acme.json` | Let's Encrypt certificates |
| `/home/kyle/appdata/traefik/data/config.yml` | `/config.yml` | Dynamic config (read-only) |

## Secrets

| Secret | File Path | Description |
|--------|-----------|-------------|
| `cf_api_token` | `/home/kyle/appdata/traefik/cf_api_token.txt` | Cloudflare DNS API token |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik dashboard hostname |
| `DOMAIN_MAIN` | Yes | Main domain for certificates |
| `DOMAIN_SANS` | Yes | SAN entries (e.g., `*.example.com`) |

## Networks

- `cn1` (external) - Shared Docker network for service routing
- `mv1` (external) - Macvlan network (static IP: 10.35.1.24)

## Links

- [Traefik](https://traefik.io/)
- [Documentation](https://doc.traefik.io/traefik/)
