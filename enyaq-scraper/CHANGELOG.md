# Changelog

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
