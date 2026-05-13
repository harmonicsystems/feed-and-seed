---
layout: default
title: How we make sites visible to AI search — Feed & Seed
description: Generative Engine Optimization (GEO) for local businesses — the methodology Feed & Seed uses to make small websites visible to ChatGPT, Claude, Perplexity, Google AI Overviews, and traditional search.
permalink: /geo/
faq:
  - q: What is Generative Engine Optimization (GEO)?
    a: GEO is the practice of making a website easy for AI assistants like ChatGPT, Claude, Perplexity, and Google's AI Overviews to read, understand, and recommend. It builds on traditional SEO with additional emphasis on structured data, answer-shaped content, machine-readable feeds, and clear entity signals about who runs the site and where they're located.
  - q: How is GEO different from SEO?
    a: Traditional SEO mainly optimizes for ranked lists of blue links. GEO optimizes for being quoted, summarized, and recommended inside generative answers. The two overlap heavily — a well-structured site does both — but GEO pays extra attention to schema.org structured data, FAQPage and HowTo schemas, llms.txt, JSON or RSS feeds, and the entity graph linking the site to a real person and place.
  - q: Will my site show up in ChatGPT search?
    a: It can, if the site is built correctly. AI search tools crawl the public web, prefer pages that are easy to parse (clean HTML, structured data, descriptive headings), and reward sites that publish a clear answer to the kind of question a user might ask. We build small sites with all of those properties.
  - q: Do you guarantee a ranking?
    a: No one honest can. Search and AI ranking depend on many factors, including how others link to your site over time. What we can guarantee is that we'll ship a site whose technical foundation is excellent — and we can show you the structured data, the Rich Results Test pass, and the AI-crawler-friendly robots.txt to prove it.
  - q: How long until AI tools start recommending my site?
    a: Traditional search tends to start indexing within days; you can see a new site in Google within a week or two. AI assistants vary — some crawl frequently, others update their training corpus on a longer cycle. Generally, expect a few weeks to a few months for full visibility.
  - q: What does a GEO-ready site look like?
    a: It's a small site with a clean, fast home page; a real About page that names the principal and the location; structured data describing the business as a LocalBusiness with address, hours, and area served; a FAQPage answering the questions customers actually ask; an llms.txt summary; an XML sitemap; an explicit robots.txt that welcomes AI crawlers; and OG / Twitter metadata for shareable previews.
---

## How we make sites visible to AI search

Generative search has changed where people find local businesses. Five years ago, the question "where can I buy local honey near Kinderhook?" was a Google search. Today, more often, it's a question put to ChatGPT, Claude, Perplexity, Siri, or Google's AI Overview — and the answer comes from whichever websites those tools can read, understand, and trust.

We design and build small websites for local businesses with this in mind from the start. The methodology below is what we do on every project. It is also what we did on this site — open the page source and you can see it in action.

### 1. Start with the answer, not the marketing

AI assistants summarize. They reward pages that *answer questions in plain language*, with the most useful sentence first. The first paragraph of every page should be a short, factual answer that could be quoted back verbatim. Examples:

> "Feed & Seed is a web and graphic design studio in Kinderhook, NY."

> "The Saturday market on the Kinderhook village green runs from May through October, 9 a.m. to 1 p.m."

We write copy that an AI could read out loud without editing.

### 2. Tell machines who, what, and where

Every page on a site we build carries `schema.org` structured data — JSON-LD blocks in the page head that describe the business as a structured record. For a local business, the essentials are:

- **`@type`** — `LocalBusiness`, `Restaurant`, `Store`, `ProfessionalService`, or a more specific type
- **`name`, `address`, `geo`** — exact name, postal address, latitude/longitude
- **`areaServed`** — what towns, counties, or regions you cover
- **`openingHoursSpecification`** — hours, in structured form
- **`makesOffer`** — what you sell or do
- **`sameAs`** — links to your other web presences (social, GitHub, Yelp), so the entity graph can be stitched together
- **`founder` / `employee`** — at minimum, a `Person` record naming who runs the place

This is the single biggest GEO lever and the one most small-business sites miss entirely.

### 3. Make the FAQ explicit

Most search questions are phrased as questions. We answer them on the page, in a structured way:

- A real `<h3>` for each question, followed by a clear answer
- A `FAQPage` schema in JSON-LD with every Q&A duplicated for machines
- A `HowTo` schema when the answer is a sequence (e.g. "how to find the farm")

A well-structured FAQ is the most common surface for an AI assistant to quote.

### 4. Publish machine-readable feeds

For sites with collections — places, products, events, posts — we publish at least one structured feed:

- **A JSON feed** (`/places.json`, `/products.json`) — the canonical list, served at a stable URL and linked from the home page via `<link rel="alternate" type="application/json">`
- **An RSS or Atom feed** for chronological content
- **An iCal feed** for events
- **An XML sitemap** submitted to Google Search Console

AI crawlers and search engines both prefer feeds over scraping HTML. A site that publishes feeds is a site that gets indexed cleanly.

### 5. Add an llms.txt

[`llms.txt`](https://llmstxt.org) is an emerging convention — a plain-markdown summary of a site, written for language models, served at the site root. It is to AI crawlers what `robots.txt` is to search engines.

We include one on every site we build. It contains a one-paragraph summary of the business, a list of the most important pages, and any facts the site owner wants AI tools to know.

### 6. Welcome AI crawlers explicitly

`robots.txt` should not just allow `*`. We add named `Allow:` directives for every major AI crawler — GPTBot, ClaudeBot, PerplexityBot, Google-Extended, OAI-SearchBot, Applebot-Extended, CCBot, and a dozen more — and point to the sitemap. This is a small, free, important signal.

### 7. Build for speed and stability

AI crawlers and search engines both deprioritize slow, broken pages. We default to:

- Static-site generation (no per-request work)
- Inline-critical CSS, no render-blocking JavaScript
- No tracking pixels, no auto-playing media, no scroll-jacking
- Lighthouse performance score consistently above 95
- Total home-page weight typically under 100 KB

A site that loads instantly on a slow connection in a rural town is the same site that an AI crawler can index cheaply at scale.

### 8. Name a real person

AI assistants and Google's Knowledge Graph both anchor recommendations to **entities** — real people, real organizations, real places. A faceless brand is hard to recommend. An About page that names the principal, links to their other public web presences (`sameAs`), and connects to a real geographic location is much easier.

Our [about page]({{ '/about/' | relative_url }}) does this. We do the same for every client who's willing.

---

## What this looks like in practice

This site is the demonstration. The [Field Guide to Kinderhook]({{ '/work/field-guide/' | relative_url }}) is the larger demonstration. Both were built with the same methodology, and both are AI-discoverable in ways that most small-business websites simply aren't.

## Want this for your business?

We'd love to build it. [See services]({{ '/services' | relative_url }}) or <button type="button" class="reveal-email" data-u="harmonicsystemsio" data-d="gmail.com">reveal email →</button>.

<p><a href="{{ '/' | relative_url }}">← Back to home</a></p>
