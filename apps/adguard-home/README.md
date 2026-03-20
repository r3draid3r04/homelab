# AdGuard Home

Network-wide DNS-based ad blocker and privacy protection with a web dashboard.

## Services

| Service | Image |
|---------|-------|
| adguardhome | `adguard/adguardhome` |

## Ports

| Host | Container | Protocol | Description |
|------|-----------|----------|-------------|
| 53 | 53 | TCP/UDP | DNS |
| 67 | 67 | UDP | DHCP server |
| 68 | 68 | UDP | DHCP client |
| 80 | 80 | TCP | HTTP (initial setup / redirect) |
| 443 | 443 | TCP/UDP | HTTPS |
| 3000 | 3000 | TCP | Web UI (initial setup) |
| 853 | 853 | TCP/UDP | DNS-over-TLS |
| 5443 | 5443 | TCP/UDP | DNS-over-QUIC |
| 6060 | 6060 | TCP | Debug / pprof |

## Volumes

| Host Path | Container Path | Description |
|-----------|---------------|-------------|
| `/my/own/workdir` | `/opt/adguardhome/work` | Working directory (filters, database) |
| `/my/own/confdir` | `/opt/adguardhome/conf` | Configuration files |

> Update the host paths in `compose.yaml` to match your preferred storage location.

## Networks

- `mv1` (external, macvlan) — Static IP `192.168.1.10` assigned for DNS access from the host network

## Notes

- A macvlan network is used so AdGuard Home can bind port 53 without conflicting with the host.
- After first launch, complete setup at `http://<host-ip>:3000`.

## Links

- [AdGuard Home](https://adguard.com/adguard-home.html)
- [GitHub](https://github.com/AdguardTeam/AdGuardHome)
