# Signal

A pedal finder and board planner for guitarists who are new to pedals.

**Live:** https://razorrka.github.io/signal/

One self-contained HTML file. No build step, no dependencies, no network calls — open
`index.html` and it works, including offline.

## What it does

**Find** — pick what you want it to sound like in plain language (warm, washed out, broken,
shimmering) plus a price window, and it ranks 106 real pedals against *your amp*. Every result
explains why it fits or does not.

**Board** — add pedals and they lay out on a board at true relative size, in correct signal-chain
order, with running totals for cost, current draw, board space and patch cables, and a
fits / does-not-fit verdict against real Pedaltrain dimensions.

**Learn** — what each kind of pedal actually does, why the chain is ordered the way it is, and
the terms that keep coming up. Notes throughout are specific to whichever amp you have selected.

**Gear** — pick your amp. This is not cosmetic; it drives everything else.

## Why the amp matters

The recommendations invert depending on what you plug into:

- **Clean-headroom amp** (Twin, Deluxe Reverb, JC-120) — your pedals make all the gain, so a drive
  pedal has to supply its own voice. Boost-style pedals mostly just get louder.
- **Amp that breaks up early** (AC15, tweed, Crush 12) — low-gain drives and boosts push it over
  the edge; heavy distortion stacked on top turns to mush.
- **High-gain amp** — the amp makes the distortion. A boost in front tightens it; a distortion
  pedal in front adds fizz.
- **No effects loop** — delay and reverb have to sit in front of your dirt, which gets muddy at
  high gain.
- **Small speaker** — a big-bottomed fuzz will flub out a 6" cone no matter how good it is.
- **Modelling amp with built-in effects** — buying a reverb pedal means paying for a sound you
  already own.

## Data honesty

- Prices are **approximate street prices in USD as of August 2026** and drift constantly. Treat
  them as a bracket, not a quote.
- Enclosure drawings are **illustrations at true relative scale**, generated from published
  dimensions. They are not product photographs, and colour and knob layout are approximations.
- Power draw is the published figure where known and a category-typical estimate otherwise.
  Check a pedal's own spec before sizing a supply.
- Nothing here is affiliated with or endorsed by any manufacturer. No listing is sponsored and
  there are no affiliate links.

## Notes

Themes: sunset (default), midnight, ember, mono, paper. State is kept in `localStorage` under the
`sig-` prefix.

Installable on iOS via Safari → Share → Add to Home Screen; a service worker caches it for full
offline use. **When shipping an update, bump `CACHE` in `sw.js`** or installed phones keep serving
the old build.
