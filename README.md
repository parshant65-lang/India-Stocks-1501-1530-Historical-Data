# India-Stocks-1501-1530-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1501 to 1530)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1501-1530-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1501 to 1530)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1501 | `KRN` | KRN Heat Exchanger and Refrigeration Limited | `KRN.NS` |
| 1502 | `KRONOX` | Kronox Lab Sciences Limited | `KRONOX.NS` |
| 1503 | `KROSS` | Kross Limited | `KROSS.NS` |
| 1504 | `KRSNAA` | Krsnaa Diagnostics Limited | `KRSNAA.NS` |
| 1505 | `KRYSTAL` | Krystal Integrated Services Limited | `KRYSTAL.NS` |
| 1506 | `KSCL` | Kaveri Seed Company Limited | `KSCL.NS` |
| 1507 | `KSE` | KSE Limited | `KSE.NS` |
| 1508 | `KSHINTL` | KSH International Limited | `KSHINTL.NS` |
| 1509 | `KSHITIJPOL` | Kshitij Polyline Limited | `KSHITIJPOL.NS` |
| 1510 | `KSL` | Kalyani Steels Limited | `KSL.NS` |
| 1511 | `KSOLVES` | Ksolves India Limited | `KSOLVES.NS` |
| 1512 | `KSR` | KSR Footwear Limited | `KSR.NS` |
| 1513 | `KTKBANK` | The Karnataka Bank Limited | `KTKBANK.NS` |
| 1514 | `KUANTUM` | Kuantum Papers Limited | `KUANTUM.NS` |
| 1515 | `KUSUMGAR` | Kusumgar Limited | `KUSUMGAR.NS` |
| 1516 | `KWIL` | Kwality Wall's (India) Limited | `KWIL.NS` |
| 1517 | `LADDERUP` | Ladderup Finance Limited | `LADDERUP.NS` |
| 1518 | `LAGNAM` | Lagnam Spintex Limited | `LAGNAM.NS` |
| 1519 | `LAHOTIOV` | Lahoti Overseas Limited | `LAHOTIOV.NS` |
| 1520 | `LAKPRE` | Lakshmi Precision Screws Limited | `LAKPRE.NS` |
| 1521 | `LAKSHMIMIL` | Lakshmi Mills Company Limited | `LAKSHMIMIL.NS` |
| 1522 | `LAL` | Lorenzini Apparels Limited | `LAL.NS` |
| 1523 | `LALITHAA` | Lalithaa Jewellery Mart Limited | `LALITHAA.NS` |
| 1524 | `LAMBODHARA` | Lambodhara Textiles Limited | `LAMBODHARA.NS` |
| 1525 | `LANCER` | Lancer Container Lines Limited | `LANCER.NS` |
| 1526 | `LANCORHOL` | Lancor Holdings Limited | `LANCORHOL.NS` |
| 1527 | `LANDMARK` | Landmark Cars Limited | `LANDMARK.NS` |
| 1528 | `LANDSMILL` | Landsmill Green Limited | `LANDSMILL.NS` |
| 1529 | `LAOPALA` | La Opala RG Limited | `LAOPALA.NS` |
| 1530 | `LASERPOWER` | Laser Power & Infra Limited | `LASERPOWER.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream KRN 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1501-1530-Historical-Data/main/KRN/1m/2026/10/KRN_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
