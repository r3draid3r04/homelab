# VPN Services

VPN-routed service stack using Gluetun as a gateway, with Cyberdrop-DL and Mullvad Browser running through the VPN tunnel.

## Services

| Service | Image |
|---------|-------|
| gluetun | `qmcgaw/gluetun` |
| cyberdrop-dl | `registry.kylerockwell.dev/docker/cyberdrop-dl:latest` |
| mullvad-browser | `lscr.io/linuxserver/mullvad-browser:latest` |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| 8887 | 8888 | gluetun | HTTP proxy |
| 8388 | 8388 TCP/UDP | gluetun | Shadowsocks |
| 3002 | 3001 | gluetun | Mullvad Browser web UI |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `${APPDATA_PATH}/gluetun` | `/gluetun` | Gluetun config and server list |
| `${APPDATA_PATH}/cyberdrop-dl` | `/app` | Cyberdrop-DL config and state |
| `cyberdrop_dl` (external) | `/downloads` | Download destination |
| `${APPDATA_PATH}/mullvad-browser/config` | `/config` | Browser profile |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `APPDATA_PATH` | Yes | Base path for application data |
| `TZ` | Yes | Timezone (e.g., `America/Chicago`) |
| `VPN_SERVICE_PROVIDER` | Yes | VPN provider (e.g., `mullvad`) |
| `VPN_TYPE` | Yes | VPN protocol (e.g., `wireguard`) |
| `WIREGUARD_PRIVATE_KEY` | Yes | WireGuard private key |
| `WIREGUARD_ADDRESSES` | Yes | WireGuard assigned addresses |
| `SERVER_CITIES` | No | Preferred server cities (e.g., `Chicago`) |

## Notes

- `cyberdrop-dl` and `mullvad-browser` both use `network_mode: "service:gluetun"` — all traffic is routed through the VPN.
- Both non-gluetun containers have `restart: "no"` — they are designed to be started manually.
- The `cyberdrop_dl` volume must exist as an external Docker volume before starting.
- Gluetun auto-updates its VPN server list every 24 hours.

## Links

- [Gluetun](https://github.com/qdm12/gluetun)
- [Cyberdrop-DL](https://cyberdrop.me/)
- [Mullvad Browser (linuxserver)](https://docs.linuxserver.io/images/docker-mullvad-browser/)
