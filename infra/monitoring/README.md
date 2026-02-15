# Monitoring Stack

Full monitoring infrastructure with Grafana, InfluxDB, Loki, Promtail, cAdvisor, SNMP exporter, and syslog-ng.

## Services

| Service | Image | Description |
|---------|-------|-------------|
| grafana | `grafana/grafana` | Metrics visualization and dashboards |
| snmp | `quay.io/prometheus/snmp-exporter` | SNMP metrics exporter |
| influxdb | `influxdb:2.7.6-alpine` | Time-series database |
| loki | `grafana/loki:latest` | Log aggregation |
| promtail | `grafana/promtail:latest` | Log collector for Loki |
| cadvisor | `gcr.io/cadvisor/cadvisor-amd64:v0.52.1` | Container resource monitoring |
| syslog-ng | `lscr.io/linuxserver/syslog-ng:latest` | Syslog collector |

## Ports

| Host | Container | Service | Description |
|------|-----------|---------|-------------|
| 3004 | 3000 | grafana | Web UI |
| 9116 | 9116 | snmp | SNMP exporter |
| 116/udp | 116/udp | snmp | SNMP trap |
| 8086 | 8086 | influxdb | InfluxDB API |
| - | 3100 | loki | Loki API (internal) |
| - | 8080 | cadvisor | cAdvisor UI (internal) |
| 514/udp | 5514/udp | syslog-ng | Syslog UDP |
| 601/tcp | 6601/tcp | syslog-ng | Syslog TCP |
| 6514/tcp | 6514/tcp | syslog-ng | Syslog TLS |

## Volumes

| Host Path | Container Path | Service | Description |
|-----------|---------------|---------|-------------|
| `/home/kyle/appdata/grafana` | `/etc/grafana/provisioning/datasources` | grafana | Datasource provisioning |
| `grafana_data` (named) | `/var/lib/grafana` | grafana | Grafana data |
| `/home/kyle/appdata/snmp-exporter` | `/etc/snmp_exporter` | snmp | SNMP config |
| `influxdb2_data` (named) | `/var/lib/influxdb2` | influxdb | InfluxDB data |
| `/home/kyle/appdata/influxdb2/config` | `/etc/influxdb2` | influxdb | InfluxDB config |
| `/home/kyle/appdata/influxdb2/scripts` | `/docker-entrypoint-initdb.d` | influxdb | Init scripts |
| `/home/kyle/appdata/loki` | `/loki` | loki | Loki data |
| `/home/kyle/appdata/promtail/promtail-config.yaml` | `/etc/promtail/config.yml` | promtail | Promtail config |
| `/var/run/docker.sock` | `/var/run/docker.sock` | promtail | Docker socket |
| `/var/log` | `/var/log` | promtail | System logs (read-only) |
| `/home/kyle/appdata/syslog-ng/config` | `/config` | syslog-ng | Syslog-ng config |
| `/home/kyle/appdata/syslog-ng/log` | `/var/log` | syslog-ng | Log storage |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `HOSTNAME` | Yes | Traefik hostname for Grafana |

## Networks

- `cn1` (external) - Shared Docker network for Traefik routing

## Links

- [Grafana](https://grafana.com/)
- [InfluxDB](https://www.influxdata.com/)
- [Loki](https://grafana.com/oss/loki/)
- [cAdvisor](https://github.com/google/cadvisor)
- [syslog-ng](https://www.syslog-ng.com/)
