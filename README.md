# the-well-events

The Well Los Osos's events feed. Every hour, GitHub Actions reads The Well's public Church Center calendar (the-well-los-osos-401754.churchcenter.com) and publishes:

- `https://legacyco.github.io/the-well-events/events.json` (read by the Squarespace embeds): upcoming events for the next 12 months and past events from the last 12 months
- `https://legacyco.github.io/the-well-events/events.ics` (calendar people can subscribe to)
- `https://legacyco.github.io/the-well-events/events.rss.xml`
- `https://legacyco.github.io/the-well-events/changes.json` (what changed since the last run, plus Register link warnings)
- `https://legacyco.github.io/the-well-events/embeds/*.js` (the 3 Squarespace embeds) and `preview.html` (all 3 with live data)

No secrets and no login. Only events The Well published on Church Center come through. Home addresses stay off the site (`STREET_ADDRESSES: campus`).

The source of truth for this code, the embeds, and the setup notes is `church-events-sync/` in `LegacyCo/legacy_playground` (branch `claude/trusting-archimedes-86ivhd`, The Well's folder is `church-events-sync/clients/the-well-los-osos/`). Change things there and copy `pco_events_sync.py`, the workflow and `embeds/` over, so the two don't drift.

If a run fails, nothing is published and the site keeps the last good list. The run page says why.
