# Adjustment review

One-day RAW price moves no split explains. `looks like a missed split` = the ratio is a usual split ratio, so Yahoo probably missed an event.
To fix one, add to data/manual_adjustments.json: `{"TICKER": [{"ex_date": "YYYY-MM-DD", "factor": 0.5, "description": "missed 2:1 split"}]}`

Jumps: 62, of which look like missed splits: 55

| ticker | company | date | prev | close | ratio | nearest | note |
|---|---|---|---|---|---|---|---|
| MRSH | Marsh McLennan | 1980-11-12 | 62.0 | 30.0 | 0.4839 | 0.4737 | looks like a missed split/bonus |
| VTRS | Viatris | 1981-11-16 | 27.0 | 12.375 | 0.4583 | 0.4615 | looks like a missed split/bonus |
| TSN | Tyson Foods | 1983-04-18 | 30.25 | 15.0 | 0.4959 | 0.5 | looks like a missed split/bonus |
| VTRS | Viatris | 1983-07-01 | 32.25 | 16.25 | 0.5039 | 0.5 | looks like a missed split/bonus |
| BEN | Franklin Resources | 1984-12-31 | 24.25 | 9.75 | 0.4021 | 0.4 | looks like a missed split/bonus |
| GL | Globe Life | 1984-05-30 | 39.25 | 19.625 | 0.5 | 0.5 | looks like a missed split/bonus |
| GL | Globe Life | 1985-09-17 | 45.0 | 21.875 | 0.4861 | 0.4737 | looks like a missed split/bonus |
| TSN | Tyson Foods | 1985-04-16 | 43.0 | 18.5 | 0.4302 | 0.4286 | looks like a missed split/bonus |
| VTRS | Viatris | 1985-02-19 | 35.75 | 17.0 | 0.4755 | 0.4737 | looks like a missed split/bonus |
| TRV | Travelers Companies (The) | 1986-06-09 | 90.25 | 43.25 | 0.4792 | 0.4737 | looks like a missed split/bonus |
| TSN | Tyson Foods | 1986-04-16 | 43.5 | 23.75 | 0.546 | 0.5455 | looks like a missed split/bonus |
| MNST | Monster Beverage | 1987-10-20 | 0.0625 | 0.0312 | 0.4992 | 0.5 | looks like a missed split/bonus |
| MNST | Monster Beverage | 1987-11-17 | 0.0312 | 0.0625 | 2.0032 | 2.0 | looks like a missed split/bonus |
| MNST | Monster Beverage | 1987-11-30 | 0.0625 | 0.0312 | 0.4992 | 0.5 | looks like a missed split/bonus |
| MNST | Monster Beverage | 1987-12-24 | 0.0312 | 0.0625 | 2.0032 | 2.0 | looks like a missed split/bonus |
| MNST | Monster Beverage | 1987-12-28 | 0.0625 | 0.0312 | 0.4992 | 0.5 | looks like a missed split/bonus |
| NVR | NVR, Inc. | 1987-06-23 | 47.125 | 10.25 | 0.2175 | 0.2222 | looks like a missed split/bonus |
| KR | Kroger | 1988-10-31 | 58.0 | 18.25 | 0.3147 | 0.3077 | looks like a missed split/bonus |
| KR | Kroger | 1988-12-05 | 18.25 | 9.5 | 0.5205 | 0.5263 | looks like a missed split/bonus |
| MNST | Monster Beverage | 1988-01-08 | 0.0312 | 0.0625 | 2.0032 | 2.0 | looks like a missed split/bonus |
| TYL | Tyler Technologies | 1988-08-22 | 17.375 | 7.125 | 0.4101 | 0.4118 | looks like a missed split/bonus |
| PNW | Pinnacle West Capital | 1989-12-07 | 5.375 | 10.25 | 1.907 | 2.0 | looks like a missed split/bonus |
| HST | Host Hotels & Resorts | 1993-10-12 | 33.25 | 6.375 | 0.1917 | 0.2 | looks like a missed split/bonus |
| HUM | Humana | 1993-03-08 | 20.0 | 6.875 | 0.3438 | 0.3333 | looks like a missed split/bonus |
| HUBB | Hubbell Incorporated | 1994-10-31 | 5.8702 | 57.876 | 9.8593 | 10.0 | looks like a missed split/bonus |
| IDXX | Idexx Laboratories | 1997-03-24 | 32.0 | 12.0 | 0.375 | 0.375 | looks like a missed split/bonus |
| LEN | Lennar | 1997-11-03 | 40.6875 | 16.625 | 0.4086 | 0.4118 | looks like a missed split/bonus |
| DECK | Deckers Brands | 1998-10-13 | 4.375 | 2.0 | 0.4571 | 0.4545 | looks like a missed split/bonus |
| DVA | DaVita | 1999-02-18 | 21.0 | 8.75 | 0.4167 | 0.4167 | looks like a missed split/bonus |
| MCK | McKesson | 1999-04-28 | 65.75 | 34.5 | 0.5247 | 0.5263 | looks like a missed split/bonus |
| AAPL | Apple Inc. | 2000-09-29 | 53.5 | 25.75 | 0.4813 | 0.4737 | looks like a missed split/bonus |
| PTC | PTC Inc. | 2000-04-03 | 21.0625 | 10.75 | 0.5104 | 0.5 | looks like a missed split/bonus |
| AES | AES Corporation | 2001-09-26 | 24.25 | 12.25 | 0.5052 | 0.5 | looks like a missed split/bonus |
| NVDA | Nvidia | 2001-09-17 | 75.7601 | 33.99 | 0.4487 | 0.4444 | looks like a missed split/bonus |
| ROK | Rockwell Automation | 2001-07-02 | 38.12 | 14.7 | 0.3856 | 0.3846 | looks like a missed split/bonus |
| PWR | Quanta Services | 2002-07-02 | 9.14 | 2.92 | 0.3195 | 0.3077 | looks like a missed split/bonus |
| SBAC | SBA Communications | 2002-10-04 | 0.8 | 0.41 | 0.5125 | 0.5 | looks like a missed split/bonus |
| VRSN | Verisign | 2002-04-26 | 18.24 | 9.89 | 0.5422 | 0.5455 | looks like a missed split/bonus |
| WMB | Williams Companies | 2002-07-22 | 5.16 | 2.01 | 0.3895 | 0.3846 | looks like a missed split/bonus |
| WMB | Williams Companies | 2002-07-29 | 0.99 | 1.99 | 2.0101 | 2.0 | looks like a missed split/bonus |
| REGN | Regeneron Pharmaceuticals | 2003-03-31 | 17.31 | 7.52 | 0.4344 | 0.4375 | looks like a missed split/bonus |
| AIG | American International Group | 2008-09-15 | 12.14 | 4.76 | 0.3921 | 0.3846 | looks like a missed split/bonus |
| AIG | American International Group | 2008-09-17 | 3.75 | 2.05 | 0.5467 | 0.5455 | looks like a missed split/bonus |
| FIS | Fidelity National Information Services | 2008-07-03 | 37.25 | 20.14 | 0.5407 | 0.5385 | looks like a missed split/bonus |
| HIG | Hartford (The) | 2008-10-30 | 19.86 | 9.62 | 0.4844 | 0.4737 | looks like a missed split/bonus |
| HIG | Hartford (The) | 2008-12-05 | 7.21 | 14.59 | 2.0236 | 2.0 | looks like a missed split/bonus |
| MO | Altria | 2008-03-31 | 73.83 | 22.2 | 0.3007 | 0.3 | looks like a missed split/bonus |
| STT | State Street Corporation | 2009-01-20 | 36.35 | 14.89 | 0.4096 | 0.4118 | looks like a missed split/bonus |
| WY | Weyerhaeuser | 2010-07-20 | 41.83 | 15.94 | 0.3811 | 0.3846 | looks like a missed split/bonus |
| KDP | Keurig Dr Pepper | 2018-07-10 | 123.66 | 22.19 | 0.1794 | 0.1818 | looks like a missed split/bonus |
| PCG | PG&E Corporation | 2019-01-14 | 17.59 | 8.38 | 0.4764 | 0.4737 | looks like a missed split/bonus |
| APA | APA Corporation | 2020-03-09 | 20.7 | 9.55 | 0.4614 | 0.4615 | looks like a missed split/bonus |
| OXY | Occidental Petroleum | 2020-03-09 | 26.86 | 12.51 | 0.4657 | 0.4667 | looks like a missed split/bonus |
| TRGP | Targa Resources | 2020-03-09 | 27.86 | 13.12 | 0.4709 | 0.4706 | looks like a missed split/bonus |
| GL | Globe Life | 2024-04-11 | 104.93 | 49.17 | 0.4686 | 0.4667 | looks like a missed split/bonus |
| BEN | Franklin Resources | 1985-01-02 | 9.75 | 24.5001 | 2.5128 | 3.0 | no clean ratio (crash, spin-off or bad data?) |
| DVN | Devon Energy | 1988-10-03 | 2.9375 | 5.5 | 1.8723 | 2.0 | no clean ratio (crash, spin-off or bad data?) |
| MNST | Monster Beverage | 1990-03-06 | 2.25 | 4.1249 | 1.8333 | 2.0 | no clean ratio (crash, spin-off or bad data?) |
| NVR | NVR, Inc. | 1993-10-01 | 0.375 | 10.25 | 27.3333 | 10.0 | no clean ratio (crash, spin-off or bad data?) |
| TSCO | Tractor Supply | 1994-02-18 | 7.0 | 22.75 | 3.25 | 3.0 | no clean ratio (crash, spin-off or bad data?) |
| MS | Morgan Stanley | 2008-10-13 | 9.68 | 18.1 | 1.8698 | 2.0 | no clean ratio (crash, spin-off or bad data?) |
| MRNA | Moderna | 2026-08-19 | 62.96 | 174.38 | 2.7697 | 3.0 | no clean ratio (crash, spin-off or bad data?) |
