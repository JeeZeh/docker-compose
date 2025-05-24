# Home Network Docker Compose

A simple Docker Compose setup for a secure, privacy-focused home network using Pi-hole and Cloudflare services.

## Services
- **Pi-hole:** Network-wide ad blocker and DNS/DHCP server
- **Cloudflare DDNS:** Updates Cloudflare DNS records to match your public IP
- **Cloudflare Tunnel:** Securely exposes services to the internet (no port forwarding needed)
- **Cloudflare DoH/DoT:** Secure DNS resolver (DNS-over-HTTPS/TLS)

## Quick Start
1. Clone this repo:
   ```sh
   git clone <your-repo-url>
   cd <repo-folder>
   ```
2. Set environment variables in a `.env` file:
   - `CF_DDNS_API_TOKEN`
   - `CF_DDNS_ZONE_ID`
   - `CLOUDFLARE_TUNNEL_TOKEN` 
3. Edit `cloudflare-ddns.json` and other configs as needed.
4. Start everything:
   ```sh
   docker compose up -d
   ```

## Access
- **Pi-hole UI:** http://<your-server-ip>:8080
- **Cloudflare Tunnel:** Managed via Cloudflare dashboard
- **DNS-over-HTTPS/TLS:** Point clients to your server's IP:5054

## Data & Configs
- `cloudflare-ddns.json` — DDNS config
- `etc-pihole/` — Pi-hole data
- `etc-dnsmasq.d/` — Optional custom configs

## References
- [Pi-hole](https://github.com/pi-hole/docker-pi-hole)
- [Cloudflare DDNS](https://github.com/timothymiller/cloudflare-ddns)
- [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/)
- [crazymax/cloudflared](https://github.com/crazy-max/docker-cloudflared)

