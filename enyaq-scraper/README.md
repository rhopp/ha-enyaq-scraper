# Enyaq Scraper — Home Assistant Add-on

A Home Assistant add-on that scrapes Škoda Enyaq listings from **Bazoš.cz**,
**Sauto.cz**, and **Škoda Plus**, stores them in a local SQLite database, tracks
market changes, and exposes an interactive dashboard directly in the Home
Assistant sidebar.

The scraper runs automatically once a day and posts a summary as a Home
Assistant persistent notification (bell icon).

## Installation

1. In Home Assistant, go to **Settings → Add-ons → Add-on Store**.
2. Click the **⋮** (top-right) → **Repositories**.
3. Add this URL and click **ADD**:

   ```
   https://github.com/rhopp/ha-enyaq-scraper
   ```

4. Find **Enyaq Scraper** in the store and click **Install**.
5. After install, open the **Configuration** tab to adjust options, then click
   **Start**.
6. Click **Enyaq** in the sidebar to open the dashboard, or use the **Run now**
   button to trigger a scan immediately.

## Options

| Option          | Default | Description                                            |
| --------------- | ------- | ------------------------------------------------------ |
| `scrape_time`   | `04:00` | Daily time (HH:MM, 24h) to run the scrape.             |
| `sauto_enabled` | `true`  | Enable the heavier Playwright/Chromium scrape of Sauto.|
| `notify_ha`     | `true`  | Send a persistent notification with the run summary.   |

## Data

The database lives at `/data/listings.db` inside the add-on and is included in
Home Assistant backups. Removing the add-on deletes this data.

## Notes

- Designed for **64-bit (aarch64)** Home Assistant OS on Raspberry Pi.
- Sauto uses headless Chromium; on a 4 GB Pi this is the heaviest step.
- The dashboard is served through HA Ingress and protected by your HA login.

Source code: <https://github.com/rhopp/enyaqscraper>
