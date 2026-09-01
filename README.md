# China Fund

A weekly spending tracker for a savings goal: **$5,920 by 15 December 2026**.

Eight weekly category caps totalling **$115.04/wk** against **$509.72/wk** of net income.
Commute spending is tracked separately from discretionary transport, because it protects
the income that funds the goal.

## Use it

Open the published page, then on iPhone: **Share → Add to Home Screen** for a fullscreen
app icon. On Android: **Install app** from the Chrome menu.

## Privacy

Entries are stored in your own browser via `localStorage`. Nothing is uploaded, and no
server ever sees your data — the hosted page is just the empty dashboard. Use **Export CSV**
to back up or move between devices.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app — markup, styles, logic |
| `sw.js` | Service worker; caches the shell so it opens offline |
| `manifest.webmanifest` | Home-screen name, icon, standalone display |
