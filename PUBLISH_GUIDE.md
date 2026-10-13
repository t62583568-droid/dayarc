# Dayarc: publish guide

Do these in order. Total hands-on time is roughly an hour, plus Google's review wait.

## 0. Quick fills (5 min)

Replace these placeholders:

- `LICENSE`: `[YOUR FULL NAME]`
- `PRIVACY.md`: `[YOUR EMAIL]` (use an email you are fine making public)

Optional: if this was built for a class or with Penn State resources, skim the university's IP policy so there are no surprises about ownership. A personal project on your own time and laptop is normally yours.

## 1. Test it (15 min)

1. `chrome://extensions` > Developer mode > Load unpacked > pick the `extension/` folder.
2. Add 2 or 3 fake habits (do not use real personal ones if you plan to take screenshots). Set one start time several days back so the sun arc and milestones show.
3. Try: slip and restart, switching habits, hide names, export, import, delete, closing and reopening the popup, dark mode.

## 2. Check the name is free (10 min)

"Dayarc" was my pick because the original "Streak" is already a well-known extension. I searched and found no matching extension, but a quick search can miss things. You confirm:

- Search "Dayarc" in the Chrome Web Store, Google, and the USPTO trademark search (tmsearch.uspto.gov).
- If something similar exists in software or apps, rename. To rename, change it in `extension/manifest.json` (two places), the `<title>` in `extension/popup.html`, `README.md`, `PRIVACY.md`, and this guide.

## 3. Put it on GitHub (10 min)

1. Create a public repo and upload everything in the repo zip (keep the folder layout).
2. Confirm `PRIVACY.md` opens at a public URL like `https://github.com/YOU/dayarc/blob/main/PRIVACY.md`. That is your privacy policy URL.
3. Add a screenshot to the README once you have one.

## 4. Take screenshots (10 min)

The store requires at least one, and they must show the real extension. Take real ones instead of mockups.

- Size: 1280x800 (or 640x400), PNG or JPEG.
- Capture the popup (Windows: Win+Shift+S, Mac: Cmd+Shift+4), then place it centered on a plain 1280x800 canvas in any image editor or Canva.
- Suggested set: main streak view, new habit form, a view with a milestone message.
- Use fake habit names only.

The small promo tile is ready: `store-assets/promo-tile-440x280.png`.

## 5. Developer account (10 min)

1. Go to the Chrome Web Store Developer Dashboard and sign in with the Google account you want to publish under.
2. Pay the one-time registration fee (it was $5 when I checked; confirm on the page).
3. Google may require 2-step verification on the account.
4. When asked about trader status, a free hobby project is normally a non-trader. Read the dashboard's wording and answer honestly.

## 6. Upload and fill in the listing

Upload `dayarc-store-upload.zip` (manifest.json is at its root, which the store requires).

**Name:** Dayarc

**Summary (max 132 characters):**
A private day counter for any habit you're leaving behind. Track streaks and milestones. Data never leaves your device.

**Description:**

Dayarc counts the time since the last time you did something you're leaving behind, and shows how close you are to your next milestone.

How it works
- Add a habit and set the last time it happened
- Watch a live counter of days, hours, minutes and seconds
- A sun moves along an arc toward your next milestone, from 1 day up to 2 years
- Track several habits at once
- See your longest streak, your restart count, and optionally money saved
- Restart after a setback without losing your history

Private by design
- Everything stays on your device. No account, no analytics, no tracking, no servers.
- Hide habit names with one checkbox
- Export a backup file whenever you like

Dayarc is a personal counter. It is not medical advice, diagnosis or treatment, and it is not a substitute for professional care. A support section inside the extension lists helplines.

**Category:** the closest of Lifestyle or Productivity in the dropdown.
**Language:** English.
**Icon:** upload `extension/icons/icon128.png`.
**Promo tile:** `store-assets/promo-tile-440x280.png`.
**Privacy policy URL:** your GitHub link to `PRIVACY.md`.
**Support URL:** your GitHub repo's Issues page.

## 7. Privacy tab answers

The dashboard asks several questions. Read each one's help text and answer honestly. These match how Dayarc actually works:

- **Single purpose:** Dayarc tracks the time since a user's last occurrence of a habit and displays a streak counter with milestones.
- **Permission justification, `storage`:** Saves the habits, start times and settings the user enters so they persist between sessions. Data is stored locally and never transmitted.
- **Remote code:** No.
- **Data collection:** Dayarc sends nothing off the device. Habit names can be health-related, so check the dashboard's definition of "collect" and its data-type list. If you are unsure whether local-only storage counts, disclosing "Health information" and explaining in your privacy policy that it stays on-device is the conservative choice.
- **Certifications:** you will be asked to confirm the data is not sold, not used for unrelated purposes, and not used for creditworthiness. All three are true for Dayarc.

## 8. Submit

Set visibility to Public, choose regions, and submit for review. Review can take anywhere from about a day to a few weeks. Keep your account email monitored, because Google writes there if anything needs fixing.

## 9. After approval

- Add the store link and repo link to your resume and README.
- Suggested resume line: *Built and published Dayarc, a privacy-first Chrome extension for tracking habit streaks (JavaScript, Manifest V3, local storage, input validation, import/export), with a public GitHub repo and Chrome Web Store listing.*

---

## Risks I checked and what changed

| Risk | What was done |
|---|---|
| Name conflicts with the existing "Streak" extension | Renamed to Dayarc. You still verify availability (step 2). |
| Health or treatment claims | Copy now says "habit" and "day counter". Disclaimer in the popup, the listing and the privacy policy. |
| Store rejection for privacy | Written privacy policy, minimal permissions (`storage` only), no network requests, no remote code. |
| Someone seeing a sensitive habit name over your shoulder | Neutral extension name, plus a "Hide habit names" option. |
| Losing a streak when the extension is removed | Export and import backup. |
| Malicious or corrupt import files | Strict validation, length and number limits, text rendered as plain text (never HTML). Tested. |
| Corrupt stored data crashing the popup | Bad entries are dropped on load and valid ones kept. Tested. |
| Clock changes making the counter negative | Counter clamps at zero. Tested. |
| Dangerous quitting advice | Support section warns that stopping some substances suddenly can be dangerous and to talk to a doctor. Hotlines are US-focused, so it tells other users to search for their country's helpline. |
| Shaming users after a slip | Restart flow is supportive and keeps your longest streak and history. |
| Hard-to-read text | Contrast increased in light mode. Keyboard focus is visible, reduced motion is respected. |
| Using assets you do not own | Icons and promo tile were generated for this project, fonts are system fonts, no third-party code. |
| Liability | MIT license with the standard "as is" clause. |

Not covered: this is a practical checklist, not legal advice. If you ever add accounts, sync, ads or payments, revisit the privacy policy and consider talking to a lawyer.
