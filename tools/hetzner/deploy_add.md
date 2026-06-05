## docker compose file in server

```yaml
# docker-compose.yml in a certain directory
services:
  frontend:
    image: ghcr.io/degiwo/myapp:latest
    restart: unless-stopped
    ports:
      - "81:8080"
# allow port 81 in firewall
```
