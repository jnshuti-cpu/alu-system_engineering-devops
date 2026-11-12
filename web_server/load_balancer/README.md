# load_balancer

Redundant web stack: two Nginx web servers behind an HAProxy load balancer.

| File | Description |
|------|-------------|
| `0-custom_http_response_header` | Installs Nginx and adds an `X-Served-By: <hostname>` response header (run on web-01 and web-02). |
| `1-install_load_balancer` | Installs HAProxy on lb-01, roundrobin across web-01 and web-02, init script enabled. Set `WEB_02_IP` (and optionally `STUDENT_ID`, `WEB_01_IP`) before running. |

Test: `curl -sI <lb-ip> | grep X-Served-By` repeatedly should alternate between `-web-01` and `-web-02`.
