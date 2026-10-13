# Dayarc

A private day counter for any habit you're leaving behind. A sun travels along an arc toward your next milestone, from 1 day up to 2 years.

![Dayarc](store-assets/promo-tile-440x280.png)

## Features

- Live counter: days, hours, minutes, seconds
- Milestones with encouragement at 1 day, 3 days, 1 week, 2 weeks, 30 days, 60 days, 90 days, 6 months, 1 year, 2 years
- Track up to 50 habits
- Longest streak, restart count, and optional money saved
- Kind, non-judgmental restart flow that keeps your history
- Hide habit names with one checkbox
- Export and import backups
- Light and dark mode
- No account, no analytics, no network requests. Data stays in `chrome.storage.local`

## Install for development

1. Clone or download this repo.
2. Open `chrome://extensions` and turn on **Developer mode**.
3. Click **Load unpacked** and select the `extension/` folder.

## Tech

JavaScript, HTML, CSS, Chrome Extension Manifest V3. Only the `storage` permission is requested. Stored and imported data is validated and sanitized, and user text is rendered as plain text, never as HTML.

## Privacy

See [PRIVACY.md](PRIVACY.md).

## Disclaimer

Dayarc is a personal counter. It is not medical advice, diagnosis, or treatment.

## License

MIT. See [LICENSE](LICENSE).
