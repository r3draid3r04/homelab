# r3draid3r04 Homelab

Docker Compose templates for a complete homelab setup, packaged as an [Arcane](https://github.com/getarcaneapp/arcane) template registry.

## About

This repository contains ready-to-deploy Docker Compose configurations for self-hosted services. Each app includes a `compose.yaml`, `.env.example`, and `README.md` with setup instructions. The `registry.json` at the root allows Arcane to discover and deploy these templates directly.

## Structure

```
apps/           # Individual application stacks
infra/          # Infrastructure services (monitoring, etc.)
registry.json   # Arcane template registry manifest
```

## Apps

| App | Description |
|-----|-------------|
| **AdGuard Home** | Network-wide DNS ad blocker and privacy protection |
| **AssetFlow** | Custom artwork management for Plex with TMDB/TVDB integration |
| **FileBot** | Media file organizer and renamer with web UI |
| **FreshRSS** | Self-hosted RSS feed aggregator |
| **Glances** | Real-time system monitoring with web UI |
| **HASS Unraid** | Home Assistant integration for Unraid servers |
| **Homepage** | Application dashboard with service integrations |
| **Immich** | Self-hosted photo/video management with ML features |
| **Immich Stacker** | Auto-stacks related photos in Immich (e.g., JPG + DNG pairs) |
| **ImmichStats** | Statistics dashboard for Immich |
| **Jellyfin** | Self-hosted media streaming server |
| **Kometa GUI** | Web GUI for Kometa (Plex Meta Manager) with ImageMaid |
| **Krokiet** | Web-based file manager for remote storage |
| **MediaScan** | Plex media library scanner and analyzer |
| **n8n** | Visual workflow automation platform |
| **Network Optimizer** | Network performance monitoring with speed testing and path analysis |
| **Nexus** | Sonatype Nexus Repository Manager for Docker images and artifacts |
| **Open WebUI** | Web interface for Ollama and other LLM backends |
| **Scrypted** | Home video integration platform with hardware acceleration |
| **Seerr** | Media request management (Jellyseerr) for Plex/Sonarr/Radarr |
| **Speedtest Tracker** | Automated internet speed test tracker with historical data |
| **Tracearr** | Activity tracker for *arr stack applications |
| **Traefik** | Reverse proxy with Let's Encrypt and Cloudflare DNS challenge |
| **Trilium** | Hierarchical note-taking with rich text and scripting |
| **Uptime Kuma** | Self-hosted uptime monitoring with notifications |
| **Vaultwarden** | Lightweight Bitwarden-compatible password manager |
| **VPN Services** | Gluetun VPN gateway with Cyberdrop-DL and Mullvad Browser |
| **VS Code Server** | Web-based VS Code via code-server |
| **What's Up Docker** | Docker container update notifier with MQTT/HA integration |

## Infrastructure

| Stack | Description |
|-------|-------------|
| **Monitoring** | Grafana, InfluxDB, Loki, Promtail, cAdvisor, SNMP exporter, syslog-ng |

## Usage with Arcane

Add this registry to Arcane by pointing it at the `registry.json`:

```
https://raw.githubusercontent.com/r3draid3r04/homelab/main/registry.json
```

From there, Arcane can browse, configure, and deploy any of the templates above.
