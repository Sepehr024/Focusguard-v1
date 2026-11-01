# FocusGuard

A lightweight Chrome extension that helps users protect focused work sessions.

## Features

- 25-minute focus timer that continues when the popup closes.
- Optional distraction-domain list.
- During an active session, listed domains are redirected to a local reminder page.
- Daily completed-session and focus-minute totals.
- Data stored locally with `chrome.storage.local`.

## Install for local testing

1. Download or clone this repository.
2. Open `chrome://extensions` in Google Chrome on a desktop.
3. Turn on **Developer mode**.
4. Choose **Load unpacked** and select this project folder.

> Important: GitHub upload from a phone is supported, but loading an unpacked Chrome extension generally requires desktop Chrome. Uploading to GitHub does not publish it to the Chrome Web Store.

## Use

1. Open the FocusGuard toolbar popup.
2. Add domains such as `youtube.com` or `reddit.com`.
3. Start a 25-minute focus session.
4. During the session, listed domains show the FocusGuard reminder page.
5. Completed sessions are counted in the daily statistics.

## Permissions

- `storage`: save the domain list, timer state, and daily totals locally.
- `alarms`: finish the timer even after the popup closes.
- `notifications`: notify when a focus session completes.
- `webNavigation` and `tabs`: detect navigation to a blocked domain and show the local reminder page.
- `<all_urls>` host access: check destination domains against the user's block list.

FocusGuard does not collect, transmit, or sell browsing data.

## Project structure

```text
focusguard-chrome/
├── manifest.json
├── popup.html
├── popup.js
├── styles.css
├── background.js
├── blocked.html
├── blocked.js
├── blocked.css
├── icons/
└── README.md
```

## Known limitations

- The timer duration is currently fixed at 25 minutes.
- Daily statistics are recorded when a session completes; manually stopped sessions are not counted.
- The extension is intended for Chrome and Chromium-based browsers that support Manifest V3.
- Browser-managed pages such as `chrome://` cannot be redirected by extensions.

## Roadmap

- Custom focus and break durations.
- Weekly statistics and export to CSV.
- Optional allow-list mode.
- Automated tests and GitHub Actions.
- Chrome Web Store packaging.

## License

MIT.
