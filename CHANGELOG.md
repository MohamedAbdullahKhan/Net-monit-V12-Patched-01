# Net-monit changelog

## V12.0 (new major release, port 5050)

**New: Traffic Analyzer** (sidebar > Traffic). Everything Sniffnet's engine does, built into Net-monit on the same Flask + SQLite + Python platform.

- Capture from a network card (native on Linux, Npcap/scapy on Windows and macOS), from a .pcap/.pcapng file, or collect NetFlow v5 / v9 / IPFIX from routers and switches.
- Live chart (incoming above the line, outgoing below), totals, ranked hosts, services, programs and countries; bytes / bits / packets.
- Connections: search, exact match with `=`, filters (program, host, country, AS, protocol, service, IP, port, direction, favorites, blacklisted), sorting, paging, detail panel with latency.
- Service detection (6,000+ ports) with categories, country and AS of every remote host (GeoLite2 or IPinfo databases), reverse DNS, program names, bogon and local-network detection.
- Favorites, an IP blacklist, notifications (traffic above a limit, a favorite active, a blacklisted address contacted) with sounds, e-mail, SMS, voice call, webhook, audit log and a notification log.
- Save packets to .pcap, CSV report, capture history in SQLite, mini-monitor window, automatic start with the service, retention setting.
- Traffic hosts are linked to your monitored Net-monit devices.

**Included from V11.3 patches 06-08**: context-aware "apply to" buttons that really apply, much faster saving (bulk notify loading, no full re-poll after a device save, batched database writes), custom dashboard views and a dashboard that remembers its tab, Save / Save & close / Cancel in every editing window.

**Fixes**: missing favicon (404 on every page); README login instructions (the first-run token is random, in `data/FIRST-RUN-ADMIN-TOKEN.txt`).

**Upgrade notes**: V12 installs side by side (`C:\NetMonit-V12.0`, service `Net_Monit_V120`, Linux `/opt/netmonit-v120`, port 5050). Like earlier major releases a new install folder has a new Device ID, so request a new free license key. To keep your devices and history, copy `config.yaml` and the `data` folder of V11.3 into the V12 folder before the first start (the database is extended automatically). Windows live capture needs Npcap (https://npcap.com) and a service running as Local System; Linux needs `CAP_NET_RAW` (the supplied systemd unit grants it).
