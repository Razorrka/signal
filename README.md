# Signal

A pedal finder and board planner for guitarists who are new to pedals.

**Live:** https://razorrka.github.io/signal/

One self-contained HTML file. No build step, no dependencies, no network calls — open
`index.html` and it works, including offline.

## What it does

**Describe the sound you want** — type what you're after in plain English ("dreamy and washed out
like White Ferrari, under $200", "a fuzz that sounds broken and falling apart") and it sets the
filters for you. Runs entirely offline against a built-in vocabulary of textures, artists and price
expressions — no account, no key, no network. Optionally, paste your own Anthropic API key and
Claude handles the descriptions the offline matcher misses.

**Find** — 137 curated pedals ranked against *your amp*, with tone descriptors, a price window, and
a country filter (56 of them are Japanese — Maxon, One Control, Free The Tone, Vemuram, Providence,
Sobbat, Shin's Music, Leqtique, Effects Bakery and more). Every result explains why it fits or does
not, and links out to real demos, reviews, and current prices.

**Market** — live search across **211,000+ real pedal listings** on Reverb. Actual current prices,
condition, seller photos and a direct link to the listing. Filter by type, condition, or Japanese
builders. This is the whole marketplace rather than the curated list, so there's no amp-fit advice
here — just what is genuinely for sale right now.

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

- Curated-list prices are **approximate street prices in USD as of August 2026** and drift
  constantly. Treat them as a bracket, not a quote. The **Market** tab is different — those are live
  seller asking prices pulled from Reverb at the moment you search.
- The Reverb endpoint is public and needs no key today, but it is not documented for anonymous use
  and could start requiring a token or disappear. Every call fails soft: Find, Board, Learn and Gear
  all keep working with no network, and only the Market tab needs to be online.
- Signal is **not affiliated with Reverb**, takes no commission and adds no affiliate tags. Listings,
  prices and photos belong to the sellers who posted them; every link goes straight to the listing.
- Demo and review buttons are **search links** to YouTube and Google. No review text is reproduced or
  invented — you land on the real results and judge for yourself.
- The amp-fit reasoning only covers the 137 curated pedals. Writing honest per-pedal tags for 211,000
  listings isn't something that can be done by hand, so live results get category-level context only.
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
