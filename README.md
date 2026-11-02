# S&P 500 data engine

Same design as the NYSE engine (it is the same code with another symbol list): raw prices live in git, adjustments are computed at build time, and only the final
yearly parquet files, history buckets, packs and manifest go to Cloudflare R2 (bucket `nse-stock-data`, folder `sp500/`).

* **Symbols:** the current 500-odd S&P 500 members (NYSE and Nasdaq), downloaded each run from github.com/datasets/s-and-p-500-companies and saved in `data/constituents.csv` (used if the download fails). Plus the indices (see below). A stock that leaves the index keeps being updated, so its history stays complete.
* **Source:** Yahoo Finance chart API (free, unofficial). Raw prices are rebuilt from Yahoo's split-adjusted ones and stored in git; splits and dividends in `data/events/`.
* **Adjustment:** splits at once; cash dividends (total-return style) only in the weekly upload run. Jumps with no split event are not guessed: they are listed in `data/reports/review_jumps.csv`. To fix a real missed split add it to `data/manual_adjustments.json` (see the NYSE README: `{"TICKER": [{"ex_date": "YYYY-MM-DD", "factor": 0.5, "replace": true}]}`).

## Order of work
1. Actions -> **Daily S&P 500 Fetcher** -> Run workflow, leave the boxes as they are (about 10 to 20 minutes; run it again if the time limit stops it).
2. Read `data/reports/` in the repo.
3. Add the three R2 secrets (`R2_ACCESS_KEY_ID`, `R2_SECRET_ACCESS_KEY`, `R2_ENDPOINT_URL`) to this repo, then Actions -> **S&P 500 Upload to R2** with `force_all` ticked.
4. Afterwards the daily fetch runs by itself on weekdays; run the upload by hand when you want R2 updated, and once a week with `weekly_run` ticked to apply dividends.

## Indices
Indices: all the S&P US indices: S&P 500 (price and total return), 100, MidCap 400, SmallCap 600, GSCI commodity and the 11 S&P 500 sector indices are fetched from Yahoo like stocks and stored in the same database. In the app an index is found with or without the `^` (`NYA` finds `^NYA`; `SPX` and `GSPC` both find `^GSPC`). Only this market's indices are in this database; for any others use `index_symbols`.
* **Add them now, without touching the stocks:** Actions -> **S&P 500 Indices Fetcher** -> Run workflow (about 1 minute), then **S&P 500 Upload to R2** with `force_all` ticked.
* **Afterwards** the normal **Daily S&P 500 Fetcher** updates the indices together with the stocks. Change the list with the `index_symbols` box (`none` = no indices).
* After the first run read the `[INDEX]` lines of the log: each index shows its first and last date and last close, so a wrong or unknown Yahoo ticker is easy to spot ("no data" = Yahoo does not have it).
* Indices have no splits or dividends, so nothing is adjusted. Their volume on Yahoo is often 0. They are left out of `review_jumps.csv`.

The list is in `INDEX_NAMES` (backend/fetch.py). The tickers are Yahoo's; the log of the indices run prints one `[INDEX]` line per ticker with its first and last date and last close, or `NO DATA on Yahoo` for a ticker Yahoo does not know. Such tickers are skipped and tried again after 30 days; send the log and the list can be corrected.

## Limits
* Survivorship bias: only today's members (plus earlier loaded ones) exist, never stocks that were in the index in the past and were delisted. The indices are complete.
* The NYSE database already holds the NYSE-listed members; this one adds the Nasdaq-listed ones and the index, so the symbols overlap on purpose.
* Yahoo is unofficial; the fetch stores nothing if more than 2% of requests fail.

Tests (offline): `python tests/test_sp500_e2e.py` and `PERIOD_MODE=half python tests/test_sp500_e2e.py`.
