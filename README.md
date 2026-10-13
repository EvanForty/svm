# SVM — Launch your own Solana

Static landing page for SVM, the one-click launchpad for SVM appchains.
No build step and no folders: every file sits at the repo root.

## Run locally

```bash
npm run dev
# open http://localhost:3000
```

Wallet extensions (Phantom, Solflare, Backpack) only inject on http(s) pages, so use the dev server rather than opening the file directly.

## Deploy to Vercel

1. Push this folder to a GitHub repo.
2. In Vercel, click **Add New → Project** and import the repo.
3. Leave Framework Preset as **Other**, with no build command and no output directory.
4. Deploy.

Or from the terminal: `npx vercel --prod`

## Before going live

- **RPC endpoint:** in `index.html`, set `RPC_URL` near the top of the main script to your own endpoint (Helius, Triton, QuickNode). The public Solana RPC rate-limits browsers, so the wallet's SOL balance may show "unavailable" without one.
- **Social previews:** once you have a domain, change the `og:image` and `twitter:image` meta tags to the full URL, e.g. `https://yourdomain.com/og.png`. X and Telegram need absolute URLs.

## Files

```
index.html            the site
logo.png              header and footer logo
og.png                social share image (1200x630)
favicon.png
apple-touch-icon.png
vercel.json           caching and security headers
package.json          local dev server script
```

## Libraries (loaded from CDN, pinned)

- `@solana/web3.js` 1.95.3 (jsDelivr)
- `three.js` r128 (cdnjs)
- Press Start 2P and VT323 (Google Fonts)
