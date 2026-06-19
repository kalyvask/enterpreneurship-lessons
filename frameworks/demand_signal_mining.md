# Demand Signal Mining

A method for using public, secondary data — reviews, forums, search, code repos — to **generate
hypotheses about where pain lives**, before you spend a single warm intro. It is the systematic
version of the "bench analysis" in RDI (`rdi.md`) and the desk-research half of the industry primer
(`../playbooks/build_industry_primer.md`).

A category of AI tools now does this automatically: set a few criteria, scan a dozen public
sources, and get back a ranked list of "validated" opportunities with scores. The scan is genuinely
useful. The word "validated" is where it goes wrong, and that distinction is the whole point of this
file.

## The one rule: a signal is a lead, never a verdict

**Scanning surfaces *stated interest at scale*. It cannot surface *desperation*.** Everything this
repo stands on — `pmf.md`'s "need is irrelevant, desperation is everything," the Mom Test's
behaviour-over-opinion, the desperation markers in `../stages/02_customer_discovery.md` — depends on
evidence a scan structurally cannot produce. A search trend tells you a topic is rising. It does not
tell you anyone *paid*, *built a workaround*, or *switched*. Those are behaviours, and behaviours
live in conversations and transactions, not in aggregate text.

So mining is **upstream of customer discovery, not a substitute for it.** Its output is a ranked
list of *places to go ask*, each one a hypothesis you still have to kill or confirm with a human.
Treating a high scan score as validation is the exact "starting with a solution and searching for
validation" failure mode named in `../stages/00_prepared_mind.md`. The cure is to hold every mined
signal as a question, not an answer.

## Where to look — the source taxonomy

Different sources surface different kinds of signal. Cast across categories; a pattern that shows up
in three unrelated source types is far stronger than a loud thread in one.

| Source type | Examples of what to read | Signal it tends to surface |
|---|---|---|
| **App / software reviews** | 1–3 star reviews, "I switched from…" reviews, changelog complaints | Switching, unmet need in a *paid* product (high value — money is already moving) |
| **Online communities** | Subreddits, niche forums, Discord/Slack archives, Hacker News | Unprompted complaints, "does anyone know a tool for…", recurring rants |
| **Code & maker platforms** | GitHub repos/issues, Show-HN, indie-maker posts, gists | People who **built their own workaround** (the strongest secondary signal there is) |
| **Q&A sites** | Stack Overflow, Quora, support forums | Recurring questions with bad or no answers = an unmet job |
| **Search behaviour** | Keyword volume, "best X for Y", rising queries, autocomplete | Problem *awareness* and its trend — weak on desperation, useful for timing |
| **Freelance & services markets** | Upwork/Fiverr gigs, agency offerings, "I'll do X for you" listings | People **paying humans** to do a thing manually = a job worth automating |
| **Marketplaces & directories** | App stores, plugin/extension stores, product directories | Where the gaps and the crowded lanes are (competition read, not demand) |
| **Video & long-form** | Tutorial comments, "how I hacked together…" videos, podcast asides | Workarounds described in the wild; emotional intensity around a pain |

## How to rank what you find — the behavioural ladder

Not all signals are equal. Rank them by **how close they are to behaviour** — the same ladder the
Mom Test and the desperation markers use, applied to text someone else already wrote. Strongest at
the top:

1. **Someone built and shared a workaround.** A GitHub repo, a janky spreadsheet posted to a forum,
   a Zapier hack. They spent time/skill to solve it themselves — the single best secondary signal.
2. **Someone is paying to solve it manually.** A recurring Upwork gig, an agency service, "I pay a
   VA to do this." Money is already moving against the problem.
3. **A paid product is being abandoned for it.** "I switched from X because…" / "X still can't do…"
   in reviews. Demand *and* an incumbent gap, with budget proven.
4. **Unprompted, recurring complaint.** The same rant from different people across communities,
   nobody selling to them. Real pain, monetisation unproven.
5. **Recurring unanswered question.** "How do I…" with no good answer, repeated. A job with no hire.
6. **Rising search volume.** Awareness and timing. Says a topic is warming; says nothing about who's
   desperate.
7. **Buzz / engagement / sentiment.** Likes, mentions, "this is cool." By this repo's standard
   (`../stages/06_pmf_measurement.md`), a **vanity metric**. Lowest weight; never let it lead.

A signal's score is how high it sits *and* how many independent source types echo it — not its
volume. Ten thousand searches rank below one posted workaround.

## The workflow

1. **Pick the haystack** (RDI Phase 2) — narrow enough to find experts, broad enough to surprise.
2. **Scan across source types**, not just the one you know. Pull the raw material; don't trust a
   tool's summary without reading the underlying threads/reviews yourself (the "can you defend it
   without the AI" test from `ai_lifecycle.md`).
3. **Cluster the signals** into candidate pains using the synthesis discipline in
   `../playbooks/synthesis.md` — active labels ("teams rebuild this report by hand every Monday"),
   not topics ("reporting").
4. **Rank each cluster on the behavioural ladder above**, weighting by cross-source recurrence.
5. **Convert the top clusters into discovery hypotheses** — a candidate desperate *who* and the pain
   you'd expect them to confirm. Then **go talk to humans**: hand the strongest leads to
   `/ent-interview-prep` and run Stage 02. The scan chose *who to call*; it did not validate the
   pain.

## What this is not

- **Not validation.** No mined signal advances a rubric gate. Gate scores need cited behavioural
  artifacts from real conversations or transactions (`../rubrics/journey_rubrics.md`), and a scan
  produces none.
- **Not an insight.** A gap you found by scanning is, by definition, visible to anyone else
  scanning — that's *consensus*. The non-consensus insight (`../stages/01_insight_and_idea.md`)
  comes from the synthesis you do across these signals plus primary conversations, not from the
  list. "What hasn't been built" is often empty because nobody's desperate, not because there's
  gold there (`pmf.md`: competitors are irrelevant before PMF; first to PMF wins, not first to
  market).
- **Not a blueprint.** Producing a tech stack and roadmap from a scan is the premature-build
  artifact `../stages/05_mvp_build.md` and `/ent-mvp-scoper` exist to cut. Scope is earned by
  evidence, not generated from a search.

## Where this lives in the journey

- [Stage 00 — Prepared Mind](../stages/00_prepared_mind.md) — mining is the structured form of bench
  analysis; do it before, and in service of, primary research.
- [`frameworks/rdi.md`](rdi.md) — Phase 2 ramp-up.
- [`playbooks/build_industry_primer.md`](../playbooks/build_industry_primer.md) — feed mined signals
  into the primer.
- [`playbooks/synthesis.md`](../playbooks/synthesis.md) — cluster the signals into candidate pains.
- [`frameworks/conflicts.md`](conflicts.md) — scan-first vs. desperation-first, and which wins.
- Then: `/ent-interview-prep` and Stage 02. The scan ends where the conversation begins.

## Source

Original synthesis for this repo. The behavioural ladder is the Mom Test / desperation discipline
(`the_mom_test.md`, `pmf.md`) applied to secondary data; the source taxonomy reflects the public
demand-signal category of tools generally. Written in the repo's own words; see `SOURCES.md`.
