# Deploy CaseRank Local Site for Free (GitHub Pages)

## 1) Create a new repository on GitHub

- Name suggestion: `caseranklocal-site`
- Keep it public

## 2) Upload files from this folder

Upload everything inside `site/`:
- `index.html`
- `styles.css`
- `privacy.html`
- `terms.html`
- `refund.html`
- `success.html`
- `cancel.html`

## 3) Enable GitHub Pages

In the repo:
- Settings -> Pages
- Source: Deploy from a branch
- Branch: `main`, folder: `/ (root)`

GitHub will publish a URL like:
- `https://YOUR_USERNAME.github.io/caseranklocal-site/`

## 4) Wire Stripe links

1. Replace `https://checkout.stripe.com/REPLACE_WITH_YOUR_LINK` in `index.html` with your real Stripe checkout URL.
2. Generate a new checkout link using your live website return URLs:

```powershell
llmauto stripe-checkout-link --price-id YOUR_PRICE_ID --success-url "https://YOUR_USERNAME.github.io/caseranklocal-site/success.html" --cancel-url "https://YOUR_USERNAME.github.io/caseranklocal-site/cancel.html"
```

3. Paste the generated checkout URL into `index.html` (both CTA buttons), then re-upload `index.html`.

## 5) Put website URL into Stripe profile

Set business website to:
- `https://YOUR_USERNAME.github.io/caseranklocal-site/`
