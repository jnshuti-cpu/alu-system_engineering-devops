# Firewall

This project configures the `ufw` firewall on `web-01`.

## Files

- `0-block_all_incoming_traffic_but`: installs `ufw` and blocks all incoming traffic except TCP ports 22 (SSH), 80 (HTTP) and 443 (HTTPS).
