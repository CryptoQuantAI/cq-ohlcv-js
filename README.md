# 📥 cq-ohlcv-js
### Fast OHLCV Downloader for JavaScript & TypeScript  
Part of the **CryptoQuantAI** Ecosystem

`cq-ohlcv-js` is the JavaScript/TypeScript version of the CryptoQuantAI OHLCV downloader,  
built for Node.js and browser-based crypto applications.

It provides a unified interface to fetch historical OHLCV data from multiple exchanges  
and prepare it for charting, indicators, ML pipelines, and trading dashboards.

---

## 🚀 Features

- ✅ Unified OHLCV API for JavaScript/TypeScript  
- ✅ Works with Binance, Bybit, MEXC, KuCoin, OKX (via REST)  
- ✅ Node.js compatible  
- ✅ Optional browser support (CORS proxied)  
- ✅ Converts exchange responses into consistent OHLCV format  
- ✅ Built-in resampling (1m → 5m → 15m → 1h → 1d)  
- ✅ Lightweight & dependency-free  
- ✅ Export to JSON / CSV  

---

## 📦 Installation

```bash
npm install cq-ohlcv-js
```

or

```bash
yarn add cq-ohlcv-js
```

---

## 💡 Quick Start

### ✅ Download OHLCV from Binance

```javascript
import { OHLCV } from "cq-ohlcv-js";

const df = await OHLCV.fetch({
  symbol: "BTCUSDT",
  timeframe: "5m",
  exchange: "binance"
});

console.log(df);
```

---

### ✅ Resample Timeframes

```javascript
import { OHLCV } from "cq-ohlcv-js";

const resampled = OHLCV.resample(df, "15m");
console.log(resampled);
```

---

### ✅ Save as CSV

```javascript
import { OHLCV } from "cq-ohlcv-js";
import fs from "fs";

const csv = OHLCV.toCSV(df);
fs.writeFileSync("btc_5m.csv", csv);
```

---

## ✅ Standardized Output Format

Every OHLCV entry returns:

```javascript
{
  time: 1710000000,
  open: 100,
  high: 105,
  low: 98,
  close: 103,
  volume: 2000
}
```

Guaranteed consistent across all supported exchanges.

---

## 🔌 Supported Exchanges

| Exchange | Status |
|---------|--------|
| Binance | ✅ |
| Bybit | ✅ |
| MEXC | ✅ |
| KuCoin | ✅ |
| OKX | ✅ |
| Coinbase | ⏳ planned |
| CCXT fallback | ⏳ planned |

---

## 🗂 Folder Structure

```
cq-ohlcv-js/
│
├── src/
│   ├── index.ts
│   ├── ohlcv.ts
│   ├── exchanges/
│   │   ├── binance.ts
│   │   ├── bybit.ts
│   │   ├── mexc.ts
│   │   ├── kucoin.ts
│   │   ├── okx.ts
│   │
│   └── utils/
│       ├── http.ts
│       ├── resample.ts
│       ├── format.ts
│
├── dist/
├── tests/
└── README.md
```

---

## 📅 Roadmap

- ✅ Multi-exchange support  
- ✅ Resampling engine  
- ⏳ WebSocket live streaming  
- ⏳ CCXT-JS fallback integration  
- ⏳ Browser SDK (Lite version)  
- ⏳ Polars-JS support  

---

## 🤝 Contributing

We welcome contributors!

Guidelines:
- ESLint + Prettier  
- TypeScript strict mode  
- Add tests for each exchange wrapper  
- Clean functional design  

---

## ⚖️ License

MIT License — free for commercial and personal use.

---

## 👨‍💻 Maintained By

CryptoQuantAI Development Team
