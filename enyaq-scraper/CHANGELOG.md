# Changelog

## 1.0.2

- Dashboard: sortable + paginated market list, price-history charts, and a new
  **Changes** overview page (new / price-changed / removed by timeframe).
- New **Compare** page (`/compare`): side-by-side comparison of 2–4 cars with
  normalized attributes (variant, trim, design selection, option package,
  battery, drivetrain, SoH, options) and derived metrics (EUR→CZK price,
  price/1,000 km, % vs same-variant median).
- Listing enrichment (deterministic + derived Enyaq specs), with optional LLM
  extraction via OpenRouter for residual fields.
- New `openrouter_api_key` option (masked) to enable LLM enrichment; leave
  empty for deterministic-only.
- Fix: Home Assistant persistent notifications from the *scheduled* run
  (cron did not inherit the container environment, so `SUPERVISOR_TOKEN` was
  missing and timestamps were UTC).

## 1.0.1

- Fix `init: false` (s6-overlay requires `/init` as PID 1).
- Add `homeassistant_api: true` so persistent notifications work.

## 1.0.0

- Initial release.
- Scrapers: Bazoš.cz (category search + pagination), Sauto.cz (Playwright),
  Škoda Plus (GraphQL).
- SQLite storage with delta engine (new / price change / removed).
- Web dashboard via Home Assistant Ingress.
- Daily scheduled scrape with configurable time.
- Home Assistant persistent notification after each run.
