# web_stack_debugging_1

Debugging project: find out why Nginx in an Ubuntu container is not listening on port 80, and automate the fix.

## Files

| File | Description |
|------|-------------|
| `0-nginx_likes_port_80` | Bash script that makes Nginx run and listen on port 80 on all active IPv4 addresses. |

## Diagnosis

`/etc/nginx/sites-enabled/default` was not the stock symlink to `/etc/nginx/sites-available/default` (it was a regular file listening on port 8080), so nothing answered on port 80.

## Fix

The script restores the symlink with `ln -sf` and restarts Nginx with `service nginx restart`.
