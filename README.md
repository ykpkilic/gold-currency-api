# Hasfiyat Gold & Currency API

Real-time **gold and currency prices for Turkey** — gram gold, quarter/half/full/Republic gold and FX rates (USD, EUR, ...). Available over **REST** and **WebSocket**.

Website: https://hasfiyat.com · Docs: https://altinapi.hasfiyat.com

## Features
- Real-time gold prices: gram, quarter (ceyrek), half, full, Republic (cumhuriyet)
- Major currency rates (USD, EUR, and more)
- REST endpoints for simple polling
- WebSocket channel for instant live updates
- Low latency, market-synced data

## Quick Start (REST)

```bash
curl -H "Authorization: Bearer YOUR_API_KEY" \
  https://altinapi.hasfiyat.com/prices/all
```

```javascript
// Node.js example
const res = await fetch("https://altinapi.hasfiyat.com/prices/all", {
  headers: { Authorization: "Bearer YOUR_API_KEY" }
});
const data = await res.json();
console.log(data); // { gramGold: ..., quarterGold: ..., usd: ..., eur: ... }
```

```python
# Python example
import requests
r = requests.get(
    "https://altinapi.hasfiyat.com/prices/all",
    headers={"Authorization": "Bearer YOUR_API_KEY"},
)
print(r.json())
```

## Live Updates (WebSocket)

```javascript
const ws = new WebSocket("wss://altinapi.hasfiyat.com/stream?token=YOUR_API_KEY");
ws.onmessage = (e) => console.log("price update:", JSON.parse(e.data));
```

## Use Cases
Jeweler price screens, fintech apps, finance/news sites, portfolio and rate-tracking tools.

## Documentation
Full docs and endpoint reference: https://altinapi.hasfiyat.com

## About
Maintained by [Hasfiyat](https://hasfiyat.com) — all-in-one management software for jewelers, including a live gold/FX price screen, bulk e-invoicing, and buy-sell & current account tracking.
