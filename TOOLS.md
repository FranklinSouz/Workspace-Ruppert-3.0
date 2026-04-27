# TOOLS.md - Local Notes

## VPS Principal
- **IP público:** 187.77.148.76
- **OS:** Ubuntu 24.04 LTS
- **Hostname:** srv1476751
- **Tailscale IP:** 100.103.17.77

## Infraestrutura
- **Reverse Proxy:** Traefik (Docker, host network, Let's Encrypt automático via `letsencrypt` certresolver)
- **Containers ativos:** `cavegroup-web` (Nginx Alpine), `traefik-traefik-1`, `openclaw-ecf2-openclaw-1`
- **Deploy de sites:** copiar HTML/CSS/JS para `/var/www/SITE/html/` → Traefik serve com HTTPS automático

## Domínios & Sites

### cavegroup.com.br
- **DNS:** Registro.br apontado para IP da VPS (já propagado)
- **HTTPS:** ✅ Let's Encrypt via Traefik
- **Compose:** `/opt/cavegroup-docker-compose.yml`
- **Arquivos:** `/var/www/cavegroup/html/`
- **Nginx conf:** `/var/www/cavegroup/nginx.conf` (porta 8088)
- **Traefik rule:** `Host(cavegroup.com.br) || Host(www.cavegroup.com.br)`
- Para publicar: copiar arquivo para `/var/www/cavegroup/html/` — imediato, sem restart

## Gateway OpenClaw
- **Bind:** loopback (`127.0.0.1:18789`)
- **Auth token:** `38b9c5862184e465b05bb4cf7efb0bb016401113ce308838`
- **Config:** `/root/.openclaw/openclaw.json`
- **controlUi.allowInsecureAuth:** true

## Tailscale
- VPS: `srv1476751` — `100.103.17.77`
- Franklin Mac: `MacBook-Pro` — `100.125.240.118`

## Pixel Agents Dashboard
- Rodando em `http://100.103.17.77:5070` (Tailscale only)
- Diretório: `/root/.openclaw/workspace/skills/openclaw-pixel-agents-dashboard/`
- Start: `OPENCLAW_GATEWAY_TOKEN=38b9c5862184e465b05bb4cf7efb0bb016401113ce308838 npm start`
- **Não persiste reboot** — sem systemd ainda

## Stack de Desenvolvimento (Roberto Dev)
- **Automações:** Make (Integromat), N8N
- **No-code/Low-code:** Lovable, Webflow, Framer
- **Landing Pages:** HTML/CSS/JS vanilla, React se necessário
- **Tracking:** Meta Pixel, Google Tag Manager, GA4

## GitHub
- **Repo workspace:** `https://github.com/FranklinSouz/ruppert-workspace` (private)
- **Repo landing pages:** `https://github.com/FranklinSouz/cave-ia` (public, GitHub Pages ativo)
