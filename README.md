# preparematelatte.milonga.life

The landing page behind the QR code on Milonga business cards. Audience is
existing customers: the page teaches them to get more out of the product, then
asks for a review and a re-order.

## Sections, in order

1. **Hero** — "The Original Mate Latte" / "Energy That Thinks" (same as the sales page)
2. **Two Ways To Make It** — hot (left) and iced (right), each with numbered steps
3. **What Is Yerba Mate?** — the leaf, the ritual, why it isn't tea or coffee
4. **Why Upgrade To The Mate Latte?** — comparison vs matcha, coffee, mushroom coffee
5. **Three Main Ingredients** — how Milonga innovates: Lion's Mane + L-theanine
6. **Leave A Review → 15% off**
7. **Elevate Your Morning Ritual** + **Re-Order** (one-time / Subscribe & Save)
8. **FAQ** — same answers as the sales page, so nothing contradicts

## Before this is fully live

- [x] **Prep videos** — `hot.mp4` and `iced.mp4` are in `assets/video/`, remuxed
      for faststart so they begin playing before the whole file downloads.
- [ ] **Review URL** — set `REVIEW_URL` in `index.html` to the review form of
      whichever platform issues the code. **The 15% is not automatic yet**: it
      needs a review app (Judge.me / Loox / Okendo) connected to a Shopify
      automatic discount. Right now the button falls back to the contact page.
- [ ] **Storefront token** — set `STOREFRONT_TOKEN` in `index.html` so
      Subscribe & Save reliably creates a subscription. Without it the buttons
      fall back to `/cart/add`, which is reliable for one-time purchases and
      best-effort for subscriptions. Same situation as the sales page.

## Design system

Copied from the sales page so the two feel like one brand: gold
`#ecc96f → #d6ab50 → #b98e38`, forest `#1b5130 / #2f7a45`, cream `#f7efe0`,
dark green radial backdrop, self-hosted Gotham (Black / Bold / Regular), gold
logo pinned top-centre that shrinks on scroll.

## Kept in sync by hand

Prices, Shopify variant IDs, the Appstle selling plan, the comparison table and
the FAQ answers are **duplicated** from the sales page in the other repo. If any
of those change there, change them here too — nothing enforces it automatically.

Analytics use the same GA4 and Meta Pixel IDs as the sales page, so scans from
the card are attributed in one funnel.

## Hosting

GitHub Pages serves `main` at the root. The `CNAME` file claims the domain —
never edit or delete it, the URL is printed on business cards. DNS is a `CNAME`
record in GoDaddy: host `preparematelatte` → `bernatent11-pixel.github.io`.

This is a separate repo from the sales page because GitHub Pages serves one
custom domain per repository.
