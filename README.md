# easy-outdoor-
This is MVP of the web app that should provide quick overview of walks and hikes that you can do around Vancouver
# Wend — Product Management Case Study

*A weekend-outing recommender for casual Vancouver locals.*


## Overview

- **Role:** Product Manager — end to end (research, strategy, design, prototype, deployment). Solo project.
- **Timeline:** `[e.g., ~4 weeks, part-time]`
- **What it is:** A responsive web app that gives a casual Vancouverite three good, low-effort outing picks in under a minute — tailored to their neighbourhood, time, energy, transport, weather, and whether they've got a dog.
- **Live prototype:** `[[your-github-pages-link]](https://anastasiyasparynyak-rgb.github.io/easy-outdoor-/)`
- **Why I built it:** To demonstrate end-to-end product thinking as I transition into product management. I deliberately chose a problem *outside* my day-to-day domain to show the skills travel.

**One-line outcome:** Took a vague idea to a named, live, research-driven prototype — with the discovery, competitive analysis, and iteration to back every decision.

---

## The problem

People in Metro Vancouver with a free weekend often waste time and energy just *deciding what to do outdoors*. The options are endless but hard to weigh against real constraints — how much time you have, whether you're on transit or have a car, how much effort you want, and what the weather's doing. The result is decision fatigue, defaulting to the same two or three places, or losing half the morning scrolling.

Existing tools don't serve the *casual* person well: trail databases are built for committed hikers, and "things to do" listicles are static walls of text you have to cross-reference. There was a gap for a tool that simply *decides for you* and that a beginner can trust.

---

## My role & approach

I owned the full product cycle: problem discovery, user research, persona definition, competitive analysis, prioritization and scoping, UX decisions, building the working prototype, and deploying it. I treated it like a real product: form a hypothesis, test it with users, let the evidence reshape the plan, and ship a focused MVP rather than a pile of half-features.

---

## Discovery

I ran two complementary research methods, in the right order:

**1. User interviews (qualitative — the "why").** Short, past-behaviour conversations (e.g., "walk me through the last time you decided what to do") rather than "would you use my app," which only invites politeness. `[N]` interviews. Early signal was strong and specific: people default to the same spots, find *deciding* the friction (not the doing), and want a quick, glanceable snapshot — one interviewee said too much text was "exhausting," which directly shaped the UI.

**2. A survey (quantitative — the "how common").** A short, behaviour-based Google Form to widen the net, with a screening question first and demographics last. `[N]` responses so far.

**Methodological choices I'd call out:** I screened for my target behaviour, avoided leading questions, and reported results as **counts, not percentages** — the sample is far too small for statistical significance, and implying precision I don't have would undermine the work. The survey is for *direction*, not proof.

---

## Who it's for (persona)

**The Casual Weekend Explorer.** A Metro Vancouver local who isn't a serious hiker, has a free half-day, doesn't want to research, and just wants a nice, low-commitment outing they'll feel good about.

Crucially, I defined the persona by **behaviour, not demographics** — "wants low-effort discovery, low tolerance for research and for picking wrong" — because a single person and a parent can share the exact same job. Demographics describe who answered; behaviour defines the user. The committed hiker (who already pays for AllTrails) is explicitly *not* who I'm building for.

---

## Competitive landscape & positioning

I mapped the space into three buckets:

- **Trail databases (AllTrails, etc.):** huge and powerful, but a *search* tool for people who already know what they want — and key personalization sits behind a paywall.
- **Content / listicles:** local and useful, but static, quick to go stale, and exhausting to cross-reference.
- **General AI chatbots:** can answer "easy transit hike near me," but confidently get *current* local details wrong and return a wall of text.

**My wedge:** a *decision* tool (not a search tool) for casual/beginners, built on **trustworthy, current local data** and a **glanceable format**, that starts from *your neighbourhood*. Positioning it against AllTrails' green brand, I even chose a deliberately different visual identity.

I was honest about the market: local-discovery apps are hard to monetize and I'm not out to beat AllTrails. As a portfolio piece and a personal tool, the value is in finding and articulating the narrow, defensible wedge.

---

## What the research told me

Some findings confirmed my hypotheses; the most valuable ones challenged them.

- **Confirmed:** people default to the same spots; travel-time-from-home matters a lot; a snapshot/low-text format is wanted.
- **Surprise #1 — weather is the single biggest pain.** It was the top annoyance *and* the top decision factor, and it ran through the open-text answers. I had it scoped as a "nice to have." The data promoted it to a headline feature.
- **Surprise #2 — parking.** Nobody was asked about it directly, yet it came up unprompted across multiple questions. Users added a feature to my roadmap.
- **A user nailed my value prop in their own words:** they wished outing info were *standardized in one place* — "is it free, what's the parking/transit situation, hours, do they allow pets… influencers don't provide all those details."
- **A sampling-bias lesson.** My first `[N]` survey responses skewed heavily toward experienced, car-owning locals — the *opposite* of my target persona. Rather than change the product, the right move was to fix the *distribution* and get responses from where casual, transit-reliant, and newer-to-Vancouver people actually are. Catching that bias — and reporting it honestly — is part of doing research properly.

---

## Product principles & key decisions

