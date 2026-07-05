# Pods Relay

A tiny fetch relay that lets the [Site Map Analysis](https://planetsocialmarketing.com/site-map-analysis) tool crawl any website from your browser. Deploy it to your own free Cloudflare account in one click:

[![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/brodricklacyhudson/pods-relay)

## After deploying

1. Copy your worker URL (it looks like `https://github.com/brodricklacyhudson/pods-relay`)
2. In the Site Map Analysis tool, open **Advanced** and paste it into the proxy field as:
   `https://github.com/brodricklacyhudson/pods-relay/?url=`
3. Deploy Pods at any site.

## What it does, and does not do

- Forwards page requests so your browser can crawl sites other than the one hosting the tool
- Identifies itself honestly as `PlanetSocial-Pods/1.0` and respects the tool's polite pacing
- Blocks private and internal addresses, caps response size, and serves only the allowed origins listed at the top of `worker.js` (edit `ALLOWED_ORIGINS` if you self-configure)
- Stores nothing. It is a pipe, not a database.

Free tier: 100,000 requests per day, far beyond what polite Pods use.

Built by [Planet Social Marketing](https://planetsocialmarketing.com).
