# ARR Stack

A Docker Compose setup for a complete media management stack using the *Arr applications (Radarr, Sonarr, etc.), with VPN protection via Gluetun, torrenting with qBittorrent, usenet with SABnzbd, and media serving with Jellyfin.

## Prerequisites

- Docker and Docker Compose
- VPN service (supports OpenVPN or WireGuard)
- Sufficient storage for media and downloads

## Setup

1. Clone this repository.
2. Copy `.env.example` to `.env` and fill in your configuration:
   - VPN credentials
   - Directory paths
   - API keys (store sensitive ones in `./secrets/` directory)
3. Ensure the required directories exist (as per `.env.example`).
4. Run `docker-compose up -d` to start the stack.

## Services

- **Gluetun**: VPN container routing traffic for most services.
- **qBittorrent**: Torrent client.
- **Radarr**: Movie management and automation.
- **Sonarr**: TV show management and automation.
- **Prowlarr**: Indexer management.
- **Jackett**: Indexer proxy.
- **Jellyseerr**: Media request management.
- **Unpackerr**: Automatic archive extraction.
- **SABnzbd**: Usenet downloader.
- **FlareSolverr**: Cloudflare bypass (not behind VPN).
- **Jellyfin**: Media server (not behind VPN).

## Access

Access the web UIs using the ports defined in your `.env` file.

## Notes

- Most services route through the VPN for privacy.
- Jellyfin and FlareSolverr are exposed directly without VPN.
- Follow Trash-Guides for optimal configuration.