- **Zero input to first value.** The app opens already showing three good picks; constraints are *adjustments*, not a form. If a beginner has to search, I've lost to the thing I'm replacing.
- **AI as an ingredient, not the product.** AI parses natural language ("chill saturday, no car") into constraints — but the product is the curated data, the trust, and the format, not a chatbot. A thin wrapper over a general model has no reason to exist.
- **Progressive disclosure.** Cards stay glanceable; standardized logistics (parking, cost, pets, transit, weather) live behind a "Details" tap. Depth for those who want it, calm for those who don't.
- **Build vs. integrate.** I didn't rebuild navigation or trail maps. The app deep-links out to Google Maps (walking directions with waypoints) and AllTrails for on-trail routes. Build the missing layer; integrate the rest.
- **Web now, app later.** Built mobile-first as a responsive web app — works in a phone browser today, app-ready tomorrow.

---

## Scope: the MVP & the cut list

**In the MVP:** neighbourhood-aware picks; natural-language input; time / transport / energy / dog / distance / type filters; plain-language difficulty warnings; live weather with rain-aware ranking; standardized logistics; a no-account "done" tracker; walking-route and transit deep-links; and local fun facts.

**Deliberately cut (with reasons):**
- **Accounts / synced history** — high friction and effort; I test the appetite for tracking first with device-only local storage, and earn accounts with evidence.
- **Live events, real-time court wait-times, full restaurant coverage** — these need live data feeds that are expensive to keep accurate, and *stale data kills trust*, which is my entire edge.
- **Embedded, drawn route maps** — real routing data per walk; a "later," not a two-week MVP.

Being able to say *what I chose not to build and why* is as important as the feature list.

---

## The product (features → the finding behind them)

- **Three ranked picks with reasons** ← people want a decision, not a list.
- **Neighbourhood-aware travel time** ← travel-from-home was a top decision factor.
- **Weather-aware ranking + forecast bar** ← weather was the #1 pain; on a wet day, rain-friendly forest walks rise and exposed spots drop.
- **Plain-language difficulty warnings** ← prevents the "I picked something too hard" regret (the Grouse Grind problem).
- **Standardized "Details" (parking, cost, pets, transit, weather, hours)** ← the "standardized info in one place" insight; parking specifically from the survey.
- **Dog filter & tags** ← casual outdoor people often have a dog; low-cost, on-thesis.
- **Urban strolls (Gastown, Yaletown, Kits, etc.)** ← casual users often want to walk-and-graze, not summit.
- **Walk-this-route & transit deep-links** ← solves "where do I start / which streets" without me building a map system.
- **Natural-language input** ← the one high-value, honest use of AI.

---

## Building it

- **Tech:** a single self-contained responsive HTML/CSS/JavaScript file — no backend, no database — so it hosts for free and stays simple.
- **Live weather:** pulled in-browser from Open-Meteo (free, no API key), so the app stays a single static file with no secrets to manage.
- **Deployment:** hosted live on GitHub Pages `[link]`, which also version-controls the work.
- **Naming:** I stress-tested candidate names against the category and found most literal outdoor words were taken or collided with adjacent apps. I chose **Wend** ("to make your way") — short, ownable, clear in the category — with the tagline *"Vancouver outings, made easy."* Learning to pick a *findable, ownable* name (not just a catchy one) was its own small lesson.

---

## Measuring success

Because this is an early prototype with a handful of users, I measure **validation, not scale:**

- **Primary (in progress):** in user testing, `[target ≥70%]` of testers say the top-3 picks included something they'd genuinely do this weekend (a relevance / "hit rate"). *Result: `[fill in after testing]`.*
- **Secondary:** median time-to-decision under a minute.
- **North Star (aspirational):** outings actually taken because of the app.

If I were scaling this, the next-stage metrics would be activation (got a pick they acted on), retention (came back next weekend), and a larger survey to quantify the pains at real confidence.

---

## Iteration: research → product

The clearest thread of the whole project is that the survey *changed the product*. Weather went from a "could-have" to a ranking input; parking became a standardized field; and the difficulty and "what to bring" features were validated by interviews even where the (skewed) survey under-weighted them. Showing that loop — research surfaced a pain I hadn't designed for, and I responded — is the heart of the case study.

---

## What I learned

- **Sampling bias is easy to walk into and important to catch.** A survey that reaches the wrong people confirms the wrong things.
- **Scope discipline beats feature count.** The MVP is stronger for what I left out.
- **Trustworthy data is the moat**, not a cleverer model — which is why I integrated maps/trails rather than rebuilding them.
- **Naming is a decision, not a discovery** — and a name has to be *ownable and findable*, not just catchy.
- **Report small samples honestly** (counts, not percentages) — credibility over impressiveness.

---

## Roadmap / next steps

- Finish discovery with the *right* persona (casual, transit-reliant, newer-to-Vancouver) to firm up the persona.
- Expand and verify the dataset (it's currently a curated `[~25]`-spot sample; travel times are estimates).
- Elevate weather and parking/logistics based on the survey.
- Test the appetite for a "places I've done" history before building real accounts.
- Later: embedded drawn route maps; events and dining as a longer-term vision.

---

## Skills demonstrated

User research (interviews + survey design) · persona definition · competitive analysis · prioritization (MoSCoW / effort-impact) · MVP scoping & trade-off decisions · metrics definition · UX and information design · rapid prototyping & shipping · product positioning · iterating on evidence.

---

## Artifacts & links

- **Live prototype:** `[your-github-pages-link]`
- **Discovery interview guide, survey, and findings** `[link or attach]`
- **Competitive analysis & dataset sources** `[link or attach]`
- **Two-week product brief / roadmap** `[link or attach]`
