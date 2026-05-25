# My uptime monitor

I use [gatus](https://github.com/TwiN/gatus) for uptime monitoring. Deployed via [Dokploy](https://dokploy.com/).

## Deployment

Gatus reads `config/config.yaml` at startup. After pushing a config change, **the container must be restarted** for changes to take effect — a redeploy alone may not trigger a restart if the Docker image hasn't changed!

```bash
ssh user@your-server "docker restart $(docker ps -qf 'name=gatus')"
```
