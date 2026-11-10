# SGA Trader — Status & Break-glass page

Independent, static status page hosted on **GitHub Pages** (off our own droplets
and off Cloudflare) so it stays reachable during a main-site / CDN / DNS outage.

- Client-side probes the main + **direct-** (Cloudflare-bypass) hostnames every 30s.
- Surfaces the break-glass URLs (`direct-crypto` / `direct-sgastretch`) and the
  Telegram announcement channel.
- No build step — plain `index.html`. Edit + push to deploy.

## Custom domain
`CNAME` points the site at **sgatrader-status.com**. At the registrar (a
**non-Cloudflare** registrar, on purpose), add:

    CNAME  sgatrader-status.com  ->  visionkraftconsulting.github.io.

(or an apex `ALIAS`/`ANAME`, or GitHub Pages A records 185.199.108–111.153).

## Telegram button
Set `TELEGRAM_URL` at the top of `index.html` to your channel
(e.g. `https://t.me/sgatrader_status`) to show the announcements button.

This is part of the [RESILIENCE_PLAN](../sgaEMA/RESILIENCE_PLAN.md) — item P0-1.
