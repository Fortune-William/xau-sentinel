# XAU Sentinel

A live gold (XAUUSD) dashboard: real-time price, session clock (Nairobi time),
session open/closed indicators, a 5-day price chart, and tracked
support/resistance levels with distance-to-price.

Built with React-style vanilla JS + Chart.js on the front, a tiny Node
backend that proxies COMEX futures data (spot XAUUSD feeds are paid; the
backend subtracts a configurable futures-to-spot offset).

## Run

```
npm install        # no extra deps beyond Node built-ins actually needed
node index.js      # serves on :3001, /sentinel + /api/price
```

(In this repo the routes live inside a larger webserver file; port 3001.)

## Files

- `index.html` — the whole UI (single file, Chart.js via CDN)
- `server-routes.ts` — the `/sentinel` and `/api/price` route handlers

## Notes

- Not financial advice. Levels are personal watchlevels; confirm on your
  broker chart before acting.
- Offset (futures minus spot) is set in `index.html` (`OFFSET`) and should
  be recalibrated occasionally.

Built by Fortune William — github.com/Fortune-William
