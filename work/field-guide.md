---
layout: default
title: Case study — Field Guide to Kinderhook
description: How Feed & Seed designed and built field-guide.feed-and-seed.com — a curated, AI-discoverable guide to Kinderhook, NY with 24 entries, structured data, and a clean machine-readable surface.
permalink: /work/field-guide/
---

## Case study: Field Guide to Kinderhook

**Live site** — [field-guide.feed-and-seed.com](https://field-guide.feed-and-seed.com)

A curated guide to food, drink, and small adventures in and around Kinderhook, NY. Twenty-four entries, hand-written notes, no scraped photos, no scroll-jacking. Designed and built by Feed & Seed as a working demonstration of how a small site can be deeply visible to both Google and AI search.

### What we built

A static, single-purpose site that lists places in and around Kinderhook with a short field-guide entry for each — what to order, who runs it, when to go, what makes it good. Each place has its own URL, its own structured data, and its own machine-readable address.

The home page lists all twenty-four places as a structured `ItemList`. Each entry page is its own `LocalBusiness` or `Place` record with name, address, coordinates, opening hours, and a Google `placeId` reference.

### How we made it findable

We treated the site as if its primary readers were machines:

- **Schema.org CollectionPage + ItemList** on the home page — twenty-four places enumerated with stable URLs, so an AI assistant can answer "what's on the Field Guide?" without scraping HTML.
- **One `LocalBusiness` record per place**, with address, lat/lng, opening hours, and the Google `placeId` so that recommendations can be cross-referenced to Google Maps.
- **A machine-readable JSON feed** at [`/places.json`](https://field-guide.feed-and-seed.com/places.json) — the canonical source of every place on the site, served as a `<link rel="alternate" type="application/json">` from the home page.
- **A markdown LLM index** at [`/llms.txt`](https://field-guide.feed-and-seed.com/llms.txt) — a plain-language summary written for language models, linked from the head of every page.
- **An iCal feed** at [`/calendar.ics`](https://field-guide.feed-and-seed.com/calendar.ics) for events, so calendar assistants can subscribe.
- **A sitemap index** at [`/sitemap-index.xml`](https://field-guide.feed-and-seed.com/sitemap-index.xml) submitted to Google Search Console.
- **Canonical URLs, OG and Twitter Card metadata, an SVG favicon, and `theme-color`** on every page.
- **Explicit `Allow:` for AI crawlers** in `robots.txt` — GPTBot, ClaudeBot, PerplexityBot, Google-Extended, and the rest.

### How we kept it fast

- Static site, zero client JavaScript by default.
- Inline-critical CSS, deferred non-critical CSS.
- Home page initial HTML is roughly 67 KB *including* the full ItemList structured data — small enough that a slow rural connection still gets the content immediately.
- No tracking pixels, no third-party fonts, no auto-playing media. Plausible analytics only.

### Tools

- **Astro 5** static-site generator
- **Tailwind v4** for styles
- **TypeScript** for the place data file (single source of truth)
- **GitHub Pages** for hosting; custom subdomain via CNAME

### What we can verify right now

Run the [Google Rich Results Test](https://search.google.com/test/rich-results?url=https%3A%2F%2Ffield-guide.feed-and-seed.com%2F) on the home page and you'll see:

- A `CollectionPage` with an `ItemList` of twenty-four named places.
- Twenty-four individual `LocalBusiness` records on per-place pages.
- A clean head: canonical, OG, Twitter, theme color, all four feed types (sitemap, RSS-style alternates, places.json, llms.txt, calendar.ics).

Ask Claude, ChatGPT, or Perplexity *"what's a good Lebanese place in Kinderhook?"* and you should see Hamrah's surface with the kind of detail that comes from a clean, well-structured page — not a guess.

### Why this matters for your business

Local businesses tend to lean on social media and Google Maps for discovery. Those help, but they're walled gardens — most of their content is invisible to search and to AI. A small, well-structured site like Field Guide does the opposite: every fact about every place is in a form that any tool can read. Same techniques work for a single restaurant, a single farm, a single shop.

We can build you something like this. [Start a conversation]({{ '/services' | relative_url }}).

<p><a href="{{ '/' | relative_url }}">← Back to home</a></p>

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "CreativeWork",
  "name": "Field Guide to Kinderhook",
  "url": "https://field-guide.feed-and-seed.com",
  "description": "A curated guide to food, drink, and small adventures in and around Kinderhook, NY.",
  "creator": {
    "@type": "Organization",
    "name": "Feed & Seed",
    "url": "https://feed-and-seed.com"
  },
  "author": {
    "@type": "Person",
    "name": "David Nyman",
    "url": "https://feed-and-seed.com/about/"
  },
  "about": {
    "@type": "Place",
    "name": "Kinderhook, NY",
    "containedInPlace": {
      "@type": "AdministrativeArea",
      "name": "Columbia County, NY"
    }
  },
  "keywords": [
    "Kinderhook",
    "Columbia County",
    "Hudson Valley",
    "field guide",
    "local recommendations",
    "structured data",
    "generative engine optimization"
  ]
}
</script>
